---
title: Broombridge 架构规范（版本0.1）
description: 详细说明了适用于 Microsoft 量程化学库的 Broombridge 量程化学架构 v 0.1。
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.spec_v_0_1
ms.openlocfilehash: 618892b6cb01855d17522b06e47f72f68595ab38
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274450"
---
# <a name="broombridge-specification-v01"></a>Broombridge 规范 v 0。1 #

本文档中的关键字 "必须"、"不得"、"需要"、"应"、"不应"、"应该"、"不能"、"建议"、"可以" 和 "可选" 将被解释为[RFC 2119](https://tools.ietf.org/html/rfc2119)中所述。

标题为 "NOTE"、"信息" 或 "警告" 的任何边栏都是信息性的。

## <a name="introduction"></a>简介 ##

本部分介绍信息。

Broombridge 文档用于在量程化学中传达模拟问题的实例，以便使用量程模拟和编程工具链进行处理。

## <a name="serialization"></a>序列化 ##

本部分进行了规范。

Broombridge 文档必须序列化为表示 JSON 对象的[YAML 1.2 文档](http://yaml.org/spec/)，如[RFC 4627](https://tools.ietf.org/html/rfc4627)第2.2 节中所述。
序列化到 YAML 的对象必须具有一个属性，该属性 `"$schema"` 的值为 `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.1.schema.json"` ，并且必须根据 JSON 架构草稿-06 规范 [[1](https://tools.ietf.org/html/draft-wright-json-schema-01)， [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)] 有效。

对于此规范的其余部分，"Broombridge 对象" 将引用从 Broombridge YAML 文档反序列化的 JSON 对象。

除非明确说明，否则对象不能具有本文档明确指定范围以外的其他属性。

## <a name="additional-definitions"></a>其他定义 ##

本部分进行了规范。

### <a name="quantity-objects"></a>数量对象 ###

本部分进行了规范。

_数量对象_是 JSON 对象，并且必须具有一个属性， `units` 其值为表1中列出的允许值之一。

如果某个数量对象除了其属性之外有一个属性，则它是一个_简单的数量对象_ `value` `units` 。
属性的值 `value` 必须是数字。

如果某个数量对象具有属性及其属性，则它是一个_有限数量的对象_ `lower` `upper` `units` 。
和属性的值 `lower` `upper` 必须是数字。
限制数量对象可以有属性 `value` ，其值为数值。

如果某个数量对象具有属性和属性及其属性，则它是一个_稀疏数组的数量对象_ `format` `values` `units` 。
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
`version`属性必须具有值 `"0.1"` 。

### <a name="example"></a>示例 ###

本部分介绍信息。

```yaml
format:                        # required
    version: "0.1"             # must match exactly
```

## <a name="integral-sets-section"></a>整数集部分 ##

本部分进行了规范。

Broombridge 对象必须具有一个属性 `integral_sets` ，其值为 JSON 数组。
属性值中的每一项 `integral_sets` 必须是描述一组整型的 JSON 对象，如本部分的其余部分所述。
在此部分的剩余部分中，术语 "整数集对象" 将引用 Broombridge 对象的属性值中的项 `integral_sets` 。

每个整型集对象都必须具有一个属性 `metadata` ，其值为 JSON 对象。
的值 `metadata` 可以是空的 JSON 对象（即 `{}` ），也可以包含实现器定义的其他属性。

### <a name="hamiltonian-section"></a>Hamiltonian 部分 ###

#### <a name="overview"></a>概述 ####

本部分介绍信息。

`hamiltonian`每个整型集对象的属性通过将其一个和两个正文术语作为实型实数数组列出，来描述特定量程化学问题的 Hamiltonian。
每个整数集对象所描述的 Hamiltonian 运算符采用形式

$ $ H = \sum \_ \{ i，j \} \sum \_ {\sigma\in \\ {\uparrow，\downarrow \\ }} H \_ \{ ij \} a ^ \{ \dagger \} \_ {i，\sigma} a \_ {j，\sigma} + \frac {1} {2} \sum \_ \{ i，j，k，l \} \sum \_ {\sigma，\rho\in \\ {\uparrow，\downarrow \\ }} H \_ {ijkl} a ^ \dagger \_ {i，\sigma} \dagger a \_ \_ \_ {j，\rho}，$ $

此处 $h _ {ijkl} = （ij | kl） $ in Mulliken 约定。

为清楚起见，electron 术语是

$ $ h_ {ij} = \int {\mathrm d} x \psi ^ * \_ i （x） \left （\frac {1} {2} \nabla ^ 2 + \sum \_ {A} \frac{Z \_ a} {| x-x \_ A |} \right） \psi \_ j （x），$ $

electron 术语是

$ $ h \_ \{ ijkl \} = \iint \{ \mathrm d \} x ^ 2 \psi ^ \{ \* \} \_ i （x \_ 1） \psi \_ j （x \_ 1） \frac \{ 1 \} \{ \| x \_ 1-x \_ 2 \| \} \psi \_ k ^ \{ \* \} （x \_ 2） \psi \_ l （x \_ 2）。
$$

如前所述，在属性的每个元素的[ `basis_set` 属性](#basis-set-object)说明中 `integral_sets` ，我们会进一步明确地假定使用的基本函数是真实的。
这样，我们就可以在术语间使用以下 symmetries 来压缩 Hamiltonian 的表示形式。

$ $ h_ {ijkl} = h_ {ijlk} = h_ {jikl} = h_ {jilk} = h_ {klij} = h_ {klji} = h_ {lkij} = h_ {lkji}。
$$


#### <a name="contents"></a>目录 ####

本部分进行了规范。

每个整数集都必须具有一个属性 `hamiltonian` ，其值为 JSON 对象。
此属性的值 `hamiltonian` 称为 Hamiltonian 对象，并且必须具有属性 `one_electron_integrals` 和， `two_electron_integrals` 如本部分的其余部分所述。
Hamiltonian 对象还可以具有属性 `particle_hole_representation` 。
如果存在，则的值 `particle_hole_representation` 必须遵循本部分的其余部分所述的格式。

##### <a name="one-electron-integrals-object"></a>Electron 整型对象 #####

本部分进行了规范。

`one_electron_integrals`Hamiltonian 对象的属性必须是稀疏数组的数量，其索引为两个整数，其值为数值。
每个术语都必须有索引 `[i, j]` `i >= j` 。

> 纪录这反映了 $h _ {ij} = h_ {ji} $ 的对称，这是 Hamiltonian 是 Hermitian 的一种后果。


###### <a name="example"></a>示例 ######

本部分介绍信息。

以下稀疏数组数量表示 Hamiltonian $ $ H = \left （-5.0 （a ^ \{ \dagger \} \_ {1，\uparrow} a \_ {1，\uparrow} + a ^ \{ \dagger \} \_ {1，\downarrow} a \_ {1，\downarrow}） + 0.17 （^ \{ \dagger \} \_ {2，\uparrow} a \_ {1，\uparrow} + a ^ \{ \dagger \} \_ {1，\uparrow} a \_ {2，\uparrow} + a ^ \{ \dagger \} \_ {2，\downarrow} a \downarrow} a \_ \{ \} \_ \_ {2，\dagger） \downarrow}） \\ ，\downarrow}
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


##### <a name="two-electron-integrals-object"></a>Electron 整型对象 #####

本部分进行了规范。

`two_electron_integrals`Hamiltonian 对象的属性必须为稀疏数组，并且有一个名为的附加属性 `index_convention` 。
的值的每个元素 `two_electron_integrals` 必须具有四个索引。

每个 `two_electron_integrals` 属性都必须具有一个 `index_convention` 属性。
属性的值 `index_convention` 必须是表1中列出的允许值之一。
如果的值 `index_convention` 为 `mulliken` ，则对于稀疏数组数量的每个元素 `two_electron_integrals` ，加载 Broombridge 文档的分析器必须实例化 Hamiltonian 术语，使其等于双 electron 运算符 $h _ {i，j，k、l} ^ \ dagger_i ^ \ dagger_j a_k a_l $，其中 $i $、$j $、$k $ 和 $l $ 必须是介于1和整数集对象的属性指定的电子数之间的整数 `n_electrons` ，其中 $h _ {i，j，k，l} $ 是 `[i, j, k, l, h(i, j, k, l)]` 稀疏数组数量的元素。

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

$ $ H = \frac12 \sum \_ {\sigma，\rho\in \\ {\uparrow，\downarrow \\ }} \Biggr （1.6 a ^ {\dagger} \_ {1，\sigma} a ^ {\dagger} \_ {1，\rho} a \_ {1，\rho} a \_ {1，\sigma}-0.1 a ^ {\dagger} \_ {6，\sigma} a ^ {\dagger} \_ {1，\rho} a \_ {3，\rho} a \_ {2，\sigma}-0.1 a ^ {\dagger} \_ {6，\sigma} a ^ {\dagger} \_ {1，\rho} \_ \_ 0.1 a ^ {\rho} \_ {1，\sigma}-\dagger} ^ {\sigma} \_ {6，\rho} \_ {3，\rho} a \_ {2，\sigma}-0.1 a ^ {\dagger} \_ {1，\sigma} a ^ {\dagger} \_ {6，\rho} a \_ {2，\rho} a \_ {3，\sigma} $ $ $-0.1 a ^ {\dagger} \_ {3，\sigma} a ^ {\dagger} \_ {2，\rho} a \_ {6，\rho} a \_ {1，\sigma}-0.1 a ^ {\dagger} \_ {3，\sigma} a ^ {\dagger} \_ {2，\rho} a \_ {1，\rho} a \_ {6，\sigma}-0.1 a ^ {\dagger} \_ {2，\sigma} a ^ {\dagger} \_ {3，\rho} a \_ {6，\rho} a \_ {1，\sigma}-0.1 a ^ {\dagger} \_ {2，\sigma} a ^ {\dagger} \_ {3，\rho} a \_ {1，\Rho} a \_ {6，\sigma}\Biggr） \\ ，\textrm{Ha}。
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

##### <a name="particlehole-representation-object"></a>粒子–洞表示对象 #####

本部分进行了规范。

"粒子-孔表示" 对象指定所存储的 "整型" 定义为 "粒子"，其中的 "创建" 和 "annihilation" 运算符从所用的引用状态（如 Hartree – Fock 状态）描述 excitations。
对象是可选的。
如果未指定对象，则在粒子孔表示形式中，Hamiltonian 将被解释为 not 给定的。
如果存在，则的值 `particle_hole_representation` 必须是稀疏数组的数量对象，其索引为四个整数，其值为数字和字符串。
每个元素的值的字符串部分必须只包含字符 `'+'` ， `'-'` 指定在 "粒子–洞" 表示中，术语中的给定因素是创建还是 annihilation 运算符。  例如 `"-+++"` ，与在站点 $i $ 和在站点上创建的粒子 $j，k $ 和 $l $。

> [!NOTE]
> 由于的值 `particle_hole_representation` 是稀疏数组的数量对象， `unit` 因此 `format` 必须指定和属性。
> 表1中列出了可接受的单位。
> `format`属性是必需的，它指示是否将 Hamiltonian 系数指定为密集数组或稀疏数组。
> 在当前版本中，仅支持稀疏数组，并解释所有未指定的元素为 $0 $，但将来的版本可能会添加对属性的其他值的支持 `format` 。

### <a name="initial-state-section"></a>初始状态部分 ###

Initial_state_suggestion 对象指定对指定 Hamiltonian 感兴趣的初始量程状态。 此对象必须是 JSON 对象的数组 `state` 。

#### <a name="state-object"></a>状态对象 ####

每个状态都表示 superposition 的 orbitals。 每个状态对象都必须具有一个 `label` 包含字符串的属性。 每个状态对象都必须具有一个 `superposition` 属性，该属性包含一个基本状态数组及其非规范化 amplitudes。

例如，初始状态 $ $ \ket{G0} = \ket{G1} = \ket{G2} = （^ {\dagger} \_ {1，\uparrow}a ^ {\dagger} \_ {2，\uparrow}a ^ {\dagger} \_ {2，\downarrow}） \ket {0} $ $ $ $ \ket{E} = \frac{0.1 （^ {\dagger} \_ {1，\uparrow}a ^ {\dagger} \_ {2，\uparrow}a ^ {\dagger} \_ {2，\downarrow}） + 0.2 （a ^ {\dagger} \_ {1，\uparrow}a ^ {\dagger} \_ {3，\uparrow}a ^ {\dagger} \_ {2，\downarrow}）} {\sqrt{| 0.1 | ^ 2 + | 0.2 | ^ 2}} \ket {0} $ $ 由表示
```yaml
initial_state_suggestions: # optional. If not provided, spin-orbitals will be filled to minimize one-body diagonal term energies.
    - state:
        label: "|G0>"
        superposition:
            - [1.0, "(1a)+","(2a)+","(2b)+","|vacuum>"]
    - state:
        label: "|G1>"
        superposition:
            - [-1.0, "(2a)+","(1a)+","(2b)+","|vacuum>"]
    - state:
        label: "|G2>"
        superposition:
            - [1.0, "(3a)","(1a)+","(2a)+","(3a)+","(2b)+","|vacuum>"]
    - state:
        label: "|E>"
        superposition:
            - [0.1, "(1a)+","(2a)+","(2b)+","|vacuum>"]
            - [0.2, "(1a)+","(3a)+","(2b)+","|vacuum>"]
```

#### <a name="basis-set-object"></a>Basis 集对象 ####

本部分进行了规范。

每个整数集对象都可以具有 `basis_set` 属性。
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
