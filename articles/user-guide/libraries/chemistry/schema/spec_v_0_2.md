---
title: 'Broombridge 架构规范 (版本 0.2) '
description: 详细说明了适用于 Microsoft 量程化学库的 Broombridge 量程化学架构 v1.0。
author: guanghaolow
ms.author: gulow
ms.date: 05/28/2019
ms.topic: conceptual
uid: microsoft.quantum.libraries.chemistry.schema.spec_v_0_2
no-loc:
- Q#
- $$v
ms.openlocfilehash: 8d26b56d88f365144510692466bfffc7feb71d88
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854060"
---
# <a name="broombridge-specification-v02"></a>Broombridge 规范 v 0。2 #

本文档中的关键字 "必须"、"不得"、"需要"、"应"、"不应"、"应该"、"不能"、"建议"、"可以" 和 "可选" 将被解释为 [RFC 2119](https://tools.ietf.org/html/rfc2119)中所述。

标题为 "NOTE"、"信息" 或 "警告" 的任何边栏都是信息性的。

## <a name="introduction"></a>简介 ##

本部分介绍信息。

Broombridge 文档用于在量程化学中传达模拟问题的实例，以便使用量程模拟和编程工具链进行处理。

## <a name="serialization"></a>序列化 ##

本部分进行了规范。

Broombridge 文档必须序列化为表示 JSON 对象的 [YAML 1.2 文档](http://yaml.org/spec/) ，如 [RFC 4627](https://tools.ietf.org/html/rfc4627) 第2.2 节中所述。
序列化到 YAML 的对象必须具有一个属性，该属性 `"$schema"` 的值为 `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.2.schema.json"` ，并且必须根据 JSON 架构草稿-06 规范 [[1](https://tools.ietf.org/html/draft-wright-json-schema-01)， [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)] 有效。

对于此规范的其余部分，"Broombridge 对象" 将引用从 Broombridge YAML 文档反序列化的 JSON 对象。

除非明确说明，否则对象不能具有本文档明确指定范围以外的其他属性。

## <a name="additional-definitions"></a>其他定义 ##

本部分进行了规范。

### <a name="quantity-objects"></a>数量对象 ###

本部分进行了规范。

_数量对象_ 是 JSON 对象，并且必须具有一个属性， `units` 其值为表1中列出的允许值之一。

如果某个数量对象除了其属性之外有一个属性，则它是一个 _简单的数量对象_ `value` `units` 。
属性的值 `value` 必须是数字。

如果某个数量对象具有属性及其属性，则它是一个 _有限数量的对象_ `lower` `upper` `units` 。
和属性的值 `lower` `upper` 必须是数字。
限制数量对象可以有属性 `value` ，其值为数值。

如果某个数量对象具有属性和属性及其属性，则它是一个 _稀疏数组的数量对象_ `format` `values` `units` 。
的值 `format` 必须是字符串 `sparse` 。
属性的值 `values` 必须是数组。
的每个元素 `values` 必须是一个数组，该数组表示稀疏数组数量的索引和值。

稀疏数组数量对象的每个元素的索引必须在整个稀疏数组数量对象中是唯一的。
如果存在值为的索引 `0` ，则分析器必须将稀疏数组的数量对象视为完全不存在该索引的稀疏数组数量对象。


数量对象必须是

- 简单数量对象，
- 一个有限数量对象，或
- 稀疏数组数量对象。


### <a name="examples"></a>示例 ###

本部分介绍信息。

表示 $ 1.9844146837 \Mathrm{Ha} $ 的简单数量 \, ：

```yaml
coulomb_repulsion:
    value: 1.9844146837
    units: hartree
```

在间隔 $ [-7，-6] \, \mathrm{Ha} $：

```yaml
fci_energy:
    upper: -6
    lower: -7
    units: hartree
```

下面是一个稀疏数组的数量，其元素 `[1, 2]` 等于 `hello` ，元素 `[3, 4]` 等于 `world` ：

```yaml
sparse_example:
    format: sparse
    units: hartree
    values:
    - [1, 2, "hello"]
    - [3, 4, "world"]
```

## <a name="format-section"></a>格式部分 ##

本部分进行了规范。

Broombridge 对象必须具有一个属性，该属性的 `format` 值为具有一个名为的属性的 JSON 对象 `version` 。
`version`属性必须具有值 `"0.2"` 。

### <a name="example"></a>示例 ###

本部分介绍信息。

```yaml
format:                        # required
    version: "0.2"             # must match exactly
```

## <a name="problem-description-section"></a>问题说明部分 ##

本部分进行了规范。

Broombridge 对象必须具有一个属性 `problem_description` ，其值为 JSON 数组。
属性值中的每一项 `problem_description` 必须是描述一组整型的 JSON 对象，如本部分的其余部分所述。
在此部分的剩余部分中，术语 "问题说明对象" 将引用 Broombridge 对象的属性值中的项 `problem_description` 。

每个问题说明对象都必须具有一个属性 `metadata` ，其值为 JSON 对象。
的值 `metadata` 可以是 () 的空 JSON 对象，也可以 `{}` 包含实现器定义的其他属性。

### <a name="hamiltonian-section"></a>Hamiltonian 部分 ###

#### <a name="overview"></a>概述 ####

本部分介绍信息。

`hamiltonian`每个问题说明对象的属性通过将其一个和两个正文术语作为实型实数数组列出，来描述特定量程化学问题的 Hamiltonian。
每个问题说明对象所描述的 Hamiltonian 运算符都采用窗体

$ $ H = \sum \_ \{ i，j \} \sum \_ {\sigma\in \\ {\uparrow，\downarrow \\ }} H \_ \{ ij \} a ^ \{ \dagger \} \_ {i，\sigma} a \_ {j，\sigma} + \frac {1} {2} \sum \_ \{ i，j，k，l \} \sum \_ {\sigma，\rho\in \\ {\uparrow，\downarrow \\ }} H \_ {ijkl} a ^ \dagger \_ {i，\sigma} \dagger a \_ \_ \_ {j，\rho}，$ $

此处 $h _ {ijkl} = (ij | kl) $ in Mulliken 约定。

为清楚起见，electron 术语是

$ $ h_ {ij} = \int {\mathrm d} x \psi ^ * \_ i (x) \left ( \frac {1} {2} \nabla ^ 2 + \sum \_ {A} \frac{Z \_ A} {| x-x \_ A |} \right) \psi \_ j (x) ，$ $

electron 术语是

$ $ h \_ \{ ijkl \} = \iint \{ \mathrm d \} x ^ 2 \psi ^ \{ \* \} \_ i (x \_ 1) \psi \_ j (x \_ 1) \frac \{ 1 \} \{ \| x \_ 1-x \_ 2 \| \} \psi \_ k ^ \{ \* \} (x \_ 2) \psi \_ l (x \_ 2) 。
$$

如前所述，在属性的每个元素的[ `basis_set` 属性](#basis-set-object)说明中 `integral_sets` ，我们会进一步明确地假定使用的基本函数是真实的。
这样，我们就可以在术语间使用以下 symmetries 来压缩 Hamiltonian 的表示形式。

$ $ h_ {ijkl} = h_ {ijlk} = h_ {jikl} = h_ {jilk} = h_ {klij} = h_ {klji} = h_ {lkij} = h_ {lkji}。
$$


#### <a name="contents"></a>目录 ####

本部分进行了规范。

每个问题说明对象都必须具有一个属性 `hamiltonian` ，其值为 JSON 对象。
此属性的值 `hamiltonian` 称为 Hamiltonian 对象，并且必须具有属性 `one_electron_integrals` 和， `two_electron_integrals` 如本部分的其余部分所述。

每个问题说明对象都必须具有一个属性 `coulomb_repulsion` ，其值为简单数量对象。
每个问题说明对象都必须具有一个属性 `energy_offet` ，其值为简单数量对象。
> 纪录 `coulomb_repulsion` 和一起添加的值将 `energy_offet` 捕获 Hamiltonian 的标识术语。

##### <a name="one-electron-integrals-object"></a>One-Electron 整型对象 #####

本部分进行了规范。

`one_electron_integrals`Hamiltonian 对象的属性必须是稀疏数组的数量，其索引为两个整数，其值为数值。
每个术语都必须有索引 `[i, j]` `i >= j` 。

> 纪录这反映了 $h _ {ij} = h_ {ji} $ 的对称，这是 Hamiltonian 是 Hermitian 的一种后果。


###### <a name="example"></a>示例 ######

本部分介绍信息。

以下稀疏数组数量表示 Hamiltonian $ $ H = \left (-5.0 (^ \{ \dagger \} \_ {1，\uparrow} a \_ {1，\uparrow} + a ^ \{ \dagger \} \_ {1，\downarrow} a \_ {1，\downarrow} ) + 0.17 (^ \{ \dagger \} \_ {2，\uparrow} a \_ {1，\uparrow} + a ^ \{ \dagger \} \_ {1，\uparrow} a \_ {2，\uparrow} + a ^ \{ \dagger \} \_ {2，\downarrow} a \_ {1，\downarrow} + a ^ \{ \dagger \} \_ {1，\downarrow} a \_ {2，\downarrow} ) \right) \\ ，\mathrm{Ha}。
$$

```yaml
one_electron_integrals:     # required
    units: hartree          # required
    format: sparse          # required
    values:                 # required
        # i j f(i,j)
        - [1, 1, -5.0]
        - [2, 1,  0.17]
```
> [!NOTE]
> Broombridge 使用基于1的索引。


##### <a name="two-electron-integrals-object"></a>Two-Electron 整型对象 #####

本部分进行了规范。

`two_electron_integrals`Hamiltonian 对象的属性必须为稀疏数组，并且有一个名为的附加属性 `index_convention` 。
的值的每个元素 `two_electron_integrals` 必须具有四个索引。

每个 `two_electron_integrals` 属性都必须具有一个 `index_convention` 属性。
属性的值 `index_convention` 必须是表1中列出的允许值之一。
如果的值 `index_convention` 为 `mulliken` ，则对于稀疏数组数量的每个元素 `two_electron_integrals` ，加载 Broombridge 文档的分析器必须实例化 Hamiltonian 术语，使其等于双 electron 运算符 $h _ {i，j，k，l} a ^ \ dagger_i ^ \ dagger_j a_k a_l $，其中 $i $、$j $、$k $ 和 $l $ 必须是至少为1的值的整数，其中 $h _ {i，j，k，l} $ 是 `[i, j, k, l, h(i, j, k, l)]` 稀疏数组数量的元素。

###### <a name="symmetries"></a>Symmetries ######

本部分进行了规范。

如果 `index_convention` 对象的属性 `two_electron_integrals` 等于 `mulliken` ，则如果存在包含索引的元素 `[i, j, k, l]` ，则不能存在以下索引，除非它们等于 `[i, j, k, l]` ：

- `[i, j, l, k]`
- `[j, i, k, l]`
- `[j, i, l, k]`
- `[k, l, i, j]`
- `[k, l, j, i]`
- `[l, k, j, i]`

> [!NOTE]
> 由于 `index_convention` 属性是稀疏数量对象，因此不能在不同元素上重复任何索引。
> 特别是，如果存在包含索引的元素 `[i, j, k, l]` ，则其他元素不能具有这些索引。


<!-- h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkji}. -->

###### <a name="example"></a>示例 #######

本部分介绍信息。

以下对象指定 Hamiltonian

$ $ H = \frac12 \sum \_ {\sigma，\rho\in \\ {\uparrow，\downarrow \\ }} \Biggr ( 1.6 ^ {\dagger} \_ {1，\sigma} a ^ {\dagger} \_ {1，\rho} a \_ {1，\rho} a \_ {1，\sigma}-0.1 a ^ {\dagger} \_ {6，\sigma} a ^ {\dagger} \_ {1，\rho} a \_ {3，\rho} a \_ {2，\sigma}-0.1 a ^ {\dagger} \_ {6，\sigma} a ^ {\dagger} \_ {1，\rho} \_ \_ 0.1 a ^ {\rho} \_ {1，\sigma}-\dagger} ^ {\sigma} \_ {6，\rho} \_ {3，\rho} a \_ {2，\sigma}-0.1 a ^ {\dagger} \_ {1，\sigma} a ^ {\dagger} \_ {6，\rho} a \_ {2，\rho} a \_ {3，\sigma} $ $ $-0.1 a ^ {\dagger} \_ {3，\sigma} a ^ {\dagger} \_ {2，\rho} a \_ {6，\rho} a \_ {1，\sigma}-0.1 a ^ {\dagger} \_ {3，\sigma} a ^ {\dagger} \_ {2，\rho} a \_ {1，\rho} a \_ {6，\sigma}-0.1 a ^ {\dagger} \_ {2，\sigma} a ^ {\dagger} \_ {3，\rho} a \_ {6，\rho} a \_ {1，\sigma}-0.1 a ^ {\dagger} \_ {2，\sigma} a ^ {\dagger} \_ {3，\rho} a \_ {1，\Rho} a \_ {6，\sigma}\Biggr) \\ ，\textrm{Ha}。
$$

```yaml
two_electron_integrals:
    index_convention: mulliken
    units: hartree
    format: sparse
    values:
        - [1, 1, 1, 1,  1.6]
        - [6, 1, 3, 2, -0.1]
```

### <a name="initial-state-section"></a>初始状态部分 ###

本部分进行了规范。

`initial_state_suggestion`其值为 JSON 数组的对象指定了对指定 Hamiltonian 感兴趣的初始量程状态。 属性值中的每一项 `initial_state_suggestion` 必须是描述一个量程状态的 JSON 对象，如本部分的其余部分所述。
在此部分的剩余部分中，术语 "状态对象" 将引用 Broombridge 对象的属性值中的项 `initial_state_suggestion` 。

#### <a name="state-object"></a>状态对象 ####

本部分进行了规范。

每个状态对象都必须具有一个 `label` 包含字符串的属性。 每个状态对象都必须具有一个 `method` 属性。 属性的值 `method` 必须是表3中所列允许的值之一。
每个状态对象都有一个属性，该属性 `energy` 的值必须是一个简单的数量对象。

如果属性的值 `method` 为 `sparse_multi_configurational` ，则状态对象必须具有一个 `superposition` 包含基础状态数组的属性，以及它们的非规范化 amplitudes。

例如，初始状态 $ $ \ket{G0} = \ket{G1} = \ket{G2} = (^ {\dagger} \_ {1，\uparrow}a ^ {\dagger} \_ {2，\uparrow}a ^ {\dagger} \_ {2，\downarrow} ) \ket {0} $ $ $ $ \ket{E} = \frac{0.1 (^ {\dagger} \_ {1，\uparrow}a ^ {\dagger} \_ {2，\uparrow}a ^ {\dagger} \_ {2，\downarrow} ) + 0.2 (^ {\dagger} \_ {1，\uparrow}a ^ {\dagger} \_ {3，\uparrow}a ^ {\dagger} \_ {2，\downarrow} ) } {\sqrt{| 0.1 | ^ 2 + | 0.2 | ^ 2}} \ket {0} ，$ $ 其中 $ \ket{E} $ 具有能源 $0.987 \textrm{Ha} $，由
```yaml
initial_state_suggestions: # optional. If not provided, spin-orbitals will be filled to minimize one-body diagonal term energies.
  - label: "|G0>"
    method: sparse_multi_configurational
    superposition:
      - [1.0, "(1a)+","(2a)+","(2b)+","|vacuum>"]
  - label: "|G1>"
    method: sparse_multi_configurational
    superposition:
      - [-1.0, "(2a)+","(1a)+","(2b)+","|vacuum>"]
  - label: "|G2>"
    method: sparse_multi_configurational
    superposition:
      - [1.0, "(3a)","(1a)+","(2a)+","(3a)+","(2b)+","|vacuum>"]
  - label: "|E>"
    energy: {units: hartree, value: 0.987}
    method: sparse_multi_configurational
    superposition:
      - [0.1, "(1a)+","(2a)+","(2b)+","|vacuum>"]
      - [0.2, "(1a)+","(3a)+","(2b)+","|vacuum>"]
```

如果属性的值 `method` 为，则 `unitary_coupled_cluster` 状态对象必须具有一个属性， `cluster_operator` 其值为 JSON 对象。
JSON 对象必须具有一个 `reference_state` 属性，其值为 "基本" 状态。
JSON 对象可能有一个 `one_body_amplitudes` 属性，其值为包含一个正文的分类运算符及其 amplitudes 的数组。
JSON 对象的 `two_body_amplitudes` 属性的值可以是包含两个正文的分类运算符及其 amplitudes 的数组。
包含基础状态数组及其非规范化 amplitudes 的数组。

例如，state $ $ \ket{\text{reference}} = (^ {\dagger} \_ {1，\uparrow}a ^ {\dagger} \_ {2，\uparrow}a ^ {\dagger} \_ {2，\downarrow} ) \ket {0} ，$ $

$ $ \ket{\text{UCCSD}} = e ^ {T-T ^ \dagger}\ket{\text{reference}}，$ $

$ $ T = 0.1 a ^ {\dagger} \_ {3，\uparrow}a \_ {2，\downarrow} + 0.2 a ^ {\dagger} \_ {2，\uparrow}a \_ {2，\downarrow}-0.3 a ^ {\dagger} \_ {1，\uparrow}a ^ {\dagger} \_ {\downarrow}a，\uparrow}a \_ {3，\downarrow} \_ {2，$ $ 由表示
```yaml
initial_state_suggestions: # optional. If not provided, spin-orbitals will be filled to minimize one-body diagonal term energies.
  - label: "UCCSD"
    method: unitary_coupled_cluster
    cluster_operator: # Initial state that cluster operator is applied to.
        reference_state: 
          [1.0, "(1a)+", "(2a)+", "(2b)+", '|vacuum>']
        one_body_amplitudes: # A one-body cluster term is t^{q}_{p} a^\dag_p a_q   
            - [0.1, "(3a)+", "(2b)"]
            - [-0.2, "(2a)+", "(2b)"]
        two_body_amplitudes: # A two-body unitary cluster term is t^{rs}_{pq} a^\dag_p a^\dag_q a_r a_s
            - [-0.3, "(1a)+", "(3b)+", "(3a)", "(2b)"]
```

#### <a name="basis-set-object"></a>Basis 集对象 ####

本部分进行了规范。

每个问题说明对象都可以具有 `basis_set` 属性。
如果存在，则属性的值 `basis_set` 必须是具有两个属性（和）的对象 `type` `name` 。

属性值标识的基本函数 `basis_set` 必须是实际值。

> [!NOTE]
> 在此规范的未来版本中，假设所有基础函数都是真实的。

## <a name="tables-and-lists"></a>表和列表 ##

### <a name="table-1-allowed-physical-units"></a>表 1. 允许的物理单元 ###

本部分进行了规范。

指定单位的任何字符串都必须是下列各项之一：

- `hartree`
- `ev`

分析器和生成方必须将以下简单数量对象视为等效：

```yaml
- {"units": "hartree", "value": 1}
- {"units": "ev", "value": 27.2113831301723}
```

### <a name="table-2-allowed-index-conventions"></a>表 2. 允许的索引约定 ###

本部分进行了规范。

指定索引约定的任何字符串都必须是下列各项之一：

- `mulliken`

本部分介绍信息。

此规范的未来版本中可能会引入其他索引约定。

#### <a name="interpretation-of-index-conventions"></a>索引约定的解释 ####

本部分介绍信息。

### <a name="table-3-allowed-state-methods"></a>表 3. 允许的状态方法 ###

本部分进行了规范。

指定 state 方法的任何字符串都必须是以下类型之一：

- `sparse_multi_configurational`
- `unitary_coupled_cluster`

本部分介绍信息。

此规范的未来版本中可能会引入其他状态方法。
