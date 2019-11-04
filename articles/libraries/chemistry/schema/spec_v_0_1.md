---
title: Broombridge 架构规范
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.spec_v_0_1
ms.openlocfilehash: a950e04d44e5de8091b034214258d2c2fa663f58
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2019
ms.locfileid: "73185352"
---
# <a name="broombridge-specification-v01"></a><span data-ttu-id="ab9e4-102">Broombridge 规范 v 0。1</span><span class="sxs-lookup"><span data-stu-id="ab9e4-102">Broombridge Specification v0.1</span></span> #

<span data-ttu-id="ab9e4-103">本文档中的关键字 "必须"、"不得"、"需要"、"应"、"不应"、"应该"、"不能"、"建议"、"可以" 和 "可选" 将被解释为[RFC 2119](https://tools.ietf.org/html/rfc2119)中所述。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-103">The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED",  "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC 2119](https://tools.ietf.org/html/rfc2119).</span></span>

<span data-ttu-id="ab9e4-104">标题为 "NOTE"、"信息" 或 "警告" 的任何边栏都是信息性的。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-104">Any sidebar with the headings "NOTE," "INFORMATION," or "WARNING" is informative.</span></span>

## <a name="introduction"></a><span data-ttu-id="ab9e4-105">简介</span><span class="sxs-lookup"><span data-stu-id="ab9e4-105">Introduction</span></span> ##

<span data-ttu-id="ab9e4-106">本部分介绍信息。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-106">This section is informative.</span></span>

<span data-ttu-id="ab9e4-107">Broombridge 文档用于在量程化学中传达模拟问题的实例，以便使用量程模拟和编程工具链进行处理。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-107">Broombridge documents are intended to communicate instances of simulation problems in quantum chemistry for processing using quantum simulation and programming toolchains.</span></span>

## <a name="serialization"></a><span data-ttu-id="ab9e4-108">序列化</span><span class="sxs-lookup"><span data-stu-id="ab9e4-108">Serialization</span></span> ##

<span data-ttu-id="ab9e4-109">本部分进行了规范。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-109">This section is normative.</span></span>

<span data-ttu-id="ab9e4-110">Broombridge 文档必须序列化为表示 JSON 对象的[YAML 1.2 文档](http://yaml.org/spec/)，如[RFC 4627](https://tools.ietf.org/html/rfc4627)第2.2 节中所述。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-110">A Broombridge document MUST be serialized as a [YAML 1.2 document](http://yaml.org/spec/) representing a JSON object as described in [RFC 4627](https://tools.ietf.org/html/rfc4627) section 2.2.</span></span>
<span data-ttu-id="ab9e4-111">序列化到 YAML 的对象必须具有 `"$schema"` 其值 `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.1.schema.json"`的属性，并且必须根据 JSON 架构草稿-06 规范 [[1](https://tools.ietf.org/html/draft-wright-json-schema-01)， [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)] 有效。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-111">The object serialized to YAML MUST have a property `"$schema"` whose value is `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.1.schema.json"`, and MUST be valid according to the JSON Schema draft-06 specifications [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].</span></span>

<span data-ttu-id="ab9e4-112">对于此规范的其余部分，"Broombridge 对象" 将引用从 Broombridge YAML 文档反序列化的 JSON 对象。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-112">For the remainder of this specification, "the Broombridge object" will refer to the JSON object deserialized from a Broombridge YAML document.</span></span>

<span data-ttu-id="ab9e4-113">除非明确说明，否则对象不能具有本文档明确指定范围以外的其他属性。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-113">Unless otherwise explicitly noted, objects MUST NOT have additional properties beyond those specified explicitly in this document.</span></span>

## <a name="additional-definitions"></a><span data-ttu-id="ab9e4-114">附加定义</span><span class="sxs-lookup"><span data-stu-id="ab9e4-114">Additional Definitions</span></span> ##

<span data-ttu-id="ab9e4-115">本部分进行了规范。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-115">This section is normative.</span></span>

### <a name="quantity-objects"></a><span data-ttu-id="ab9e4-116">数量对象</span><span class="sxs-lookup"><span data-stu-id="ab9e4-116">Quantity Objects</span></span> ###

<span data-ttu-id="ab9e4-117">本部分进行了规范。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-117">This section is normative.</span></span>

<span data-ttu-id="ab9e4-118">_数量对象_是 JSON 对象，并且必须具有属性 `units` 其值为表1中列出的允许值之一。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-118">A _quantity object_ is a JSON object, and MUST have a property `units` whose value is one of the allowed values listed in Table 1.</span></span>

<span data-ttu-id="ab9e4-119">如果某个数量对象除了其 `units` 属性外，还具有一个属性 `value`，则该对象是一个_简单的数量_对象。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-119">A quantity object is a _simple quantity object_ if it has a single property `value` in addition to its `units` property.</span></span>
<span data-ttu-id="ab9e4-120">`value` 属性的值必须是数字。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-120">The value of the `value` property MUST be a number.</span></span>

<span data-ttu-id="ab9e4-121">如果某个数量对象具有 `lower` 和 `upper` 其 `units` 属性之外的属性，则它是一个_受限的数量对象_。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-121">A quantity object is a _bounded quantity object_ if it has the properties `lower` and `upper` in addition to its `units` property.</span></span>
<span data-ttu-id="ab9e4-122">`lower` 和 `upper` 属性的值必须是数字。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-122">The values of the `lower` and `upper` properties MUST be numbers.</span></span>
<span data-ttu-id="ab9e4-123">绑定的数量对象可以有属性 `value` 其值为数值。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-123">A bounded quantity object MAY have a property `value` whose value is a number.</span></span>

<span data-ttu-id="ab9e4-124">如果某个数量对象具有属性 `format` 并且属性 `values` 除其 `units` 属性以外，则它是一个_稀疏数组的数量对象_。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-124">A quantity object is a _sparse array quantity object_ if it has the property `format` and a property `values` in addition to its `units` property.</span></span>
<span data-ttu-id="ab9e4-125">`format` 的值必须是 `sparse`的字符串。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-125">The value of `format` MUST be the string `sparse`.</span></span>
<span data-ttu-id="ab9e4-126">`values` 属性的值必须是一个数组。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-126">The value of the `values` property MUST be an array.</span></span>
<span data-ttu-id="ab9e4-127">`values` 的每个元素必须是一个数组，该数组表示稀疏数组数量的索引和值。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-127">Each element of `values` MUST be an array representing the indices and value of the sparse array quantity.</span></span>

<span data-ttu-id="ab9e4-128">稀疏数组数量对象的每个元素的索引必须在整个稀疏数组数量对象中是唯一的。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-128">The indices for each element of a sparse array quantity object MUST be unique across the entire sparse array quantity object.</span></span>
<span data-ttu-id="ab9e4-129">如果存在值为 `0`的索引，则分析器必须将稀疏数组的数量对象视为稀疏数组数量对象，而该对象的索引根本就不存在。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-129">If an index is present with a value of `0`, a parser MUST treat the sparse array quantity object identically to a sparse array quantity object in which that index is not present at all.</span></span>


<span data-ttu-id="ab9e4-130">数量对象必须是</span><span class="sxs-lookup"><span data-stu-id="ab9e4-130">A quantity object MUST either be</span></span>

- <span data-ttu-id="ab9e4-131">简单数量对象，</span><span class="sxs-lookup"><span data-stu-id="ab9e4-131">a simple quantity object,</span></span>
- <span data-ttu-id="ab9e4-132">一个有限数量对象，或</span><span class="sxs-lookup"><span data-stu-id="ab9e4-132">a bounded quantity object, or</span></span>
- <span data-ttu-id="ab9e4-133">稀疏数组数量对象。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-133">a sparse array quantity object.</span></span>


### <a name="examples"></a><span data-ttu-id="ab9e4-134">示例</span><span class="sxs-lookup"><span data-stu-id="ab9e4-134">Examples</span></span> ###

<span data-ttu-id="ab9e4-135">本部分介绍信息。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-135">This section is informative.</span></span>

<span data-ttu-id="ab9e4-136">表示 $ 1.9844146837\,\mathrm{Ha} $：</span><span class="sxs-lookup"><span data-stu-id="ab9e4-136">A simple quantity representing $1.9844146837\,\mathrm{Ha}$:</span></span>

```yaml
coulomb_repulsion:
    value: 1.9844146837
    units: hartree
```

<span data-ttu-id="ab9e4-137">表示按间隔 $ [-7，-6]\,\mathrm{Ha} $：</span><span class="sxs-lookup"><span data-stu-id="ab9e4-137">A bounded quantity representing a uniform distribution over the interval $[-7, -6]\,\mathrm{Ha}$:</span></span>

```yaml
fci_energy:
    upper: -6
    lower: -7
    units: hartree
```

<span data-ttu-id="ab9e4-138">下面是一个稀疏数组的数量，其元素 `[1, 2]` 等于 `hello` 并 `[3, 4]` 等于 `world`：</span><span class="sxs-lookup"><span data-stu-id="ab9e4-138">The following is a sparse array quantity with an element `[1, 2]` equal to `hello` and an element `[3, 4]` equal to `world`:</span></span>

```yaml
sparse_example:
    format: sparse
    units: hartree
    values:
    - [1, 2, "hello"]
    - [3, 4, "world"]
```

## <a name="format-section"></a><span data-ttu-id="ab9e4-139">格式部分</span><span class="sxs-lookup"><span data-stu-id="ab9e4-139">Format Section</span></span> ##

<span data-ttu-id="ab9e4-140">本部分进行了规范。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-140">This section is normative.</span></span>

<span data-ttu-id="ab9e4-141">Broombridge 对象必须具有属性 `format` 其值是一个具有名为 `version`的属性的 JSON 对象。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-141">The Broombridge object MUST have a property `format` whose value is a JSON object with one property called `version`.</span></span>
<span data-ttu-id="ab9e4-142">`version` 属性的值必须为 `"0.1"`。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-142">The `version` property MUST have the value `"0.1"`.</span></span>

### <a name="example"></a><span data-ttu-id="ab9e4-143">示例</span><span class="sxs-lookup"><span data-stu-id="ab9e4-143">Example</span></span> ###

<span data-ttu-id="ab9e4-144">本部分介绍信息。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-144">This section is informative.</span></span>

```yaml
format:                        # required
    version: "0.1"             # must match exactly
```

## <a name="integral-sets-section"></a><span data-ttu-id="ab9e4-145">整数集部分</span><span class="sxs-lookup"><span data-stu-id="ab9e4-145">Integral Sets Section</span></span> ##

<span data-ttu-id="ab9e4-146">本部分进行了规范。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-146">This section is normative.</span></span>

<span data-ttu-id="ab9e4-147">Broombridge 对象必须具有属性 `integral_sets` 其值为 JSON 数组。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-147">The Broombridge object MUST have a property `integral_sets` whose value is a JSON array.</span></span>
<span data-ttu-id="ab9e4-148">`integral_sets` 属性的值中的每一项必须是描述一组整型的 JSON 对象，如本部分的其余部分所述。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-148">Each item in the value of the `integral_sets` property MUST be a JSON object describing one set of integrals, as described in the remainder of this section.</span></span>
<span data-ttu-id="ab9e4-149">在此部分的剩余部分中，术语 "整数集对象" 将引用 Broombridge 对象的 `integral_sets` 属性值中的项。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-149">In the remainder of this section, the term "integral set object" will refer to an item in the value of the `integral_sets` property of the Broombridge object.</span></span>

<span data-ttu-id="ab9e4-150">每个整型集对象都必须具有属性 `metadata` 其值为 JSON 对象。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-150">Each integral set object MUST have a property `metadata` whose value is a JSON object.</span></span>
<span data-ttu-id="ab9e4-151">`metadata` 的值可以是空的 JSON 对象（即 `{}`），也可以包含实现器定义的其他属性。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-151">The value of `metadata` MAY be the empty JSON object (that is, `{}`), or MAY contain additional properties defined by the implementor.</span></span>

### <a name="hamiltonian-section"></a><span data-ttu-id="ab9e4-152">Hamiltonian 部分</span><span class="sxs-lookup"><span data-stu-id="ab9e4-152">Hamiltonian Section</span></span> ###

#### <a name="overview"></a><span data-ttu-id="ab9e4-153">概述</span><span class="sxs-lookup"><span data-stu-id="ab9e4-153">Overview</span></span> ####

<span data-ttu-id="ab9e4-154">本部分介绍信息。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-154">This section is informative.</span></span>

<span data-ttu-id="ab9e4-155">每个整型集对象的 `hamiltonian` 属性通过将其一个和两个正文术语作为实数组的稀疏数组列出，为特定的量程化学问题描述 Hamiltonian。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-155">The `hamiltonian` property of each integral set object describes the Hamiltonian for a particular quantum chemistry problem by listing out its one- and two-body terms as sparse arrays of real numbers.</span></span>
<span data-ttu-id="ab9e4-156">每个整数集对象所描述的 Hamiltonian 运算符采用形式</span><span class="sxs-lookup"><span data-stu-id="ab9e4-156">The Hamiltonian operators described by each integral set object take the form</span></span>

<span data-ttu-id="ab9e4-157">$ $ H = \sum\_\{i，j\}\sum\_{\sigma\in\\{\uparrow，\downarrow\\}} H\_\{ij\} ^\{\dagger\}\_，\sigma} a\_{j，\sigma} + \frac{1}{2}\sum\_\{i，j，k，l\}\sum\_{\sigma，\rho\in\\{\uparrow，\downarrow\\}} h\_{ijkl} a ^ \dagger\_{i，\sigma} 为 ^ \dagger\_{k，\rho}\_{l，\rho} a\_{j，\sigma}，$ $</span><span class="sxs-lookup"><span data-stu-id="ab9e4-157">$$ H = \sum\_\{i,j\}\sum\_{\sigma\in\\{\uparrow,\downarrow\\}} h\_\{ij\} a^\{\dagger\}\_{i,\sigma} a\_{j,\sigma} + \frac{1}{2}\sum\_\{i,j,k,l\}\sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}} h\_{ijkl} a^\dagger\_{i,\sigma} a^\dagger\_{k,\rho} a\_{l,\rho} a\_{j,\sigma}, $$</span></span>

<span data-ttu-id="ab9e4-158">此处 $h _ {ijkl} = （ij | kl） $ in Mulliken 约定。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-158">here $h_{ijkl}= (ij|kl)$ in Mulliken convention.</span></span>

<span data-ttu-id="ab9e4-159">为清楚起见，electron 术语是</span><span class="sxs-lookup"><span data-stu-id="ab9e4-159">For clarity, the one-electron term is</span></span>

<span data-ttu-id="ab9e4-160">$ $ h_ {ij} = \int {\mathrm d} x \psi ^ \*\_i （x） \left （\frac{1}{2}\nabla ^ 2 + \sum\_{A} \frac{Z\_\right） \psi\_j （x），$ $</span><span class="sxs-lookup"><span data-stu-id="ab9e4-160">$$ h_{ij} = \int {\mathrm d}x \psi^\*\_i(x) \left(\frac{1}{2}\nabla^2 + \sum\_{A}\frac{Z\_A}{|x-x\_A|}  \right) \psi\_j(x), $$</span></span>

<span data-ttu-id="ab9e4-161">electron 术语是</span><span class="sxs-lookup"><span data-stu-id="ab9e4-161">and the two-electron term is</span></span>

<span data-ttu-id="ab9e4-162">$ $ h\_\{ijkl\} = \iint \{\mathrm d\}x ^ 2 \psi ^\{\*\}\_i （x\_1） \psi\_j （x\_1） \frac\{1\}\{\|x\_1-x\_\|\}\_\psi\{k ^ \*\}\_（x\_2） \psi\_l （x 2）。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-162">$$ h\_\{ijkl\} = \iint \{\mathrm d\}x^2 \psi^\{\*\}\_i(x\_1)\psi\_j(x\_1) \frac\{1\}\{\|x\_1 -x\_2\|\}\psi\_k^\{\*\}(x\_2) \psi\_l(x\_2).</span></span>
$$

<span data-ttu-id="ab9e4-163">如我们在 `integral_sets` 属性的每个元素的[`basis_set` 属性](#basis-set-object)说明中所述，我们会进一步明确假设所使用的基本函数是真实的。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-163">As noted in our description of the [`basis_set` property](#basis-set-object) of each element of the `integral_sets` property, we further explicitly assume that the basis functions used are real-valued.</span></span>
<span data-ttu-id="ab9e4-164">这样，我们就可以在术语间使用以下 symmetries 来压缩 Hamiltonian 的表示形式。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-164">This allows us to use the following symmetries between the terms to compress the representation of the Hamiltonian.</span></span>

<span data-ttu-id="ab9e4-165">$ $ h_ {ijkl} = h_ {ijlk} = h_ {jikl} = h_ {jilk} = h_ {klij} = h_ {klji} = h_ {lkij} = h_ {lkji}。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-165">$$ h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkij}=h_{lkji}.</span></span>
$$


#### <a name="contents"></a><span data-ttu-id="ab9e4-166">内容</span><span class="sxs-lookup"><span data-stu-id="ab9e4-166">Contents</span></span> ####

<span data-ttu-id="ab9e4-167">本部分进行了规范。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-167">This section is normative.</span></span>

<span data-ttu-id="ab9e4-168">每个整数集都必须具有属性 `hamiltonian` 其值为 JSON 对象。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-168">Each integral set MUST have a property `hamiltonian` whose value is a JSON object.</span></span>
<span data-ttu-id="ab9e4-169">`hamiltonian` 属性的值称为 Hamiltonian 对象，并且必须具有此部分的其余部分所述的属性 `one_electron_integrals` 和 `two_electron_integrals`。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-169">The value of the `hamiltonian` property is known as a Hamiltonian object, and MUST have the properties `one_electron_integrals` and `two_electron_integrals` as described in the remainder of this section.</span></span>
<span data-ttu-id="ab9e4-170">Hamiltonian 对象还可能具有 `particle_hole_representation`的属性。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-170">A Hamiltonian object MAY also have a property `particle_hole_representation`.</span></span>
<span data-ttu-id="ab9e4-171">如果存在，则 `particle_hole_representation` 的值必须遵循本部分剩余部分所述的格式。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-171">If present, the value of `particle_hole_representation` MUST follow the format described in the remainder of this section.</span></span>

##### <a name="one-electron-integrals-object"></a><span data-ttu-id="ab9e4-172">Electron 整型对象</span><span class="sxs-lookup"><span data-stu-id="ab9e4-172">One-Electron Integrals Object</span></span> #####

<span data-ttu-id="ab9e4-173">本部分进行了规范。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-173">This section is normative.</span></span>

<span data-ttu-id="ab9e4-174">Hamiltonian 对象的 `one_electron_integrals` 属性必须是一个稀疏数组数量，其索引为两个整数，其值为数值。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-174">The `one_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity whose indices are two integers and whose values are numbers.</span></span>
<span data-ttu-id="ab9e4-175">每个术语的索引 `[i, j]` 都必须是 `i >= j`。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-175">Every term MUST have indices `[i, j]` where `i >= j`.</span></span>

> <span data-ttu-id="ab9e4-176">纪录这反映了 $h _ {ij} = h_ {ji} $ 这一事实的对称，这是 Hamiltonian Hermitian 的结果。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-176">[NOTE] This reflects the symmetry that $h_{ij} = h_{ji}$ which is a consequence of the fact that the Hamiltonian is Hermitian.</span></span>


###### <a name="example"></a><span data-ttu-id="ab9e4-177">示例</span><span class="sxs-lookup"><span data-stu-id="ab9e4-177">Example</span></span> ######

<span data-ttu-id="ab9e4-178">本部分介绍信息。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-178">This section is informative.</span></span>

<span data-ttu-id="ab9e4-179">以下稀疏数组数量表示 Hamiltonian $ $ H = \left （-5.0 （a ^\{\dagger\}\_{1，\uparrow} a\_{1，\uparrow} + a ^\{\dagger\}\_{1，\downarrow}\_{1，\downarrow}） + 0.17 （a ^\{\dagger\}\_{2，\uparrow}\_{1，\uparrow} + a ^\{\dagger\}\_{1，\uparrow} a\_{2，\uparrow} + a ^\{\dagger\}\_{2，\downarrow} a\_{1，\downarrow} + a ^\{\dagger\}\_{1，\downarrow} a\_{2，\downarrow}） \right）\\，\mathrm{Ha}。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-179">The following sparse array quantity represents the Hamiltonian $$ H = \left(-5.0  (a^\{\dagger\}\_{1,\uparrow} a\_{1,\uparrow}+a^\{\dagger\}\_{1,\downarrow} a\_{1,\downarrow})+ 0.17 (a^\{\dagger\}\_{2,\uparrow} a\_{1,\uparrow}+ a^\{\dagger\}\_{1,\uparrow} a\_{2,\uparrow}+a^\{\dagger\}\_{2,\downarrow} a\_{1,\downarrow}+ a^\{\dagger\}\_{1,\downarrow} a\_{2,\downarrow})\right)\\,\mathrm{Ha}.</span></span>
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
> <span data-ttu-id="ab9e4-180">Broombridge 使用基于1的索引。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-180">Broombridge uses 1-based indexing.</span></span>


##### <a name="two-electron-integrals-object"></a><span data-ttu-id="ab9e4-181">Electron 整型对象</span><span class="sxs-lookup"><span data-stu-id="ab9e4-181">Two-Electron Integrals Object</span></span> #####

<span data-ttu-id="ab9e4-182">本部分进行了规范。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-182">This section is normative.</span></span>

<span data-ttu-id="ab9e4-183">Hamiltonian 对象的 `two_electron_integrals` 属性必须是具有一个名为 `index_convention`的附加属性的稀疏数组量。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-183">The `two_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity with one additional property called `index_convention`.</span></span>
<span data-ttu-id="ab9e4-184">`two_electron_integrals` 的值的每个元素必须具有四个索引。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-184">Each element of the value of `two_electron_integrals` MUST have four indices.</span></span>

<span data-ttu-id="ab9e4-185">每个 `two_electron_integrals` 属性都必须具有 `index_convention` 属性。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-185">Each `two_electron_integrals` property MUST have a `index_convention` property.</span></span>
<span data-ttu-id="ab9e4-186">`index_convention` 属性的值必须是表1中列出的允许值之一。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-186">The value of the `index_convention` property MUST be one of the allowed values listed in Table 1.</span></span>
<span data-ttu-id="ab9e4-187">如果 `mulliken``index_convention` 的值，则对于 `two_electron_integrals` 稀疏数组数量的每个元素，加载 Broombridge 文档的分析器必须实例化一个 Hamiltonian 术语，使其等于双 electron 运算符 $h _ {i，j，k，l} a ^ \dagger_i a ^ \dagger_j a_k $，其中 $i $、$j $、$k $ 和 $l $ 必须是从1到整数集对象的 `n_electrons` 属性指定的电子数之间的整数，其中 $h _ {i，j，k，l} $ 是稀疏数组数量的元素 `[i, j, k, l, h(i, j, k, l)]`。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-187">If the value of `index_convention` is `mulliken`, then for each element of the `two_electron_integrals` sparse array quantity, a parser loading a Broombridge document MUST instantiate a Hamiltonian term equal to the two-electron operator $h_{i, j, k, l} a^\dagger_i a^\dagger_j a_k a_l$, where $i$, $j$, $k$, and $l$ MUST be integers in the inclusive range from 1 to the number of electrons specified by the `n_electrons` property of the integral set object, and where $h_{i, j, k, l}$ is the element `[i, j, k, l, h(i, j, k, l)]` of the sparse array quantity.</span></span>

###### <a name="symmetries"></a><span data-ttu-id="ab9e4-188">Symmetries</span><span class="sxs-lookup"><span data-stu-id="ab9e4-188">Symmetries</span></span> ######

<span data-ttu-id="ab9e4-189">本部分进行了规范。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-189">This section is normative.</span></span>

<span data-ttu-id="ab9e4-190">如果 `two_electron_integrals` 对象的 `index_convention` 属性等于 `mulliken`，则如果存在包含索引 `[i, j, k, l]` 的元素，则不能存在以下索引，除非它们等于 `[i, j, k, l]`：</span><span class="sxs-lookup"><span data-stu-id="ab9e4-190">If the `index_convention` property of a `two_electron_integrals` object is equal to `mulliken`, then if an element with indices `[i, j, k, l]` is present, the following indices MUST NOT be present unless they are equal to `[i, j, k, l]`:</span></span>

- `[i, j, l, k]`
- `[j, i, k, l]`
- `[j, i, l, k]`
- `[k, l, i, j]`
- `[k, l, j, i]`
- `[l, k, j, i]`

> [!NOTE]
> <span data-ttu-id="ab9e4-191">由于 `index_convention` 属性是稀疏数量对象，因此不能在不同元素上重复任何索引。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-191">Because the `index_convention` property is a sparse quantity object, no indices may be repeated on different elements.</span></span>
> <span data-ttu-id="ab9e4-192">特别是，如果存在索引 `[i, j, k, l]` 的元素，则其他元素不能具有这些索引。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-192">In particular, if an element with indices `[i, j, k, l]` is present, no other element may have those indices.</span></span>


<!-- h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkji}. -->

###### <a name="example"></a><span data-ttu-id="ab9e4-193">示例</span><span class="sxs-lookup"><span data-stu-id="ab9e4-193">Example</span></span> #######

<span data-ttu-id="ab9e4-194">本部分介绍信息。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-194">This section is informative.</span></span>

<span data-ttu-id="ab9e4-195">以下对象指定 Hamiltonian</span><span class="sxs-lookup"><span data-stu-id="ab9e4-195">The following object specifies the Hamiltonian</span></span>

<span data-ttu-id="ab9e4-196">$ $ H = \frac12 \sum\_{\sigma，\rho\in\\{\uparrow，\downarrow\\}} \Biggr （1.6 a ^ {\dagger}\_{1，\sigma} a ^ {\dagger}\_{1，\rho} a\_{1，\rho} a\_{1，\sigma}-0.1 a ^ {\dagger}\_{6，\sigma} 为 ^ {\dagger}\_{1，\rho} a\_{3，\rho} a\_{2，\sigma}-0.1 a ^ {\dagger}\_{6，\sigma} a ^ {\dagger}\_{1，\rho} a\_{2，\rho}\_，\sigma}-0.1 a ^ {\dagger}\_{1，\sigma}，^ {\dagger}\_{6，\rho} a\_{3，\rho} a\_{2，\sigma}-0.1 a ^ {\dagger}\_{1，\sigma} a ^ {\dagger}\_{6，\rho} a\_{2，\rho} a\_{3，\sigma} $ $ $-0.1 a ^ {\dagger}\_{3，\sigma} a ^ {\dagger}\_{2，\rho} a\_{6，\rho} a\_{1，\sigma}-0.1 a ^ {\dagger}\_{2，\rho} a\_{1，\rho} a\_{6，\sigma}-0.1 a ^ {\dagger}\_{2，\sigma} a ^ {\dagger}\_{3，\rho} a\_{6，\rho} a\_{1，\sigma}-0.1 a ^ {\dagger}\_{2，\sigma} 为 ^ {\dagger}\_{3，\rho} a\_{1，\rho} a\_{6，\sigma}\Biggr）\\，\textrm{Ha}。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-196">$$ H = \frac12 \sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}}\Biggr( 1.6 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{1,\rho} a\_{1,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{2,\rho} a\_{3,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{2,\rho} a\_{3,\sigma} $$ $$- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{1,\rho} a\_{6,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{1,\rho} a\_{6,\sigma}\Biggr)\\,\textrm{Ha}.</span></span>
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

##### <a name="particlehole-representation-object"></a><span data-ttu-id="ab9e4-197">粒子–洞表示对象</span><span class="sxs-lookup"><span data-stu-id="ab9e4-197">Particle–Hole Representation Object</span></span> #####

<span data-ttu-id="ab9e4-198">本部分进行了规范。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-198">This section is normative.</span></span>

<span data-ttu-id="ab9e4-199">"粒子-孔表示" 对象指定存储的 "整型" 的定义与 "粒子" 孔表示形式相关，其中，"创建" 和 "annihilation" 运算符从所用的引用状态（如 Hartree）中描述了 excitations。Fock 状态。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-199">The particle–hole representation object specifies that the integrals stored are defined with respect to particle hole representation wherein the creation and annihilation operators describe excitations away from the reference state used, such as a Hartree–Fock state.</span></span>
<span data-ttu-id="ab9e4-200">对象是可选的。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-200">The object is OPTIONAL.</span></span>
<span data-ttu-id="ab9e4-201">如果未指定对象，则在粒子孔表示形式中，Hamiltonian 将被解释为 not 给定的。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-201">If the object is not specified then the Hamiltonian is to be interpreted as not given in particle-hole representation.</span></span>
<span data-ttu-id="ab9e4-202">如果存在，则 `particle_hole_representation` 的值必须是一个稀疏数组数量对象，其索引为四个整数，其值为数字和字符串。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-202">If present, the value of `particle_hole_representation` MUST be a sparse array quantity object whose indices are four integers, and whose values are a number and a string.</span></span>
<span data-ttu-id="ab9e4-203">每个元素的值的字符串部分必须仅包含 `'+'` 和 `'-'` 的字符，该字符指定字词中的给定因子是在粒子–洞表示中是创建还是 annihilation 运算符。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-203">The string portion of the value of each element MUST contain only the characters `'+'` and `'-'` which specifies whether a given factor in the term is a creation or annihilation operator in the particle–hole representation.</span></span>  <span data-ttu-id="ab9e4-204">例如 `"-+++"` 与到在站点上创建的洞 $i $ 和在站点 $j 上创建的粒子，k $ 和 $l $。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-204">For example `"-+++"` coresponds to a hole being created at site $i$ and particles being created at sites $j,k$ and $l$.</span></span>

> [!NOTE]
> <span data-ttu-id="ab9e4-205">因为 `particle_hole_representation` 的值是稀疏数组的数量对象，所以必须指定 `unit` 和 `format` 属性。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-205">As the value of the `particle_hole_representation` is a sparse array quantity object, the `unit` and `format` properties must be specified.</span></span>
> <span data-ttu-id="ab9e4-206">表1中列出了可接受的单位。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-206">Acceptable units include are listed in Table 1.</span></span>
> <span data-ttu-id="ab9e4-207">`format` 属性是必需的，指示是否将 Hamiltonian 系数指定为密集数组或稀疏数组。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-207">The `format` property is required, and indicates whether the Hamiltonian coefficients are specified as a dense or sparse array.</span></span>
> <span data-ttu-id="ab9e4-208">在当前版本中，仅支持稀疏数组，并解释所有未指定的元素为 $0 $，但将来的版本可能会添加对 `format` 属性的其他值的支持。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-208">In the current version, only sparse arrays are supported, with interpretation that all unspecified elements are $0$, but future versions may add support for additional values of the `format` property.</span></span>

### <a name="initial-state-section"></a><span data-ttu-id="ab9e4-209">初始状态部分</span><span class="sxs-lookup"><span data-stu-id="ab9e4-209">Initial State Section</span></span> ###

<span data-ttu-id="ab9e4-210">Initial_state_suggestion 对象指定对指定的 Hamiltonian 感兴趣的初始量程状态。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-210">The initial_state_suggestion object specifies initial quantum states of interest to the specified Hamiltonian.</span></span> <span data-ttu-id="ab9e4-211">此对象必须是 JSON `state` 对象的数组。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-211">This object must be an array of JSON `state` objects.</span></span>

#### <a name="state-object"></a><span data-ttu-id="ab9e4-212">状态对象</span><span class="sxs-lookup"><span data-stu-id="ab9e4-212">State object</span></span> ####

<span data-ttu-id="ab9e4-213">每个状态都表示 superposition 的 orbitals。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-213">Each states represents a superposition of occupied orbitals.</span></span> <span data-ttu-id="ab9e4-214">每个状态对象都必须具有一个包含字符串的 `label` 属性。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-214">Each state object MUST have a `label` property containing a string.</span></span> <span data-ttu-id="ab9e4-215">每个状态对象都必须具有一个 `superposition` 属性，该属性包含一个基本状态数组及其非规范化 amplitudes。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-215">Each state object MUST have a `superposition` property containing an array of basis states and their unnormalized amplitudes.</span></span>

<span data-ttu-id="ab9e4-216">例如，初始状态 $ $ \ket{G0} = \ket{G1} = \ket{G2} = （^ {\dagger}\_{1，\uparrow}a ^ {\dagger}\_{2，\uparrow}a ^ {\dagger}\_{2，\downarrow}） \ket{0} $ $ $ $ \ket{E} = \frac{0.1 （^ {\dagger}\_{1，\uparrow}a ^ {\dagger}\_{2，\uparrow}a ^ {\dagger}\_{2，\downarrow}） + 0.2 （a ^ {\dagger}\_{1，\uparrow}a ^ {\_\dagger}\_{2，\uparrow}a）} {\dagger} | 0.1 | ^ 2 + | 0.2 | ^ 2}} \downarrow}{0} $ $表示的</span><span class="sxs-lookup"><span data-stu-id="ab9e4-216">For example, the initial states $$ \ket{G0}=\ket{G1}=\ket{G2}=(a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})\ket{0} $$ $$ \ket{E}=\frac{0.1 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})+0.2 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{3,\uparrow}a^{\dagger}\_{2,\downarrow})}{\sqrt{|0.1|^2+|0.2|^2}}\ket{0} $$ are represented by</span></span>
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

#### <a name="basis-set-object"></a><span data-ttu-id="ab9e4-217">Basis 集对象</span><span class="sxs-lookup"><span data-stu-id="ab9e4-217">Basis Set Object</span></span> ####

<span data-ttu-id="ab9e4-218">本部分进行了规范。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-218">This section is normative.</span></span>

<span data-ttu-id="ab9e4-219">每个整型集对象都有一个 `basis_set` 属性。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-219">Each integral set object MAY have a `basis_set` property.</span></span>
<span data-ttu-id="ab9e4-220">如果存在，则 `basis_set` 属性的值必须是具有两个属性的对象 `type` 和 `name`。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-220">If present, the value of the `basis_set` property MUST be an object with two properties, `type` and `name`.</span></span>

<span data-ttu-id="ab9e4-221">`basis_set` 属性的值所标识的基本函数必须是实际值。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-221">The basis functions identified by the value of the `basis_set` property MUST be real-valued.</span></span>

> [!NOTE]
> <span data-ttu-id="ab9e4-222">在此规范的未来版本中，假设所有基础函数都是真实的。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-222">The assumption that all basis functions are real-valued may be relaxed in future versions of this specification.</span></span>

## <a name="tables-and-lists"></a><span data-ttu-id="ab9e4-223">表和列表</span><span class="sxs-lookup"><span data-stu-id="ab9e4-223">Tables and Lists</span></span> ##

### <a name="table-1-allowed-physical-units"></a><span data-ttu-id="ab9e4-224">表 1.</span><span class="sxs-lookup"><span data-stu-id="ab9e4-224">Table 1.</span></span> <span data-ttu-id="ab9e4-225">允许的物理单元</span><span class="sxs-lookup"><span data-stu-id="ab9e4-225">Allowed Physical Units</span></span> ###

<span data-ttu-id="ab9e4-226">本部分进行了规范。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-226">This section is normative.</span></span>

<span data-ttu-id="ab9e4-227">指定单位的任何字符串都必须是下列各项之一：</span><span class="sxs-lookup"><span data-stu-id="ab9e4-227">Any string specifying a unit MUST be one of the following:</span></span>

- `hartree`
- `ev`

<span data-ttu-id="ab9e4-228">分析器和生成方必须将以下简单数量对象视为等效：</span><span class="sxs-lookup"><span data-stu-id="ab9e4-228">Parsers and producers MUST treat the following simple quantity objects as equivalent:</span></span>

```yaml
- {"units": "hartree", "value": 1}
- {"units": "ev", "value": 27.2113831301723}
```

### <a name="table-2-allowed-index-conventions"></a><span data-ttu-id="ab9e4-229">表2：</span><span class="sxs-lookup"><span data-stu-id="ab9e4-229">Table 2.</span></span> <span data-ttu-id="ab9e4-230">允许的索引约定</span><span class="sxs-lookup"><span data-stu-id="ab9e4-230">Allowed Index Conventions</span></span> ###

<span data-ttu-id="ab9e4-231">本部分进行了规范。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-231">This section is normative.</span></span>

<span data-ttu-id="ab9e4-232">指定索引约定的任何字符串都必须是下列各项之一：</span><span class="sxs-lookup"><span data-stu-id="ab9e4-232">Any string specifying an index convention MUST be one of the following:</span></span>

- `mulliken`

<span data-ttu-id="ab9e4-233">本部分介绍信息。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-233">This section is informative.</span></span>

<span data-ttu-id="ab9e4-234">此规范的未来版本中可能会引入其他索引约定。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-234">Additional index conventions may be introduced in future versions of this specification.</span></span>

#### <a name="interpretation-of-index-conventions"></a><span data-ttu-id="ab9e4-235">索引约定的解释</span><span class="sxs-lookup"><span data-stu-id="ab9e4-235">Interpretation of Index Conventions</span></span> ####

<span data-ttu-id="ab9e4-236">本部分介绍信息。</span><span class="sxs-lookup"><span data-stu-id="ab9e4-236">This section is informative.</span></span>
