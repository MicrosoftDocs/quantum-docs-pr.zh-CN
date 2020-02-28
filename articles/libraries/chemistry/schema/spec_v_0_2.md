---
title: Broombridge 架构规范（版本0.2）
description: 详细说明了适用于 Microsoft 量程化学库的 Broombridge 量程化学架构 v1.0。
author: guanghaolow
ms.author: gulow@microsoft.com
ms.date: 05/28/2019
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.spec_v_0_2
ms.openlocfilehash: df7e651b7d32e672c6e83346ff603132bd55c1a2
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907267"
---
# <a name="broombridge-specification-v02"></a><span data-ttu-id="b3b95-103">Broombridge 规范 v 0。2</span><span class="sxs-lookup"><span data-stu-id="b3b95-103">Broombridge Specification v0.2</span></span> #

<span data-ttu-id="b3b95-104">本文档中的关键字 "必须"、"不得"、"需要"、"应"、"不应"、"应该"、"不能"、"建议"、"可以" 和 "可选" 将被解释为[RFC 2119](https://tools.ietf.org/html/rfc2119)中所述。</span><span class="sxs-lookup"><span data-stu-id="b3b95-104">The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED",  "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC 2119](https://tools.ietf.org/html/rfc2119).</span></span>

<span data-ttu-id="b3b95-105">标题为 "NOTE"、"信息" 或 "警告" 的任何边栏都是信息性的。</span><span class="sxs-lookup"><span data-stu-id="b3b95-105">Any sidebar with the headings "NOTE," "INFORMATION," or "WARNING" is informative.</span></span>

## <a name="introduction"></a><span data-ttu-id="b3b95-106">介绍</span><span class="sxs-lookup"><span data-stu-id="b3b95-106">Introduction</span></span> ##

<span data-ttu-id="b3b95-107">本部分介绍信息。</span><span class="sxs-lookup"><span data-stu-id="b3b95-107">This section is informative.</span></span>

<span data-ttu-id="b3b95-108">Broombridge 文档用于在量程化学中传达模拟问题的实例，以便使用量程模拟和编程工具链进行处理。</span><span class="sxs-lookup"><span data-stu-id="b3b95-108">Broombridge documents are intended to communicate instances of simulation problems in quantum chemistry for processing using quantum simulation and programming toolchains.</span></span>

## <a name="serialization"></a><span data-ttu-id="b3b95-109">序列化</span><span class="sxs-lookup"><span data-stu-id="b3b95-109">Serialization</span></span> ##

<span data-ttu-id="b3b95-110">本部分进行了规范。</span><span class="sxs-lookup"><span data-stu-id="b3b95-110">This section is normative.</span></span>

<span data-ttu-id="b3b95-111">Broombridge 文档必须序列化为表示 JSON 对象的[YAML 1.2 文档](http://yaml.org/spec/)，如[RFC 4627](https://tools.ietf.org/html/rfc4627)第2.2 节中所述。</span><span class="sxs-lookup"><span data-stu-id="b3b95-111">A Broombridge document MUST be serialized as a [YAML 1.2 document](http://yaml.org/spec/) representing a JSON object as described in [RFC 4627](https://tools.ietf.org/html/rfc4627) section 2.2.</span></span>
<span data-ttu-id="b3b95-112">序列化到 YAML 的对象必须具有 `"$schema"` 其值 `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.2.schema.json"`的属性，并且必须根据 JSON 架构草稿-06 规范 [[1](https://tools.ietf.org/html/draft-wright-json-schema-01)， [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)] 有效。</span><span class="sxs-lookup"><span data-stu-id="b3b95-112">The object serialized to YAML MUST have a property `"$schema"` whose value is `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.2.schema.json"`, and MUST be valid according to the JSON Schema draft-06 specifications [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].</span></span>

<span data-ttu-id="b3b95-113">对于此规范的其余部分，"Broombridge 对象" 将引用从 Broombridge YAML 文档反序列化的 JSON 对象。</span><span class="sxs-lookup"><span data-stu-id="b3b95-113">For the remainder of this specification, "the Broombridge object" will refer to the JSON object deserialized from a Broombridge YAML document.</span></span>

<span data-ttu-id="b3b95-114">除非明确说明，否则对象不能具有本文档明确指定范围以外的其他属性。</span><span class="sxs-lookup"><span data-stu-id="b3b95-114">Unless otherwise explicitly noted, objects MUST NOT have additional properties beyond those specified explicitly in this document.</span></span>

## <a name="additional-definitions"></a><span data-ttu-id="b3b95-115">其他定义</span><span class="sxs-lookup"><span data-stu-id="b3b95-115">Additional Definitions</span></span> ##

<span data-ttu-id="b3b95-116">本部分进行了规范。</span><span class="sxs-lookup"><span data-stu-id="b3b95-116">This section is normative.</span></span>

### <a name="quantity-objects"></a><span data-ttu-id="b3b95-117">数量对象</span><span class="sxs-lookup"><span data-stu-id="b3b95-117">Quantity Objects</span></span> ###

<span data-ttu-id="b3b95-118">本部分进行了规范。</span><span class="sxs-lookup"><span data-stu-id="b3b95-118">This section is normative.</span></span>

<span data-ttu-id="b3b95-119">_数量对象_是 JSON 对象，并且必须具有属性 `units` 其值为表1中列出的允许值之一。</span><span class="sxs-lookup"><span data-stu-id="b3b95-119">A _quantity object_ is a JSON object, and MUST have a property `units` whose value is one of the allowed values listed in Table 1.</span></span>

<span data-ttu-id="b3b95-120">如果某个数量对象除了其 `units` 属性外，还具有一个属性 `value`，则该对象是一个_简单的数量_对象。</span><span class="sxs-lookup"><span data-stu-id="b3b95-120">A quantity object is a _simple quantity object_ if it has a single property `value` in addition to its `units` property.</span></span>
<span data-ttu-id="b3b95-121">`value` 属性的值必须是数字。</span><span class="sxs-lookup"><span data-stu-id="b3b95-121">The value of the `value` property MUST be a number.</span></span>

<span data-ttu-id="b3b95-122">如果某个数量对象具有 `lower` 和 `upper` 其 `units` 属性之外的属性，则它是一个_受限的数量对象_。</span><span class="sxs-lookup"><span data-stu-id="b3b95-122">A quantity object is a _bounded quantity object_ if it has the properties `lower` and `upper` in addition to its `units` property.</span></span>
<span data-ttu-id="b3b95-123">`lower` 和 `upper` 属性的值必须是数字。</span><span class="sxs-lookup"><span data-stu-id="b3b95-123">The values of the `lower` and `upper` properties MUST be numbers.</span></span>
<span data-ttu-id="b3b95-124">绑定的数量对象可以有属性 `value` 其值为数值。</span><span class="sxs-lookup"><span data-stu-id="b3b95-124">A bounded quantity object MAY have a property `value` whose value is a number.</span></span>

<span data-ttu-id="b3b95-125">如果某个数量对象具有属性 `format` 并且属性 `values` 除其 `units` 属性以外，则它是一个_稀疏数组的数量对象_。</span><span class="sxs-lookup"><span data-stu-id="b3b95-125">A quantity object is a _sparse array quantity object_ if it has the property `format` and a property `values` in addition to its `units` property.</span></span>
<span data-ttu-id="b3b95-126">`format` 的值必须是 `sparse`的字符串。</span><span class="sxs-lookup"><span data-stu-id="b3b95-126">The value of `format` MUST be the string `sparse`.</span></span>
<span data-ttu-id="b3b95-127">`values` 属性的值必须是一个数组。</span><span class="sxs-lookup"><span data-stu-id="b3b95-127">The value of the `values` property MUST be an array.</span></span>
<span data-ttu-id="b3b95-128">`values` 的每个元素必须是一个数组，该数组表示稀疏数组数量的索引和值。</span><span class="sxs-lookup"><span data-stu-id="b3b95-128">Each element of `values` MUST be an array representing the indices and value of the sparse array quantity.</span></span>

<span data-ttu-id="b3b95-129">稀疏数组数量对象的每个元素的索引必须在整个稀疏数组数量对象中是唯一的。</span><span class="sxs-lookup"><span data-stu-id="b3b95-129">The indices for each element of a sparse array quantity object MUST be unique across the entire sparse array quantity object.</span></span>
<span data-ttu-id="b3b95-130">如果存在值为 `0`的索引，则分析器必须将稀疏数组的数量对象视为稀疏数组数量对象，而该对象的索引根本就不存在。</span><span class="sxs-lookup"><span data-stu-id="b3b95-130">If an index is present with a value of `0`, a parser MUST treat the sparse array quantity object identically to a sparse array quantity object in which that index is not present at all.</span></span>


<span data-ttu-id="b3b95-131">数量对象必须是</span><span class="sxs-lookup"><span data-stu-id="b3b95-131">A quantity object MUST either be</span></span>

- <span data-ttu-id="b3b95-132">简单数量对象，</span><span class="sxs-lookup"><span data-stu-id="b3b95-132">a simple quantity object,</span></span>
- <span data-ttu-id="b3b95-133">一个有限数量对象，或</span><span class="sxs-lookup"><span data-stu-id="b3b95-133">a bounded quantity object, or</span></span>
- <span data-ttu-id="b3b95-134">稀疏数组数量对象。</span><span class="sxs-lookup"><span data-stu-id="b3b95-134">a sparse array quantity object.</span></span>


### <a name="examples"></a><span data-ttu-id="b3b95-135">示例</span><span class="sxs-lookup"><span data-stu-id="b3b95-135">Examples</span></span> ###

<span data-ttu-id="b3b95-136">本部分介绍信息。</span><span class="sxs-lookup"><span data-stu-id="b3b95-136">This section is informative.</span></span>

<span data-ttu-id="b3b95-137">表示 $ 1.9844146837\,\mathrm{Ha} $：</span><span class="sxs-lookup"><span data-stu-id="b3b95-137">A simple quantity representing $1.9844146837\,\mathrm{Ha}$:</span></span>

```yaml
coulomb_repulsion:
    value: 1.9844146837
    units: hartree
```

<span data-ttu-id="b3b95-138">表示按间隔 $ [-7，-6]\,\mathrm{Ha} $：</span><span class="sxs-lookup"><span data-stu-id="b3b95-138">A bounded quantity representing a uniform distribution over the interval $[-7, -6]\,\mathrm{Ha}$:</span></span>

```yaml
fci_energy:
    upper: -6
    lower: -7
    units: hartree
```

<span data-ttu-id="b3b95-139">下面是一个稀疏数组的数量，其元素 `[1, 2]` 等于 `hello` 并 `[3, 4]` 等于 `world`：</span><span class="sxs-lookup"><span data-stu-id="b3b95-139">The following is a sparse array quantity with an element `[1, 2]` equal to `hello` and an element `[3, 4]` equal to `world`:</span></span>

```yaml
sparse_example:
    format: sparse
    units: hartree
    values:
    - [1, 2, "hello"]
    - [3, 4, "world"]
```

## <a name="format-section"></a><span data-ttu-id="b3b95-140">格式部分</span><span class="sxs-lookup"><span data-stu-id="b3b95-140">Format Section</span></span> ##

<span data-ttu-id="b3b95-141">本部分进行了规范。</span><span class="sxs-lookup"><span data-stu-id="b3b95-141">This section is normative.</span></span>

<span data-ttu-id="b3b95-142">Broombridge 对象必须具有属性 `format` 其值是一个具有名为 `version`的属性的 JSON 对象。</span><span class="sxs-lookup"><span data-stu-id="b3b95-142">The Broombridge object MUST have a property `format` whose value is a JSON object with one property called `version`.</span></span>
<span data-ttu-id="b3b95-143">`version` 属性的值必须为 `"0.2"`。</span><span class="sxs-lookup"><span data-stu-id="b3b95-143">The `version` property MUST have the value `"0.2"`.</span></span>

### <a name="example"></a><span data-ttu-id="b3b95-144">示例</span><span class="sxs-lookup"><span data-stu-id="b3b95-144">Example</span></span> ###

<span data-ttu-id="b3b95-145">本部分介绍信息。</span><span class="sxs-lookup"><span data-stu-id="b3b95-145">This section is informative.</span></span>

```yaml
format:                        # required
    version: "0.2"             # must match exactly
```

## <a name="problem-description-section"></a><span data-ttu-id="b3b95-146">问题说明部分</span><span class="sxs-lookup"><span data-stu-id="b3b95-146">Problem Description Section</span></span> ##

<span data-ttu-id="b3b95-147">本部分进行了规范。</span><span class="sxs-lookup"><span data-stu-id="b3b95-147">This section is normative.</span></span>

<span data-ttu-id="b3b95-148">Broombridge 对象必须具有属性 `problem_description` 其值为 JSON 数组。</span><span class="sxs-lookup"><span data-stu-id="b3b95-148">The Broombridge object MUST have a property `problem_description` whose value is a JSON array.</span></span>
<span data-ttu-id="b3b95-149">`problem_description` 属性的值中的每一项必须是描述一组整型的 JSON 对象，如本部分的其余部分所述。</span><span class="sxs-lookup"><span data-stu-id="b3b95-149">Each item in the value of the `problem_description` property MUST be a JSON object describing one set of integrals, as described in the remainder of this section.</span></span>
<span data-ttu-id="b3b95-150">在本部分的剩余部分中，术语 "问题说明对象" 将引用 Broombridge 对象的 `problem_description` 属性值中的项。</span><span class="sxs-lookup"><span data-stu-id="b3b95-150">In the remainder of this section, the term "problem description object" will refer to an item in the value of the `problem_description` property of the Broombridge object.</span></span>

<span data-ttu-id="b3b95-151">每个问题说明对象都必须具有属性 `metadata` 其值为 JSON 对象。</span><span class="sxs-lookup"><span data-stu-id="b3b95-151">Each problem description object MUST have a property `metadata` whose value is a JSON object.</span></span>
<span data-ttu-id="b3b95-152">`metadata` 的值可以是空的 JSON 对象（即 `{}`），也可以包含实现器定义的其他属性。</span><span class="sxs-lookup"><span data-stu-id="b3b95-152">The value of `metadata` MAY be the empty JSON object (that is, `{}`), or MAY contain additional properties defined by the implementor.</span></span>

### <a name="hamiltonian-section"></a><span data-ttu-id="b3b95-153">Hamiltonian 部分</span><span class="sxs-lookup"><span data-stu-id="b3b95-153">Hamiltonian Section</span></span> ###

#### <a name="overview"></a><span data-ttu-id="b3b95-154">概述</span><span class="sxs-lookup"><span data-stu-id="b3b95-154">Overview</span></span> ####

<span data-ttu-id="b3b95-155">本部分介绍信息。</span><span class="sxs-lookup"><span data-stu-id="b3b95-155">This section is informative.</span></span>

<span data-ttu-id="b3b95-156">每个问题说明对象的 `hamiltonian` 属性介绍了特定量程化学问题的 Hamiltonian，方法是将其一个和两个正文术语作为实数组的稀疏数组列出。</span><span class="sxs-lookup"><span data-stu-id="b3b95-156">The `hamiltonian` property of each problem description object describes the Hamiltonian for a particular quantum chemistry problem by listing out its one- and two-body terms as sparse arrays of real numbers.</span></span>
<span data-ttu-id="b3b95-157">每个问题说明对象所描述的 Hamiltonian 运算符都采用窗体</span><span class="sxs-lookup"><span data-stu-id="b3b95-157">The Hamiltonian operators described by each problem description object take the form</span></span>

<span data-ttu-id="b3b95-158">$ $ H = \sum\_\{i，j\}\sum\_{\sigma\in\\{\uparrow，\downarrow\\}} H\_\{ij\} ^\{\dagger\}\_{i，\sigma} a\_{j，\sigma} + \frac{1}{2}\sum\_\{i，j，k，l\}\sum\_{\sigma，\rho\in\\{\uparrow} a ^ \downarrow\\{i，\sigma} 为 ^ \dagger\_{k，\rho}\_{l，\rho} a\_{j，\sigma}，$ $\_\_</span><span class="sxs-lookup"><span data-stu-id="b3b95-158">$$ H = \sum\_\{i,j\}\sum\_{\sigma\in\\{\uparrow,\downarrow\\}} h\_\{ij\} a^\{\dagger\}\_{i,\sigma} a\_{j,\sigma} + \frac{1}{2}\sum\_\{i,j,k,l\}\sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}} h\_{ijkl} a^\dagger\_{i,\sigma} a^\dagger\_{k,\rho} a\_{l,\rho} a\_{j,\sigma}, $$</span></span>

<span data-ttu-id="b3b95-159">此处 $h _ {ijkl} = （ij | kl） $ in Mulliken 约定。</span><span class="sxs-lookup"><span data-stu-id="b3b95-159">here $h_{ijkl}= (ij|kl)$ in Mulliken convention.</span></span>

<span data-ttu-id="b3b95-160">为清楚起见，electron 术语是</span><span class="sxs-lookup"><span data-stu-id="b3b95-160">For clarity, the one-electron term is</span></span>

<span data-ttu-id="b3b95-161">$ $ h_ {ij} = \int {\mathrm d} x \psi ^ \*\_i （x） \left （\frac{1}{2}\nabla ^ 2 + \sum\_{A} \frac{Z\_\right） \psi\_j （x），$ $\_</span><span class="sxs-lookup"><span data-stu-id="b3b95-161">$$ h_{ij} = \int {\mathrm d}x \psi^\*\_i(x) \left(\frac{1}{2}\nabla^2 + \sum\_{A}\frac{Z\_A}{|x-x\_A|}  \right) \psi\_j(x), $$</span></span>

<span data-ttu-id="b3b95-162">electron 术语是</span><span class="sxs-lookup"><span data-stu-id="b3b95-162">and the two-electron term is</span></span>

<span data-ttu-id="b3b95-163">$ $ h\_\{ijkl\} = \iint \{\mathrm d\}x ^ 2 \psi ^\{\*\}\_i （x\_1） \psi\_x\_\{\}x \{1-x \|\_\_\|\frac \}\_\{\*\}（x\_2） \psi\_l （x\_2）。</span><span class="sxs-lookup"><span data-stu-id="b3b95-163">$$ h\_\{ijkl\} = \iint \{\mathrm d\}x^2 \psi^\{\*\}\_i(x\_1)\psi\_j(x\_1) \frac\{1\}\{\|x\_1 -x\_2\|\}\psi\_k^\{\*\}(x\_2) \psi\_l(x\_2).</span></span>
$$

<span data-ttu-id="b3b95-164">如我们在 `integral_sets` 属性的每个元素的[`basis_set` 属性](#basis-set-object)说明中所述，我们会进一步明确假设所使用的基本函数是真实的。</span><span class="sxs-lookup"><span data-stu-id="b3b95-164">As noted in our description of the [`basis_set` property](#basis-set-object) of each element of the `integral_sets` property, we further explicitly assume that the basis functions used are real-valued.</span></span>
<span data-ttu-id="b3b95-165">这样，我们就可以在术语间使用以下 symmetries 来压缩 Hamiltonian 的表示形式。</span><span class="sxs-lookup"><span data-stu-id="b3b95-165">This allows us to use the following symmetries between the terms to compress the representation of the Hamiltonian.</span></span>

<span data-ttu-id="b3b95-166">$ $ h_ {ijkl} = h_ {ijlk} = h_ {jikl} = h_ {jilk} = h_ {klij} = h_ {klji} = h_ {lkij} = h_ {lkji}。</span><span class="sxs-lookup"><span data-stu-id="b3b95-166">$$ h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkij}=h_{lkji}.</span></span>
$$


#### <a name="contents"></a><span data-ttu-id="b3b95-167">内容</span><span class="sxs-lookup"><span data-stu-id="b3b95-167">Contents</span></span> ####

<span data-ttu-id="b3b95-168">本部分进行了规范。</span><span class="sxs-lookup"><span data-stu-id="b3b95-168">This section is normative.</span></span>

<span data-ttu-id="b3b95-169">每个问题说明对象都必须具有属性 `hamiltonian` 其值为 JSON 对象。</span><span class="sxs-lookup"><span data-stu-id="b3b95-169">Each problem description object MUST have a property `hamiltonian` whose value is a JSON object.</span></span>
<span data-ttu-id="b3b95-170">`hamiltonian` 属性的值称为 Hamiltonian 对象，并且必须具有此部分的其余部分所述的属性 `one_electron_integrals` 和 `two_electron_integrals`。</span><span class="sxs-lookup"><span data-stu-id="b3b95-170">The value of the `hamiltonian` property is known as a Hamiltonian object, and MUST have the properties `one_electron_integrals` and `two_electron_integrals` as described in the remainder of this section.</span></span>

<span data-ttu-id="b3b95-171">每个问题说明对象都必须具有属性 `coulomb_repulsion` 其值为简单数量对象。</span><span class="sxs-lookup"><span data-stu-id="b3b95-171">Each problem description object MUST have a property `coulomb_repulsion` whose value is a simple quantity object.</span></span>
<span data-ttu-id="b3b95-172">每个问题说明对象都必须具有属性 `energy_offet` 其值为简单数量对象。</span><span class="sxs-lookup"><span data-stu-id="b3b95-172">Each problem description object MUST have a property `energy_offet` whose value is a simple quantity object.</span></span>
> <span data-ttu-id="b3b95-173">纪录同时添加的 `coulomb_repulsion` 和 `energy_offet` 的值将捕获 Hamiltonian 的标识术语。</span><span class="sxs-lookup"><span data-stu-id="b3b95-173">[NOTE] The values of `coulomb_repulsion` and `energy_offet` added together capture the identity term of the Hamiltonian.</span></span>

##### <a name="one-electron-integrals-object"></a><span data-ttu-id="b3b95-174">Electron 整型对象</span><span class="sxs-lookup"><span data-stu-id="b3b95-174">One-Electron Integrals Object</span></span> #####

<span data-ttu-id="b3b95-175">本部分进行了规范。</span><span class="sxs-lookup"><span data-stu-id="b3b95-175">This section is normative.</span></span>

<span data-ttu-id="b3b95-176">Hamiltonian 对象的 `one_electron_integrals` 属性必须是一个稀疏数组数量，其索引为两个整数，其值为数值。</span><span class="sxs-lookup"><span data-stu-id="b3b95-176">The `one_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity whose indices are two integers and whose values are numbers.</span></span>
<span data-ttu-id="b3b95-177">每个术语的索引 `[i, j]` 都必须是 `i >= j`。</span><span class="sxs-lookup"><span data-stu-id="b3b95-177">Every term MUST have indices `[i, j]` where `i >= j`.</span></span>

> <span data-ttu-id="b3b95-178">纪录这反映了 $h _ {ij} = h_ {ji} $ 的对称，这是 Hamiltonian 是 Hermitian 的一种后果。</span><span class="sxs-lookup"><span data-stu-id="b3b95-178">[NOTE] This reflects the symmetry that $h_{ij} = h_{ji}$ which is a consequence of the fact that the Hamiltonian is Hermitian.</span></span>


###### <a name="example"></a><span data-ttu-id="b3b95-179">示例</span><span class="sxs-lookup"><span data-stu-id="b3b95-179">Example</span></span> ######

<span data-ttu-id="b3b95-180">本部分介绍信息。</span><span class="sxs-lookup"><span data-stu-id="b3b95-180">This section is informative.</span></span>

<span data-ttu-id="b3b95-181">以下稀疏数组数量表示 Hamiltonian $ $ H = \left （-5.0 （a ^\{\dagger\}\_{1，\uparrow} a\_{1，\uparrow} + a ^\{\dagger\}\_{1，\downarrow} a\_{1，\downarrow}） + 0.17 （a ^\{\dagger\}\_{2，\uparrow} a\_{1，\uparrow} + a ^\{\dagger\}\_{1，\uparrow} a\_{2，\uparrow} + a ^\{\dagger\}\_{2，\downarrow} a\_{1，\downarrow} + a ^\{\dagger\}\_{1，\downarrow} a\_{2，\downarrow}） \right）\\，\mathrm{Ha}。</span><span class="sxs-lookup"><span data-stu-id="b3b95-181">The following sparse array quantity represents the Hamiltonian $$ H = \left(-5.0  (a^\{\dagger\}\_{1,\uparrow} a\_{1,\uparrow}+a^\{\dagger\}\_{1,\downarrow} a\_{1,\downarrow})+ 0.17 (a^\{\dagger\}\_{2,\uparrow} a\_{1,\uparrow}+ a^\{\dagger\}\_{1,\uparrow} a\_{2,\uparrow}+a^\{\dagger\}\_{2,\downarrow} a\_{1,\downarrow}+ a^\{\dagger\}\_{1,\downarrow} a\_{2,\downarrow})\right)\\,\mathrm{Ha}.</span></span>
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
> <span data-ttu-id="b3b95-182">Broombridge 使用基于1的索引。</span><span class="sxs-lookup"><span data-stu-id="b3b95-182">Broombridge uses 1-based indexing.</span></span>


##### <a name="two-electron-integrals-object"></a><span data-ttu-id="b3b95-183">Electron 整型对象</span><span class="sxs-lookup"><span data-stu-id="b3b95-183">Two-Electron Integrals Object</span></span> #####

<span data-ttu-id="b3b95-184">本部分进行了规范。</span><span class="sxs-lookup"><span data-stu-id="b3b95-184">This section is normative.</span></span>

<span data-ttu-id="b3b95-185">Hamiltonian 对象的 `two_electron_integrals` 属性必须是具有一个名为 `index_convention`的附加属性的稀疏数组量。</span><span class="sxs-lookup"><span data-stu-id="b3b95-185">The `two_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity with one additional property called `index_convention`.</span></span>
<span data-ttu-id="b3b95-186">`two_electron_integrals` 的值的每个元素必须具有四个索引。</span><span class="sxs-lookup"><span data-stu-id="b3b95-186">Each element of the value of `two_electron_integrals` MUST have four indices.</span></span>

<span data-ttu-id="b3b95-187">每个 `two_electron_integrals` 属性都必须具有 `index_convention` 属性。</span><span class="sxs-lookup"><span data-stu-id="b3b95-187">Each `two_electron_integrals` property MUST have a `index_convention` property.</span></span>
<span data-ttu-id="b3b95-188">`index_convention` 属性的值必须是表1中列出的允许值之一。</span><span class="sxs-lookup"><span data-stu-id="b3b95-188">The value of the `index_convention` property MUST be one of the allowed values listed in Table 1.</span></span>
<span data-ttu-id="b3b95-189">如果 `mulliken``index_convention` 的值，则对于 `two_electron_integrals` 稀疏数组数量的每个元素，加载 Broombridge 文档的分析器必须实例化 Hamiltonian 术语，使其等于 electron 运算符 $h _ {i，j，k，l} a ^ \ dagger_i ^ \ dagger_j a_k a_l $，其中 $i $、$j $、$k $ 和 $l $ 必须是至少为1的值的整数，其中 $h _ {i，j，k，l} $ 是稀疏数组数量的元素 `[i, j, k, l, h(i, j, k, l)]`。</span><span class="sxs-lookup"><span data-stu-id="b3b95-189">If the value of `index_convention` is `mulliken`, then for each element of the `two_electron_integrals` sparse array quantity, a parser loading a Broombridge document MUST instantiate a Hamiltonian term equal to the two-electron operator $h_{i, j, k, l} a^\dagger_i a^\dagger_j a_k a_l$, where $i$, $j$, $k$, and $l$ MUST be integers of value at least 1, and where $h_{i, j, k, l}$ is the element `[i, j, k, l, h(i, j, k, l)]` of the sparse array quantity.</span></span>

###### <a name="symmetries"></a><span data-ttu-id="b3b95-190">Symmetries</span><span class="sxs-lookup"><span data-stu-id="b3b95-190">Symmetries</span></span> ######

<span data-ttu-id="b3b95-191">本部分进行了规范。</span><span class="sxs-lookup"><span data-stu-id="b3b95-191">This section is normative.</span></span>

<span data-ttu-id="b3b95-192">如果 `two_electron_integrals` 对象的 `index_convention` 属性等于 `mulliken`，则如果存在包含索引 `[i, j, k, l]` 的元素，则不能存在以下索引，除非它们等于 `[i, j, k, l]`：</span><span class="sxs-lookup"><span data-stu-id="b3b95-192">If the `index_convention` property of a `two_electron_integrals` object is equal to `mulliken`, then if an element with indices `[i, j, k, l]` is present, the following indices MUST NOT be present unless they are equal to `[i, j, k, l]`:</span></span>

- `[i, j, l, k]`
- `[j, i, k, l]`
- `[j, i, l, k]`
- `[k, l, i, j]`
- `[k, l, j, i]`
- `[l, k, j, i]`

> [!NOTE]
> <span data-ttu-id="b3b95-193">由于 `index_convention` 属性是稀疏数量对象，因此不能在不同元素上重复任何索引。</span><span class="sxs-lookup"><span data-stu-id="b3b95-193">Because the `index_convention` property is a sparse quantity object, no indices may be repeated on different elements.</span></span>
> <span data-ttu-id="b3b95-194">特别是，如果存在索引 `[i, j, k, l]` 的元素，则其他元素不能具有这些索引。</span><span class="sxs-lookup"><span data-stu-id="b3b95-194">In particular, if an element with indices `[i, j, k, l]` is present, no other element may have those indices.</span></span>


<!-- h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkji}. -->

###### <a name="example"></a><span data-ttu-id="b3b95-195">示例</span><span class="sxs-lookup"><span data-stu-id="b3b95-195">Example</span></span> #######

<span data-ttu-id="b3b95-196">本部分介绍信息。</span><span class="sxs-lookup"><span data-stu-id="b3b95-196">This section is informative.</span></span>

<span data-ttu-id="b3b95-197">以下对象指定 Hamiltonian</span><span class="sxs-lookup"><span data-stu-id="b3b95-197">The following object specifies the Hamiltonian</span></span>

<span data-ttu-id="b3b95-198">$ $ H = \frac12 \sum\_{\sigma，\rho\in\\{\uparrow，\downarrow\\}} \Biggr （1.6 a ^ {\dagger}\_{1，\sigma} ^ {\dagger}\_{1，\rho} a\_{1，\rho} a\_{1，\sigma}-0.1 a ^ {\dagger}\_{6，\sigma} a ^ {\dagger}\_{1，\rho} a\_{3，\rho} a\_{2，\sigma}-0.1 a ^ {\dagger}\_{6，\sigma}，\rho} a\_{3，\sigma}-0.1 a ^ {\dagger}\_{1，\sigma} a ^ {\dagger}\_{6，\rho} a\_{3，\rho} a\_{2，\sigma}-0.1 a ^ {\dagger}\_{1，\sigma} a ^ {\dagger}\_{6，\rho} a\_{2，\rho} a\_{3，\sigma} $ $ $-0.1 a ^ {\dagger}\_{3，\sigma} a ^ {\dagger}\_{2，\rho} a\_{6，\rho} \sigma}-\_{3 0。1，\sigma} 为 ^ {\dagger}\_{2，\rho}\_{1，\rho} a\_{6，\sigma}-0.1 a ^ {\dagger}\_{2，\sigma} a ^ {\dagger}\_{3，\rho} a\_{6，\rho} a\_{1，\sigma}-0.1 a ^ {\dagger}\_{2，\sigma} a ^ {\dagger}\_{3，\rho} a \rho}\_，\sigma}\Biggr\_\_\_\_\\</span><span class="sxs-lookup"><span data-stu-id="b3b95-198">$$ H = \frac12 \sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}}\Biggr( 1.6 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{1,\rho} a\_{1,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{2,\rho} a\_{3,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{2,\rho} a\_{3,\sigma} $$ $$- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{1,\rho} a\_{6,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{1,\rho} a\_{6,\sigma}\Biggr)\\,\textrm{Ha}.</span></span>
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

### <a name="initial-state-section"></a><span data-ttu-id="b3b95-199">初始状态部分</span><span class="sxs-lookup"><span data-stu-id="b3b95-199">Initial State Section</span></span> ###

<span data-ttu-id="b3b95-200">本部分进行了规范。</span><span class="sxs-lookup"><span data-stu-id="b3b95-200">This section is normative.</span></span>

<span data-ttu-id="b3b95-201">`initial_state_suggestion` 对象，其值为 JSON 数组指定指定 Hamiltonian 感兴趣的初始量程状态。</span><span class="sxs-lookup"><span data-stu-id="b3b95-201">The `initial_state_suggestion` object whose value is a JSON array specifies initial quantum states of interest to the specified Hamiltonian.</span></span> <span data-ttu-id="b3b95-202">`initial_state_suggestion` 属性的值中的每一项都必须是描述一个量程状态的 JSON 对象，如本部分的其余部分所述。</span><span class="sxs-lookup"><span data-stu-id="b3b95-202">Each item in the value of the `initial_state_suggestion` property MUST be a JSON object describing one quantum state, as described in the remainder of this section.</span></span>
<span data-ttu-id="b3b95-203">在此部分的剩余部分中，术语 "状态对象" 将引用 Broombridge 对象的 `initial_state_suggestion` 属性值中的项。</span><span class="sxs-lookup"><span data-stu-id="b3b95-203">In the remainder of this section, the term "state object" will refer to an item in the value of the `initial_state_suggestion` property of the Broombridge object.</span></span>

#### <a name="state-object"></a><span data-ttu-id="b3b95-204">状态对象</span><span class="sxs-lookup"><span data-stu-id="b3b95-204">State object</span></span> ####

<span data-ttu-id="b3b95-205">本部分进行了规范。</span><span class="sxs-lookup"><span data-stu-id="b3b95-205">This section is normative.</span></span>

<span data-ttu-id="b3b95-206">每个状态对象都必须具有一个包含字符串的 `label` 属性。</span><span class="sxs-lookup"><span data-stu-id="b3b95-206">Each state object MUST have a `label` property containing a string.</span></span> <span data-ttu-id="b3b95-207">每个状态对象都必须具有一个 `method` 属性。</span><span class="sxs-lookup"><span data-stu-id="b3b95-207">Each state object MUST have a `method` property.</span></span> <span data-ttu-id="b3b95-208">`method` 属性的值必须是表3中所列允许的值之一。</span><span class="sxs-lookup"><span data-stu-id="b3b95-208">The value of the `method` property MUST be one of the allowed values listed in Table 3.</span></span>
<span data-ttu-id="b3b95-209">每个状态对象都有一个属性 `energy` 其值必须为简单数量对象。</span><span class="sxs-lookup"><span data-stu-id="b3b95-209">Each state object MAY have a property `energy` whose value MUST be a simple quantity object.</span></span>

<span data-ttu-id="b3b95-210">如果 `sparse_multi_configurational``method` 属性的值，则状态对象必须具有一个 `superposition` 属性，该属性包含一个基本状态数组及其非规范化 amplitudes。</span><span class="sxs-lookup"><span data-stu-id="b3b95-210">If the value of the `method` property is `sparse_multi_configurational`, the state object MUST have a `superposition` property containing an array of basis states and their unnormalized amplitudes.</span></span>

<span data-ttu-id="b3b95-211">例如，初始状态 $ $ \ket{G0} = \ket{G1} = \ket{G2} = （^ {\dagger}\_{1，\uparrow}a ^ {\dagger}\_{2，\uparrow}a ^ {\dagger}\_{2，\downarrow}） \ket{0} $ $ $ $ \ket{E} = \frac{0.1 （^ {\dagger}\_{1，\uparrow}a ^ {\dagger}\_{2，\uparrow}a ^ {\dagger}\_{2，\downarrow}） + 0.2 （a ^ {\dagger}\_{1，\uparrow}a ^ {\dagger}\_{2，\uparrow}a）} {\dagger} | 0.1 | ^ 2 + | 0.2 | ^ 2}} \downarrow}{0}\_，$ $ 其中 $ \ket{E} $ 具有能量 $0.987 \textrm{Ha} $，由表示</span><span class="sxs-lookup"><span data-stu-id="b3b95-211">For example, the initial states $$ \ket{G0}=\ket{G1}=\ket{G2}=(a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})\ket{0} $$ $$ \ket{E}=\frac{0.1 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})+0.2 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{3,\uparrow}a^{\dagger}\_{2,\downarrow})}{\sqrt{|0.1|^2+|0.2|^2}}\ket{0}, $$ where $\ket{E}$ has energy $0.987 \textrm{Ha}$, are represented by</span></span>
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

<span data-ttu-id="b3b95-212">如果 `unitary_coupled_cluster``method` 属性的值，则状态对象必须具有一个 `cluster_operator` 属性，其值为 JSON 对象。</span><span class="sxs-lookup"><span data-stu-id="b3b95-212">If the value of the `method` property is `unitary_coupled_cluster`, the state object MUST have a `cluster_operator` property whose value is a JSON object.</span></span>
<span data-ttu-id="b3b95-213">JSON 对象必须具有一个 `reference_state` 属性，其值为基础状态。</span><span class="sxs-lookup"><span data-stu-id="b3b95-213">The JSON object MUST have a `reference_state` property whose value is a basis state.</span></span>
<span data-ttu-id="b3b95-214">JSON 对象可能有一个 `one_body_amplitudes` 属性，其值为包含一个正文的分类运算符及其 amplitudes 的数组。</span><span class="sxs-lookup"><span data-stu-id="b3b95-214">The JSON object MAY have a `one_body_amplitudes` property whose value is an array of one-body cluster operators and their amplitudes.</span></span>
<span data-ttu-id="b3b95-215">JSON 对象可能有一个 `two_body_amplitudes` 属性，其值为两主体群集运算符及其 amplitudes 的数组。</span><span class="sxs-lookup"><span data-stu-id="b3b95-215">The JSON object MAY have a `two_body_amplitudes` property whose value is an array of two-body cluster operators and their amplitudes.</span></span>
<span data-ttu-id="b3b95-216">包含基础状态数组及其非规范化 amplitudes 的数组。</span><span class="sxs-lookup"><span data-stu-id="b3b95-216">containing an array of basis states and their unnormalized amplitudes.</span></span>

<span data-ttu-id="b3b95-217">例如，state $ $ \ket{\text{reference}} = （^ {\dagger}\_{1，\uparrow}a ^ {\dagger}\_{2，\uparrow}a ^ {\dagger}\_{2，\downarrow}） \ket{0}，$ $</span><span class="sxs-lookup"><span data-stu-id="b3b95-217">For example, the state $$ \ket{\text{reference}}=(a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})\ket{0}, $$</span></span>

<span data-ttu-id="b3b95-218">$ $ \ket{\text{UCCSD}} = e ^ {T-T ^ \dagger}\ket{\text{reference}}，$ $</span><span class="sxs-lookup"><span data-stu-id="b3b95-218">$$ \ket{\text{UCCSD}}=e^{T-T^\dagger}\ket{\text{reference}}, $$</span></span>

<span data-ttu-id="b3b95-219">$ $ T = 0.1 ^ {\dagger}\_{3，\uparrow}a\_{2，\downarrow} + 0.2 a ^ {\dagger}\_{2，\uparrow}a\_{2，\downarrow}-0.3 a ^ {\dagger}\_{1，\uparrow}a ^ {\dagger}\_{2，\downarrow}a $ $ 由表示\_\_</span><span class="sxs-lookup"><span data-stu-id="b3b95-219">$$ T = 0.1 a^{\dagger}\_{3,\uparrow}a\_{2,\downarrow} + 0.2 a^{\dagger}\_{2,\uparrow}a\_{2,\downarrow} - 0.3 a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{3,\downarrow}a\_{3,\uparrow}a\_{2,\downarrow} $$ is represented by</span></span>
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

#### <a name="basis-set-object"></a><span data-ttu-id="b3b95-220">Basis 集对象</span><span class="sxs-lookup"><span data-stu-id="b3b95-220">Basis Set Object</span></span> ####

<span data-ttu-id="b3b95-221">本部分进行了规范。</span><span class="sxs-lookup"><span data-stu-id="b3b95-221">This section is normative.</span></span>

<span data-ttu-id="b3b95-222">每个问题说明对象都有一个 `basis_set` 属性。</span><span class="sxs-lookup"><span data-stu-id="b3b95-222">Each problem description object MAY have a `basis_set` property.</span></span>
<span data-ttu-id="b3b95-223">如果存在，则 `basis_set` 属性的值必须是具有两个属性的对象 `type` 和 `name`。</span><span class="sxs-lookup"><span data-stu-id="b3b95-223">If present, the value of the `basis_set` property MUST be an object with two properties, `type` and `name`.</span></span>

<span data-ttu-id="b3b95-224">`basis_set` 属性的值所标识的基本函数必须是实际值。</span><span class="sxs-lookup"><span data-stu-id="b3b95-224">The basis functions identified by the value of the `basis_set` property MUST be real-valued.</span></span>

> [!NOTE]
> <span data-ttu-id="b3b95-225">在此规范的未来版本中，假设所有基础函数都是真实的。</span><span class="sxs-lookup"><span data-stu-id="b3b95-225">The assumption that all basis functions are real-valued may be relaxed in future versions of this specification.</span></span>

## <a name="tables-and-lists"></a><span data-ttu-id="b3b95-226">表和列表</span><span class="sxs-lookup"><span data-stu-id="b3b95-226">Tables and Lists</span></span> ##

### <a name="table-1-allowed-physical-units"></a><span data-ttu-id="b3b95-227">表 1。</span><span class="sxs-lookup"><span data-stu-id="b3b95-227">Table 1.</span></span> <span data-ttu-id="b3b95-228">允许的物理单元</span><span class="sxs-lookup"><span data-stu-id="b3b95-228">Allowed Physical Units</span></span> ###

<span data-ttu-id="b3b95-229">本部分进行了规范。</span><span class="sxs-lookup"><span data-stu-id="b3b95-229">This section is normative.</span></span>

<span data-ttu-id="b3b95-230">指定单位的任何字符串都必须是下列各项之一：</span><span class="sxs-lookup"><span data-stu-id="b3b95-230">Any string specifying a unit MUST be one of the following:</span></span>

- `hartree`
- `ev`

<span data-ttu-id="b3b95-231">分析器和生成方必须将以下简单数量对象视为等效：</span><span class="sxs-lookup"><span data-stu-id="b3b95-231">Parsers and producers MUST treat the following simple quantity objects as equivalent:</span></span>

```yaml
- {"units": "hartree", "value": 1}
- {"units": "ev", "value": 27.2113831301723}
```

### <a name="table-2-allowed-index-conventions"></a><span data-ttu-id="b3b95-232">表 2.</span><span class="sxs-lookup"><span data-stu-id="b3b95-232">Table 2.</span></span> <span data-ttu-id="b3b95-233">允许的索引约定</span><span class="sxs-lookup"><span data-stu-id="b3b95-233">Allowed Index Conventions</span></span> ###

<span data-ttu-id="b3b95-234">本部分进行了规范。</span><span class="sxs-lookup"><span data-stu-id="b3b95-234">This section is normative.</span></span>

<span data-ttu-id="b3b95-235">指定索引约定的任何字符串都必须是下列各项之一：</span><span class="sxs-lookup"><span data-stu-id="b3b95-235">Any string specifying an index convention MUST be one of the following:</span></span>

- `mulliken`

<span data-ttu-id="b3b95-236">本部分介绍信息。</span><span class="sxs-lookup"><span data-stu-id="b3b95-236">This section is informative.</span></span>

<span data-ttu-id="b3b95-237">此规范的未来版本中可能会引入其他索引约定。</span><span class="sxs-lookup"><span data-stu-id="b3b95-237">Additional index conventions may be introduced in future versions of this specification.</span></span>

#### <a name="interpretation-of-index-conventions"></a><span data-ttu-id="b3b95-238">索引约定的解释</span><span class="sxs-lookup"><span data-stu-id="b3b95-238">Interpretation of Index Conventions</span></span> ####

<span data-ttu-id="b3b95-239">本部分介绍信息。</span><span class="sxs-lookup"><span data-stu-id="b3b95-239">This section is informative.</span></span>

### <a name="table-3-allowed-state-methods"></a><span data-ttu-id="b3b95-240">表3：</span><span class="sxs-lookup"><span data-stu-id="b3b95-240">Table 3.</span></span> <span data-ttu-id="b3b95-241">允许的状态方法</span><span class="sxs-lookup"><span data-stu-id="b3b95-241">Allowed State methods</span></span> ###

<span data-ttu-id="b3b95-242">本部分进行了规范。</span><span class="sxs-lookup"><span data-stu-id="b3b95-242">This section is normative.</span></span>

<span data-ttu-id="b3b95-243">指定 state 方法的任何字符串都必须是以下类型之一：</span><span class="sxs-lookup"><span data-stu-id="b3b95-243">Any string specifying a state method MUST be one of the following:</span></span>

- `sparse_multi_configurational`
- `unitary_coupled_cluster`

<span data-ttu-id="b3b95-244">本部分介绍信息。</span><span class="sxs-lookup"><span data-stu-id="b3b95-244">This section is informative.</span></span>

<span data-ttu-id="b3b95-245">此规范的未来版本中可能会引入其他状态方法。</span><span class="sxs-lookup"><span data-stu-id="b3b95-245">Additional state methods may be introduced in future versions of this specification.</span></span>
