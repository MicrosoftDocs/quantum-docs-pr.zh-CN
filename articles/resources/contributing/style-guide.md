---
title: 'Microsoft Q # 样式指南'
description: '了解 Q # 程序和库的命名、输入、文档和格式设置约定。'
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.style
ms.openlocfilehash: f8e398b5c9932a5079222fed7ad20e54de814eb8
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274370"
---
# <a name="q-style-guide"></a><span data-ttu-id="fc860-103">Q # 样式指南</span><span class="sxs-lookup"><span data-stu-id="fc860-103">Q# Style Guide</span></span> #
## <a name="general-conventions"></a><span data-ttu-id="fc860-104">一般约定</span><span class="sxs-lookup"><span data-stu-id="fc860-104">General Conventions</span></span> ##

<span data-ttu-id="fc860-105">本指南中建议的约定旨在帮助以 Q # 编写编写的程序和库更易于阅读和理解。</span><span class="sxs-lookup"><span data-stu-id="fc860-105">The conventions suggested in this guide are intended to help make programs and libraries written in Q# easier to read and understand.</span></span>

## <a name="guidance"></a><span data-ttu-id="fc860-106">指南</span><span class="sxs-lookup"><span data-stu-id="fc860-106">Guidance</span></span>

<span data-ttu-id="fc860-107">建议：</span><span class="sxs-lookup"><span data-stu-id="fc860-107">We suggest:</span></span>

- <span data-ttu-id="fc860-108">永远不要忽略约定，除非你有意这样做，以便为用户提供更具可读性且更易理解的代码。</span><span class="sxs-lookup"><span data-stu-id="fc860-108">Never disregard a convention unless you’re doing so intentionally in order to provide more readable and understandable code for your users.</span></span>

## <a name="naming-conventions"></a><span data-ttu-id="fc860-109">命名约定</span><span class="sxs-lookup"><span data-stu-id="fc860-109">Naming Conventions</span></span> ##

<span data-ttu-id="fc860-110">在提供量子开发工具包时，我们努力实现函数和操作名称，这些名称有助于量子开发人员编写易于阅读的程序，并最大程度地减少意外情况。</span><span class="sxs-lookup"><span data-stu-id="fc860-110">In offering the Quantum Development Kit, we strive for function and operation names that help quantum developers write programs that are easy to read and that minimize surprise.</span></span>
<span data-ttu-id="fc860-111">这种情况的一个重要部分是，当我们为函数、操作和类型选择名称时，我们将建立编程人员用来表示量程概念的*词汇*;利用我们的选择，我们可以在很大程度上帮助或阻止他们进行清晰的沟通。</span><span class="sxs-lookup"><span data-stu-id="fc860-111">An important part of that is that when we choose names for functions, operations, and types, we are establishing the *vocabulary* that programmers use to express quantum concepts; with our choices, we either help or hinder them in their effort to clearly communicate.</span></span>
<span data-ttu-id="fc860-112">这会给我们带来责任，以确保我们引入的名称更清晰，而不是隐匿性。</span><span class="sxs-lookup"><span data-stu-id="fc860-112">This places a responsibility on us to make sure that the names we introduce offer clarity rather than obscurity.</span></span>
<span data-ttu-id="fc860-113">在本部分中，我们将详细说明我们如何在明确指导下实现这一义务，帮助我们通过 Q # 开发社区获得最佳帮助。</span><span class="sxs-lookup"><span data-stu-id="fc860-113">In this section, we detail how we meet this obligation in terms of explicit guidance that helps us do the best by the Q# development community.</span></span>

### <a name="operations-and-functions"></a><span data-ttu-id="fc860-114">操作和函数</span><span class="sxs-lookup"><span data-stu-id="fc860-114">Operations and Functions</span></span> ###

<span data-ttu-id="fc860-115">名称应建立的首要任务之一就是给定的符号表示函数还是操作。</span><span class="sxs-lookup"><span data-stu-id="fc860-115">One of the first things that a name should establish is whether a given symbol represents a function or an operation.</span></span>
<span data-ttu-id="fc860-116">函数和操作之间的区别对于理解代码块的行为方式至关重要。</span><span class="sxs-lookup"><span data-stu-id="fc860-116">The difference between functions and operations is critical to understanding how a block of code behaves.</span></span>
<span data-ttu-id="fc860-117">为了向用户传达函数和操作之间的区别，我们依赖于该 Q # 模型，通过使用副作用来进行量程操作。</span><span class="sxs-lookup"><span data-stu-id="fc860-117">To communicate the distinction between functions and operations to users, we rely on that Q# models quantum operations through the use of side effects.</span></span>
<span data-ttu-id="fc860-118">也就是说，操作*执行*一些操作。</span><span class="sxs-lookup"><span data-stu-id="fc860-118">That is, an operation *does* something.</span></span>

<span data-ttu-id="fc860-119">与此相反，函数说明了数据之间的数学关系。</span><span class="sxs-lookup"><span data-stu-id="fc860-119">By contrast, functions describe the mathematical relationships between data.</span></span>
<span data-ttu-id="fc860-120">表达式 `Sin(PI() / 2.0)` *为* `1.0` ，而不表示程序或其 qubits 的状态。</span><span class="sxs-lookup"><span data-stu-id="fc860-120">The expression `Sin(PI() / 2.0)` *is* `1.0`, and implies nothing about the state of a program or its qubits.</span></span>

<span data-ttu-id="fc860-121">汇总是，操作在函数时执行操作。</span><span class="sxs-lookup"><span data-stu-id="fc860-121">Summarizing, operations do things while functions are things.</span></span>
<span data-ttu-id="fc860-122">这种区别意味着我们将操作命名为动词和函数作为名词。</span><span class="sxs-lookup"><span data-stu-id="fc860-122">This distinction suggests that we name operations as verbs and functions as nouns.</span></span>

> [!NOTE]
> <span data-ttu-id="fc860-123">声明用户定义类型时，将同时隐式定义用于构造该类型的实例的新函数。</span><span class="sxs-lookup"><span data-stu-id="fc860-123">When a user-defined type is declared, a new function that constructs instances of that type is implicitly defined at the same time.</span></span>
> <span data-ttu-id="fc860-124">从这个角度来看，用户定义类型应命名为名词，使类型本身和构造函数具有一致的名称。</span><span class="sxs-lookup"><span data-stu-id="fc860-124">From that perspective, user-defined types should be named as nouns so that both the type itself and the constructor function have consistent names.</span></span>

<span data-ttu-id="fc860-125">在合理的情况下，请确保操作名称以明确指示操作所使用的效果的动词开头。</span><span class="sxs-lookup"><span data-stu-id="fc860-125">Where reasonable, ensure that operation names begin with verbs that clearly indicate the effect taken by the operation.</span></span>
<span data-ttu-id="fc860-126">例如：</span><span class="sxs-lookup"><span data-stu-id="fc860-126">For example:</span></span>

- `MeasureInteger`
- `EstimateEnergy`
- `SampleInt`

<span data-ttu-id="fc860-127">值得特别提的一种情况是，操作采用另一操作作为输入并调用它。</span><span class="sxs-lookup"><span data-stu-id="fc860-127">One case that deserves special mention is when an operation takes another operation as input and calls it.</span></span>
<span data-ttu-id="fc860-128">在这种情况下，在定义外部操作时，输入操作执行的操作不会被清除，这样就不会立即清除正确的谓词。</span><span class="sxs-lookup"><span data-stu-id="fc860-128">In such cases, the action taken by the input operation is not clear when the outer operation is defined, such that the right verb is not immediately clear.</span></span>
<span data-ttu-id="fc860-129">建议谓词 `Apply` ，如 `ApplyIf` 、 `ApplyToEach` 和 `ApplyToFirst` 。</span><span class="sxs-lookup"><span data-stu-id="fc860-129">We recommend the verb `Apply`, as in `ApplyIf`, `ApplyToEach`, and `ApplyToFirst`.</span></span>
<span data-ttu-id="fc860-130">在这种情况下，其他谓词也可能有用，如中所示 `IterateThroughCartesianPower` 。</span><span class="sxs-lookup"><span data-stu-id="fc860-130">Other verbs may be useful in this case as well, as in `IterateThroughCartesianPower`.</span></span>

| <span data-ttu-id="fc860-131">Verb</span><span class="sxs-lookup"><span data-stu-id="fc860-131">Verb</span></span> | <span data-ttu-id="fc860-132">预期效果</span><span class="sxs-lookup"><span data-stu-id="fc860-132">Expected Effect</span></span> |
| ---- | ------ |
| <span data-ttu-id="fc860-133">应用</span><span class="sxs-lookup"><span data-stu-id="fc860-133">Apply</span></span> | <span data-ttu-id="fc860-134">作为输入提供的操作称为</span><span class="sxs-lookup"><span data-stu-id="fc860-134">An operation provided as input is called</span></span> |
| <span data-ttu-id="fc860-135">Assert</span><span class="sxs-lookup"><span data-stu-id="fc860-135">Assert</span></span> | <span data-ttu-id="fc860-136">模拟器检查可能的量程度量结果的假设</span><span class="sxs-lookup"><span data-stu-id="fc860-136">A hypothesis about the outcome of a possible quantum measurement is checked by a simulator</span></span> |
| <span data-ttu-id="fc860-137">估价</span><span class="sxs-lookup"><span data-stu-id="fc860-137">Estimate</span></span> | <span data-ttu-id="fc860-138">返回一个传统值，表示从一个或多个度量值中提取的估计值</span><span class="sxs-lookup"><span data-stu-id="fc860-138">A classical value is returned, representing an estimate drawn from one or more measurements</span></span> |
| <span data-ttu-id="fc860-139">度量</span><span class="sxs-lookup"><span data-stu-id="fc860-139">Measure</span></span> | <span data-ttu-id="fc860-140">将执行量程度量，并将其结果返回给用户</span><span class="sxs-lookup"><span data-stu-id="fc860-140">A quantum measurement is performed, and its result is returned to the user</span></span> |
| <span data-ttu-id="fc860-141">准备</span><span class="sxs-lookup"><span data-stu-id="fc860-141">Prepare</span></span> | <span data-ttu-id="fc860-142">给定的 qubits 寄存器初始化为特定状态</span><span class="sxs-lookup"><span data-stu-id="fc860-142">A given register of qubits is initialized into a particular state</span></span> |
| <span data-ttu-id="fc860-143">示例</span><span class="sxs-lookup"><span data-stu-id="fc860-143">Sample</span></span> | <span data-ttu-id="fc860-144">从某一分布中随机返回一个传统值</span><span class="sxs-lookup"><span data-stu-id="fc860-144">A classical value is returned at random from some distribution</span></span> |

<span data-ttu-id="fc860-145">对于函数，我们建议避免使用谓词来取代常用名词（请参阅下面正确名词的指导）或形容词：</span><span class="sxs-lookup"><span data-stu-id="fc860-145">For functions, we suggest avoiding the use of verbs in favor of common nouns (see guidance on proper nouns below) or adjectives:</span></span>

- `ConstantArray`
- `Head`
- `LookupFunction`

<span data-ttu-id="fc860-146">特别是，在几乎所有情况下，我们建议使用过去的 participles，以指示函数名称与量程程序中其他位置的操作或副作用强连接。</span><span class="sxs-lookup"><span data-stu-id="fc860-146">In particular, in almost all cases, we suggest using past participles where appropriate to indicate that a function name is strongly connected to an action or side effect elsewhere in a quantum program.</span></span>
<span data-ttu-id="fc860-147">例如， `ControlledOnInt` 使用谓词 "control" 的分词部分形式指示函数充当形容词来修改其参数。</span><span class="sxs-lookup"><span data-stu-id="fc860-147">For example,  `ControlledOnInt` uses the part participle form of the verb "control" to indicate that the function acts as an adjective to modify its argument.</span></span>
<span data-ttu-id="fc860-148">此名称具有与内置函子的语义相匹配的额外权益 `Controlled` ，如下面进一步所述。</span><span class="sxs-lookup"><span data-stu-id="fc860-148">This name has the additional benefit of matching the semantics of the built-in `Controlled` functor, as discussed further below.</span></span>
<span data-ttu-id="fc860-149">同样，可以使用_代理名词_构造操作名称中的函数和 UDT 名称，如 `Encoder` 与强关联的 UDT 的名称相同 `Encode` 。</span><span class="sxs-lookup"><span data-stu-id="fc860-149">Similarly, _agent nouns_ can be used to construct function and UDT names from operation names, as in the case of the name `Encoder` for a UDT that is strongly associated with `Encode`.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="fc860-150">指南</span><span class="sxs-lookup"><span data-stu-id="fc860-150">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="fc860-151">建议：</span><span class="sxs-lookup"><span data-stu-id="fc860-151">We suggest:</span></span>

- <span data-ttu-id="fc860-152">为操作名称使用谓词。</span><span class="sxs-lookup"><span data-stu-id="fc860-152">Use verbs for operation names.</span></span>
- <span data-ttu-id="fc860-153">使用名词或形容词作为函数名称。</span><span class="sxs-lookup"><span data-stu-id="fc860-153">Use nouns or adjectives for function names.</span></span>
- <span data-ttu-id="fc860-154">将名词用于用户定义的类型和属性。</span><span class="sxs-lookup"><span data-stu-id="fc860-154">Use nouns for user-defined types and attributes.</span></span>
- <span data-ttu-id="fc860-155">对于所有可调用名称，请 `CamelCase` 在、或中使用强首选项 `pascalCase` `snake_case` `ANGRY_CASE` 。</span><span class="sxs-lookup"><span data-stu-id="fc860-155">For all callable names, use `CamelCase` in strong preference to `pascalCase`, `snake_case`, or `ANGRY_CASE`.</span></span> <span data-ttu-id="fc860-156">具体而言，请确保可调用名称以大写字母开头。</span><span class="sxs-lookup"><span data-stu-id="fc860-156">In particular, ensure that callable names start with uppercase letters.</span></span>
- <span data-ttu-id="fc860-157">对于所有局部变量，请 `pascalCase` 在、或中使用强首选项 `CamelCase` `snake_case` `ANGRY_CASE` 。</span><span class="sxs-lookup"><span data-stu-id="fc860-157">For all local variables, use `pascalCase` in strong preference to `CamelCase`, `snake_case`, or `ANGRY_CASE`.</span></span> <span data-ttu-id="fc860-158">具体而言，请确保本地变量以小写字母开头。</span><span class="sxs-lookup"><span data-stu-id="fc860-158">In particular, ensure that local variables start with lowercase letters.</span></span>
- <span data-ttu-id="fc860-159">避免 `_` 在函数和操作名称中使用下划线; 需要其他级别的层次结构时，请使用命名空间和命名空间别名。</span><span class="sxs-lookup"><span data-stu-id="fc860-159">Avoid the use of underscores `_` in function and operation names; where additional levels of hierarchy are needed, use namespaces and namespace aliases.</span></span>

# <a name="examples"></a>[<span data-ttu-id="fc860-160">示例</span><span class="sxs-lookup"><span data-stu-id="fc860-160">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="fc860-161">“属性”</span><span class="sxs-lookup"><span data-stu-id="fc860-161">Name</span></span> | <span data-ttu-id="fc860-162">描述</span><span class="sxs-lookup"><span data-stu-id="fc860-162">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="fc860-163">☑</span><span class="sxs-lookup"><span data-stu-id="fc860-163">☑</span></span> | `operation ReflectAboutStart` | <span data-ttu-id="fc860-164">清除动词的使用（"反射"）以指示操作的效果。</span><span class="sxs-lookup"><span data-stu-id="fc860-164">Clear use of a verb ("reflect") to indicate the effect of the operation.</span></span> |
| <span data-ttu-id="fc860-165">☒</span><span class="sxs-lookup"><span data-stu-id="fc860-165">☒</span></span> | <s>`operation XRotation`</s> | <span data-ttu-id="fc860-166">使用名词短语建议函数，而不是操作。</span><span class="sxs-lookup"><span data-stu-id="fc860-166">Use of noun phrase suggests function, rather than operation.</span></span> |
| <span data-ttu-id="fc860-167">☒</span><span class="sxs-lookup"><span data-stu-id="fc860-167">☒</span></span> | <s>`operation search_oracle`</s> | <span data-ttu-id="fc860-168">使用 `snake_case` Contravenes Q # 表示法。</span><span class="sxs-lookup"><span data-stu-id="fc860-168">Use of `snake_case` contravenes Q# notation.</span></span> |
| <span data-ttu-id="fc860-169">☒</span><span class="sxs-lookup"><span data-stu-id="fc860-169">☒</span></span> | <s>`operation Search_Oracle`</s> | <span data-ttu-id="fc860-170">在操作名称 contravenes Q # 表示法内部使用下划线。</span><span class="sxs-lookup"><span data-stu-id="fc860-170">Use of underscores internal to operation name contravenes Q# notation.</span></span> |
| <span data-ttu-id="fc860-171">☑</span><span class="sxs-lookup"><span data-stu-id="fc860-171">☑</span></span> | `function StatePreparationOracle` | <span data-ttu-id="fc860-172">使用名词短语建议函数返回操作。</span><span class="sxs-lookup"><span data-stu-id="fc860-172">Use of noun phrase suggests that the function returns an operation.</span></span> |
| <span data-ttu-id="fc860-173">☑</span><span class="sxs-lookup"><span data-stu-id="fc860-173">☑</span></span> | `function EqualityFact` | <span data-ttu-id="fc860-174">清除名词的使用（"事实"），以指示这是一个函数，而形容词却是一个函数。</span><span class="sxs-lookup"><span data-stu-id="fc860-174">Clear use of noun ("fact") to indicate that this is a function, while the adjective.</span></span> |
| <span data-ttu-id="fc860-175">☒</span><span class="sxs-lookup"><span data-stu-id="fc860-175">☒</span></span> | <s>`function GetRotationAngles`</s> | <span data-ttu-id="fc860-176">使用谓词（"get"）表示这是一个操作。</span><span class="sxs-lookup"><span data-stu-id="fc860-176">Use of verb ("get") suggests that this is an operation.</span></span> |
| <span data-ttu-id="fc860-177">☑</span><span class="sxs-lookup"><span data-stu-id="fc860-177">☑</span></span> | `newtype GeneratorTerm` | <span data-ttu-id="fc860-178">名词短语的使用显然是指调用 UDT 构造函数的结果。</span><span class="sxs-lookup"><span data-stu-id="fc860-178">Use of noun phrase clearly refers to the result of calling the UDT constructor.</span></span> |
| <span data-ttu-id="fc860-179">☒</span><span class="sxs-lookup"><span data-stu-id="fc860-179">☒</span></span> | <s>`@Attribute() newtype RunOnce()`</s> | <span data-ttu-id="fc860-180">使用谓词短语建议 UDT 构造函数为操作。</span><span class="sxs-lookup"><span data-stu-id="fc860-180">Use of verb phrase suggests that the UDT constructor is an operation.</span></span> |
| <span data-ttu-id="fc860-181">☑</span><span class="sxs-lookup"><span data-stu-id="fc860-181">☑</span></span> | `@Attribute() newtype Deprecated(Reason : String)` | <span data-ttu-id="fc860-182">使用名词短语会传达属性的使用情况。</span><span class="sxs-lookup"><span data-stu-id="fc860-182">Use of noun phrase communicates the use of the attribute.</span></span> |

***

### <a name="shorthand-and-abbreviations"></a><span data-ttu-id="fc860-183">速记和缩写</span><span class="sxs-lookup"><span data-stu-id="fc860-183">Shorthand and Abbreviations</span></span> ###

<span data-ttu-id="fc860-184">上述建议（尽管如此）有很多形式的速记，可在量程计算中了解常见和普遍使用情况。</span><span class="sxs-lookup"><span data-stu-id="fc860-184">The above advice notwithstanding, there are many forms of shorthand that see common and pervasive use in quantum computing.</span></span>
<span data-ttu-id="fc860-185">建议使用现有的和常见的速记，特别是对于目标计算机操作的内部操作。</span><span class="sxs-lookup"><span data-stu-id="fc860-185">We suggest using existing and common shorthand where it exists, especially for operations that are intrinsic to the operation of a target machine.</span></span>
<span data-ttu-id="fc860-186">例如，我们选择名称而不是 `X` `ApplyX` ，而 `Rz` 不是 `RotateAboutZ` 。</span><span class="sxs-lookup"><span data-stu-id="fc860-186">For example, we choose the name `X` instead of `ApplyX`, and `Rz` instead of `RotateAboutZ`.</span></span>
<span data-ttu-id="fc860-187">使用此类速记时，操作名称应全部大写（例如： `MAJ` ）。</span><span class="sxs-lookup"><span data-stu-id="fc860-187">When using such shorthand, operation names should be all uppercase (e.g.: `MAJ`).</span></span>

<span data-ttu-id="fc860-188">在使用常用首字母缩写词和缩略词（例如 "QFT" 表示 "量程傅立叶转换"）时，应用此约定时需要注意一些。</span><span class="sxs-lookup"><span data-stu-id="fc860-188">Some care is required when applying this convention in the case of commonly used acronyms and initialisms such as "QFT" for "quantum Fourier transform."</span></span>
<span data-ttu-id="fc860-189">建议遵循以下常规 .NET 约定，以便在全名中使用首字母缩写词和缩略词，这规定：</span><span class="sxs-lookup"><span data-stu-id="fc860-189">We suggest following general .NET conventions for the use of acronyms and initialisms in full names, which prescribe that:</span></span>

- <span data-ttu-id="fc860-190">以大写形式命名两字母首字母缩写词和缩略词（例如： `BE` 对于 "大字节序"），</span><span class="sxs-lookup"><span data-stu-id="fc860-190">two-letter acronyms and initialisms are named in upper case (e.g.: `BE` for "big-endian"),</span></span>
- <span data-ttu-id="fc860-191">所有更长的首字母缩写词和缩略词在中命名 `CamelCase` （例如： `Qft` "量程傅立叶变换"）</span><span class="sxs-lookup"><span data-stu-id="fc860-191">all longer acronyms and initialisms are named in `CamelCase` (e.g.: `Qft` for "quantum Fourier transform")</span></span>

<span data-ttu-id="fc860-192">因此，实现 QFT 的操作可以被称为 `QFT` 速记，或写出为 `ApplyQft` 。</span><span class="sxs-lookup"><span data-stu-id="fc860-192">Thus, an operation implementing the QFT could either be called `QFT` as shorthand, or written out as `ApplyQft`.</span></span>

<span data-ttu-id="fc860-193">对于特别常用的操作和函数，可能需要提供一个较长格式的简短名称作为_别名_：</span><span class="sxs-lookup"><span data-stu-id="fc860-193">For particularly commonly used operations and functions, it may be desirable to provide a shorthand name as an _alias_ for a longer form:</span></span>

```qsharp
operation CCNOT(control0 : Qubit, control1 : Qubit, target : Qubit)
is Adj + Ctl {
    Controlled X([control0, control1], target);
}
```

# <a name="guidance"></a>[<span data-ttu-id="fc860-194">指南</span><span class="sxs-lookup"><span data-stu-id="fc860-194">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="fc860-195">建议：</span><span class="sxs-lookup"><span data-stu-id="fc860-195">We suggest:</span></span>

- <span data-ttu-id="fc860-196">适当时，请考虑经常接受和广泛使用的速记名称。</span><span class="sxs-lookup"><span data-stu-id="fc860-196">Consider commonly accepted and widely used shorthand names when appropriate.</span></span>
- <span data-ttu-id="fc860-197">将大写字母用于速记。</span><span class="sxs-lookup"><span data-stu-id="fc860-197">Use uppercase for shorthand.</span></span>
- <span data-ttu-id="fc860-198">将大写字母用于短（两字母）首字母缩写词和缩略词。</span><span class="sxs-lookup"><span data-stu-id="fc860-198">Use uppercase for short (two-letter) acronyms and initialisms.</span></span>
- <span data-ttu-id="fc860-199">使用 `CamelCase` 更长（三个或更多字母）的首字母缩写词和缩略词。</span><span class="sxs-lookup"><span data-stu-id="fc860-199">Use `CamelCase` for longer (three or more letter) acronyms and initialisms.</span></span>

# <a name="examples"></a>[<span data-ttu-id="fc860-200">示例</span><span class="sxs-lookup"><span data-stu-id="fc860-200">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="fc860-201">“属性”</span><span class="sxs-lookup"><span data-stu-id="fc860-201">Name</span></span> | <span data-ttu-id="fc860-202">描述</span><span class="sxs-lookup"><span data-stu-id="fc860-202">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="fc860-203">☑</span><span class="sxs-lookup"><span data-stu-id="fc860-203">☑</span></span> | `X` | <span data-ttu-id="fc860-204">"应用 $X $ 转换" 的公认简写</span><span class="sxs-lookup"><span data-stu-id="fc860-204">Well-understood shorthand for "apply an $X$ transformation"</span></span> |
| <span data-ttu-id="fc860-205">☑</span><span class="sxs-lookup"><span data-stu-id="fc860-205">☑</span></span> | `CNOT` | <span data-ttu-id="fc860-206">"受控-非" 的理解简写</span><span class="sxs-lookup"><span data-stu-id="fc860-206">Well-understood shorthand for "controlled-NOT"</span></span> |
| <span data-ttu-id="fc860-207">☒</span><span class="sxs-lookup"><span data-stu-id="fc860-207">☒</span></span> | <s>`Cnot`</s> | <span data-ttu-id="fc860-208">速记不得为 `CamelCase` 。</span><span class="sxs-lookup"><span data-stu-id="fc860-208">Shorthand should not be in `CamelCase`.</span></span> |
| <span data-ttu-id="fc860-209">☑</span><span class="sxs-lookup"><span data-stu-id="fc860-209">☑</span></span> | `ApplyQft` | <span data-ttu-id="fc860-210">常见的 initialism "QFT" 显示为长格式的名称的一部分。</span><span class="sxs-lookup"><span data-stu-id="fc860-210">Common initialism "QFT" appears as a part of a long-form name.</span></span> |
| <span data-ttu-id="fc860-211">☑</span><span class="sxs-lookup"><span data-stu-id="fc860-211">☑</span></span> | `QFT` | <span data-ttu-id="fc860-212">常见的 initialism "QFT" 显示为简写名称的一部分。</span><span class="sxs-lookup"><span data-stu-id="fc860-212">Common initialism "QFT" appears as a part of a shorthand name.</span></span> |



***


### <a name="proper-nouns-in-names"></a><span data-ttu-id="fc860-213">名称中的正确名词</span><span class="sxs-lookup"><span data-stu-id="fc860-213">Proper Nouns in Names</span></span> ###

<span data-ttu-id="fc860-214">尽管在物理学中，在第一位用户发布相关任务后，通常还会对其进行命名，因此，大多数非 physicists 不熟悉所有人的姓名和所有历史记录。</span><span class="sxs-lookup"><span data-stu-id="fc860-214">While in physics it is common to name things after the first person to publish about them, most non-physicists aren’t familiar with everyone’s names and all of the history.</span></span>
<span data-ttu-id="fc860-215">由于来自物理学的命名约定太大，因此，可能会给输入带来巨大的障碍，因为其他背景中的用户必须了解大量看似模糊的名称才能使用常见操作和概念。</span><span class="sxs-lookup"><span data-stu-id="fc860-215">Relying too heavily on naming conventions from physics can thus put up a substantial barrier to entry, as users from other backgrounds must learn a large number of seemingly opaque names in order to use common operations and concepts.</span></span>
<!-- An important part of the task of reducing confusion is to make code more accessible.
Especially in a field such as quantum computing that is rich with domain expertise, we must at all times be cognizant of the demands we place on that expertise as we design quantum software.
In naming code symbols, one way that this cognizance expresses itself is as an awareness of the convention from physics of adopting as the names of algorithms and operations the names of their original publishers.
While we must maintain the history and intellectual provenance of concepts in quantum computing, demanding that all users be versed in this history to use even the most basic of functions and operations places a barrier to entry that is in most cases severe enough to even present an ethical compromise. -->
<span data-ttu-id="fc860-216">因此，我们建议无论在哪一种合理的情况下，都要将描述概念的常用名词视为强首选项，以使描述概念的发布历史记录的正确名词。</span><span class="sxs-lookup"><span data-stu-id="fc860-216">Thus, we recommend that wherever reasonable, common nouns that describe a concept be adopted in strong preference to proper nouns that describe the publication history of a concept.</span></span>
<span data-ttu-id="fc860-217">例如，单独控制的交换和双向受控 NOT 操作通常称为学术文献中的 "Fredkin" 和 "Toffoli" 操作，但在 Q # 中标识为 `CSWAP` 和 `CCNOT` 。</span><span class="sxs-lookup"><span data-stu-id="fc860-217">As a particular example, the singly controlled SWAP and doubly controlled NOT operations are often called the "Fredkin" and "Toffoli" operations in academic literature, but are identified in Q# primarily as `CSWAP` and `CCNOT`.</span></span>
<span data-ttu-id="fc860-218">在这两种情况下，API 文档注释都提供基于正确名词的同义词名称以及所有合适的引文。</span><span class="sxs-lookup"><span data-stu-id="fc860-218">In both cases, the API documentation comments provide synonymous names based on proper nouns, along with all appropriate citations.</span></span>

<span data-ttu-id="fc860-219">如果始终需要使用正确名词的某些使用方式，则此首选项非常重要，例如，Q # 遵循许多传统语言所设置的传统语言（例如），并引用对 `Bool` 布尔值逻辑的引用中的类型，这反过来又以 George Boole 为荣誉。</span><span class="sxs-lookup"><span data-stu-id="fc860-219">This preference is especially important given that some usage of proper nouns will always be necessary — Q# follows the tradition set by many classical languages, for instance, and refers to `Bool` types in reference to Boolean logic, which is in turn named in honor of George Boole.</span></span>
<span data-ttu-id="fc860-220">几个量程概念的命名方式类似于类似的命名方式，其中包括 `Pauli` 对 Q # 语言的内置类型。</span><span class="sxs-lookup"><span data-stu-id="fc860-220">A few quantum concepts similarly are named in a similar fashion, including the `Pauli` type built-in to the Q# language.</span></span>
<span data-ttu-id="fc860-221">通过最大限度地减少使用正确名词的情况并不是很重要，我们将减少不能合理避免正确名词的影响。</span><span class="sxs-lookup"><span data-stu-id="fc860-221">By minimizing the usage of proper nouns where such usage is not essential, we reduce the impact where proper nouns cannot be reasonably avoided.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="fc860-222">指南</span><span class="sxs-lookup"><span data-stu-id="fc860-222">Guidance</span></span>](#tab/guidance) 

<span data-ttu-id="fc860-223">建议：</span><span class="sxs-lookup"><span data-stu-id="fc860-223">We suggest:</span></span>

- <span data-ttu-id="fc860-224">不要在名称中使用正确名词。</span><span class="sxs-lookup"><span data-stu-id="fc860-224">Avoid the use of proper nouns in names.</span></span>

# <a name="examples"></a>[<span data-ttu-id="fc860-225">示例</span><span class="sxs-lookup"><span data-stu-id="fc860-225">Examples</span></span>](#tab/examples)

***

### <a name="type-conversions"></a><span data-ttu-id="fc860-226">类型转换</span><span class="sxs-lookup"><span data-stu-id="fc860-226">Type Conversions</span></span> ###

<span data-ttu-id="fc860-227">由于 Q # 是一种强类型和 staticly 类型的语言，因此只能使用对类型转换函数的显式调用将一种类型的值用作另一种类型的值。</span><span class="sxs-lookup"><span data-stu-id="fc860-227">Since Q# is a strongly and staticly typed language, a value of one type can only be used as a value of another type by using an explicit call to a type conversion function.</span></span>
<span data-ttu-id="fc860-228">这与允许值隐式更改类型（例如，类型提升）或通过强制转换的语言不同。</span><span class="sxs-lookup"><span data-stu-id="fc860-228">This is in contrast to languages which allow for values to change types implicitly (e.g.: type promotion), or through casting.</span></span>
<span data-ttu-id="fc860-229">因此，类型转换函数在 Q # 库开发中扮演着重要的角色，并且包含有关命名的一个更常见的决策。</span><span class="sxs-lookup"><span data-stu-id="fc860-229">As a result, type conversion functions play an important role in Q# library development, and comprise one of the more commonly encountered decisions about naming.</span></span>
<span data-ttu-id="fc860-230">但请注意，由于类型转换始终是_确定性_的，因此可以将它们作为函数编写，因而会在上述建议的范围之内。</span><span class="sxs-lookup"><span data-stu-id="fc860-230">We note, however, that since type conversions are always _deterministic_, they can be written as functions and thus fall under the advice above.</span></span>
<span data-ttu-id="fc860-231">具体而言，我们建议不要将类型转换函数命名为谓词（例如： `ConvertToX` ）或副词 prepositional 短语（ `ToX` ），但应将其命名为形容词 prepositional 短语，指示源和目标类型（ `XAsY` ）。</span><span class="sxs-lookup"><span data-stu-id="fc860-231">In particular, we suggest that type conversion functions should never be named as verbs (e.g.: `ConvertToX`) or adverb prepositional phrases (`ToX`), but should be named as adjective prepositional phrases that indicate the source and destination types (`XAsY`).</span></span>
<span data-ttu-id="fc860-232">在类型转换函数名称中列出数组类型时，建议采用速记 `Arr` 。</span><span class="sxs-lookup"><span data-stu-id="fc860-232">When listing array types in type conversion function names, we recommend the shorthand `Arr`.</span></span>
<span data-ttu-id="fc860-233">避免异常情况，我们建议使用命名所有类型转换函数， `As` 以便可以快速识别它们。</span><span class="sxs-lookup"><span data-stu-id="fc860-233">Barring exceptional circumstances, we recommend that all type conversion functions be named using `As` so that they can be quickly identified.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="fc860-234">指南</span><span class="sxs-lookup"><span data-stu-id="fc860-234">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="fc860-235">建议：</span><span class="sxs-lookup"><span data-stu-id="fc860-235">We suggest:</span></span>

- <span data-ttu-id="fc860-236">如果函数将类型的值转换 `X` 为类型的值 `Y` ，请使用名称 `AsY` 或 `XAsY` 。</span><span class="sxs-lookup"><span data-stu-id="fc860-236">If a function converts a value of type `X` to a value of type `Y`, use either the name `AsY` or `XAsY`.</span></span>

# <a name="examples"></a>[<span data-ttu-id="fc860-237">示例</span><span class="sxs-lookup"><span data-stu-id="fc860-237">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="fc860-238">“属性”</span><span class="sxs-lookup"><span data-stu-id="fc860-238">Name</span></span> | <span data-ttu-id="fc860-239">描述</span><span class="sxs-lookup"><span data-stu-id="fc860-239">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="fc860-240">☒</span><span class="sxs-lookup"><span data-stu-id="fc860-240">☒</span></span> | <s>`ToDouble`</s> | <span data-ttu-id="fc860-241">介词 "to" 会生成谓词短语，指示操作而不是函数。</span><span class="sxs-lookup"><span data-stu-id="fc860-241">The preposition "to" results in a verb phrase, indicating an operation and not a function.</span></span> |
| <span data-ttu-id="fc860-242">☒</span><span class="sxs-lookup"><span data-stu-id="fc860-242">☒</span></span> | <s>`AsDouble`</s> | <span data-ttu-id="fc860-243">函数名称中不明确输入类型。</span><span class="sxs-lookup"><span data-stu-id="fc860-243">The input type is not clear from the function name.</span></span> |
| <span data-ttu-id="fc860-244">☒</span><span class="sxs-lookup"><span data-stu-id="fc860-244">☒</span></span> | <s>`PauliArrFromBoolArr`</s> | <span data-ttu-id="fc860-245">输入和输出类型的显示顺序不正确。</span><span class="sxs-lookup"><span data-stu-id="fc860-245">The input and output types appear in the wrong order.</span></span> |
| <span data-ttu-id="fc860-246">☑</span><span class="sxs-lookup"><span data-stu-id="fc860-246">☑</span></span> | `ResultArrAsBoolArr` | <span data-ttu-id="fc860-247">输入类型和输出类型都是明确的。</span><span class="sxs-lookup"><span data-stu-id="fc860-247">Both the input types and output types are clear.</span></span> |

***

### <a name="private-or-internal-names"></a><span data-ttu-id="fc860-248">专用或内部名称</span><span class="sxs-lookup"><span data-stu-id="fc860-248">Private or Internal Names</span></span> ###

<span data-ttu-id="fc860-249">在许多情况下，名称将严格地用于库或项目的内部，并且不是库提供的 API 的保证部分。</span><span class="sxs-lookup"><span data-stu-id="fc860-249">In many cases, a name is intended strictly for use internal to a library or project, and is not a guaranteed part of the API offered by a library.</span></span>
<span data-ttu-id="fc860-250">清楚地表明，在命名函数和操作时，这种情况很有帮助，使得对仅限内部的代码的意外依赖关系变得显而易见。</span><span class="sxs-lookup"><span data-stu-id="fc860-250">It is helpful to clearly indicate that this is the case when naming functions and operations so that accidental dependencies on internal-only code are made obvious.</span></span>
<span data-ttu-id="fc860-251">如果操作或函数不能直接使用，而是应由部分应用程序操作的匹配可调用的使用，请考虑使用以关键字开头的名称，该名称以 `internal` 部分应用的可调用的开头。</span><span class="sxs-lookup"><span data-stu-id="fc860-251">If an operation or function is not intended for direct use, but rather should be used by a matching callable which acts by partial application, consider using a name starting with the `internal` keyword for the callable that is partially applied.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="fc860-252">指南</span><span class="sxs-lookup"><span data-stu-id="fc860-252">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="fc860-253">建议：</span><span class="sxs-lookup"><span data-stu-id="fc860-253">We suggest:</span></span>

- <span data-ttu-id="fc860-254">当函数、操作或用户定义类型不是 Q # 库或程序的公共 API 的一部分时，请通过将 `internal` 关键字置于 `function` 、 `operation` 或声明之前来确保将其标记为内部 `newtype` 。</span><span class="sxs-lookup"><span data-stu-id="fc860-254">When a function, operation, or user-defined type is not a part of the public API for a Q# library or program, ensure that it is marked as internal by placing the `internal` keyword before the `function`, `operation`, or `newtype` declaration.</span></span>

# <a name="examples"></a>[<span data-ttu-id="fc860-255">示例</span><span class="sxs-lookup"><span data-stu-id="fc860-255">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="fc860-256">“属性”</span><span class="sxs-lookup"><span data-stu-id="fc860-256">Name</span></span> | <span data-ttu-id="fc860-257">描述</span><span class="sxs-lookup"><span data-stu-id="fc860-257">Description</span></span> |
|---|------|-------------|
| <span data-ttu-id="fc860-258">☒</span><span class="sxs-lookup"><span data-stu-id="fc860-258">☒</span></span> | <s>`operation _ApplyDecomposedOperation`</s> | <span data-ttu-id="fc860-259">不要使用下划线 `_` 指示此操作仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="fc860-259">Do not use an underscore `_` to indicate that this operation is for internal use only.</span></span> |
| <span data-ttu-id="fc860-260">☑</span><span class="sxs-lookup"><span data-stu-id="fc860-260">☑</span></span> | `internal operation ApplyDecomposedOperation` | <span data-ttu-id="fc860-261">`internal`开头的关键字清楚地指示此操作仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="fc860-261">The `internal` keyword at the beginning clearly indicates that this operation is for internal use only.</span></span> |

***
### <a name="variants"></a><span data-ttu-id="fc860-262">变量</span><span class="sxs-lookup"><span data-stu-id="fc860-262">Variants</span></span> ###

<span data-ttu-id="fc860-263">尽管此限制可能不会在 Q # 的未来版本中保持不变，但目前这种情况下，通常会有一组相关的操作或函数，这些操作或函数可由函子它们的输入支持，或其参数的具体类型区分开来。</span><span class="sxs-lookup"><span data-stu-id="fc860-263">Though this limitation may not persist in future versions of Q#, it is presently the case that there will often be groups of related operations or functions that are distinguished by which functors their inputs support, or by the concrete types of their arguments.</span></span>
<span data-ttu-id="fc860-264">可以通过使用相同的根名称，后跟一个或两个指示其变体的字母来区分这些组。</span><span class="sxs-lookup"><span data-stu-id="fc860-264">These groups can be distinguished by using the same root name, followed by one or two letters that indicate its variant.</span></span>

| <span data-ttu-id="fc860-265">Suffix</span><span class="sxs-lookup"><span data-stu-id="fc860-265">Suffix</span></span> | <span data-ttu-id="fc860-266">含义</span><span class="sxs-lookup"><span data-stu-id="fc860-266">Meaning</span></span> |
|--------|---------|
| `A` | <span data-ttu-id="fc860-267">需要输入支持`Adjoint`</span><span class="sxs-lookup"><span data-stu-id="fc860-267">Input expected to support `Adjoint`</span></span> |
| `C` | <span data-ttu-id="fc860-268">需要输入支持`Controlled`</span><span class="sxs-lookup"><span data-stu-id="fc860-268">Input expected to support `Controlled`</span></span> |
| `CA` | <span data-ttu-id="fc860-269">需要输入才能支持 `Controlled` 和`Adjoint`</span><span class="sxs-lookup"><span data-stu-id="fc860-269">Input expected to support `Controlled` and `Adjoint`</span></span> |
| `I` | <span data-ttu-id="fc860-270">输入或输入的类型为`Int`</span><span class="sxs-lookup"><span data-stu-id="fc860-270">Input or inputs are of type `Int`</span></span> |
| `D` | <span data-ttu-id="fc860-271">输入或输入的类型为`Double`</span><span class="sxs-lookup"><span data-stu-id="fc860-271">Input or inputs are of type `Double`</span></span> |
| `L` | <span data-ttu-id="fc860-272">输入或输入的类型为`BigInt`</span><span class="sxs-lookup"><span data-stu-id="fc860-272">Input or inputs are of type `BigInt`</span></span> |

# <a name="guidance"></a>[<span data-ttu-id="fc860-273">指南</span><span class="sxs-lookup"><span data-stu-id="fc860-273">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="fc860-274">建议：</span><span class="sxs-lookup"><span data-stu-id="fc860-274">We suggest:</span></span>

- <span data-ttu-id="fc860-275">如果函数或操作不与任何类似的函数或操作（由类型和函子支持的输入）相关联，请不要使用后缀。</span><span class="sxs-lookup"><span data-stu-id="fc860-275">If a function or operation is not related to any similar functions or operations by the types and functor support of their inputs, do not use a suffix.</span></span>
- <span data-ttu-id="fc860-276">如果函数或操作由类型和函子对其输入的支持相关联，则可使用上表中所示的后缀来区分变体。</span><span class="sxs-lookup"><span data-stu-id="fc860-276">If a function or operation is related to any similar functions or operations by the types and functor support of their inputs, use suffixes as in the table above to distinguish variants.</span></span>

# <a name="examples"></a>[<span data-ttu-id="fc860-277">示例</span><span class="sxs-lookup"><span data-stu-id="fc860-277">Examples</span></span>](#tab/examples)

***

### <a name="arguments-and-variables"></a><span data-ttu-id="fc860-278">参数和变量</span><span class="sxs-lookup"><span data-stu-id="fc860-278">Arguments and Variables</span></span> ###

<span data-ttu-id="fc860-279">函数或操作的 Q # 代码的主要目标是使其易于阅读和理解。</span><span class="sxs-lookup"><span data-stu-id="fc860-279">A key goal of the Q# code for a function or operation is for it to be easily read and understood.</span></span>
<span data-ttu-id="fc860-280">同样，输入和类型参数的名称应传达函数或自变量在提供后的使用方式。</span><span class="sxs-lookup"><span data-stu-id="fc860-280">Similarly, the names of inputs and type arguments should communicate how a function or argument will be used once provided.</span></span>


# <a name="guidance"></a>[<span data-ttu-id="fc860-281">指南</span><span class="sxs-lookup"><span data-stu-id="fc860-281">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="fc860-282">建议：</span><span class="sxs-lookup"><span data-stu-id="fc860-282">We suggest:</span></span>

- <span data-ttu-id="fc860-283">对于所有变量和输入名称，请 `pascalCase` 在、或中使用强首选项 `CamelCase` `snake_case` `ANGRY_CASE` 。</span><span class="sxs-lookup"><span data-stu-id="fc860-283">For all variable and input names, use `pascalCase` in strong preference to `CamelCase`, `snake_case`, or `ANGRY_CASE`.</span></span>
- <span data-ttu-id="fc860-284">输入名称应为描述性值;如果可能，请避免一个或两个字母名称。</span><span class="sxs-lookup"><span data-stu-id="fc860-284">Input names should be descriptive; avoid one or two letter names where possible.</span></span>
- <span data-ttu-id="fc860-285">仅接受一个类型自变量的操作和函数应 `T` 在其角色非常明显时用它来表示该类型参数。</span><span class="sxs-lookup"><span data-stu-id="fc860-285">Operations and functions accepting exactly one type argument should denote that type argument by `T` when its role is obvious.</span></span>
- <span data-ttu-id="fc860-286">如果函数或操作采用多个类型自变量，或者如果单个类型参数的角色不明显，请考虑 `T` `TOutput` 对每个类型使用以（例如：）开头的简短大写单词。</span><span class="sxs-lookup"><span data-stu-id="fc860-286">If a function or operation takes multiple type arguments, or if the role of a single type argument is not obvious, consider using a short capitalized word prefaced by `T` (e.g.: `TOutput`) for each type.</span></span>
- <span data-ttu-id="fc860-287">不要在参数和变量名称中包括类型名称;此信息可以并且应由您的开发环境提供。</span><span class="sxs-lookup"><span data-stu-id="fc860-287">Do not include type names in argument and variable names; this information can and should be provided by your development environment.</span></span>
- <span data-ttu-id="fc860-288">按复数（）表示标量类型 `flagQubit` ，并按复数（）表示数组类型 `measResults` 。</span><span class="sxs-lookup"><span data-stu-id="fc860-288">Denote scalar types by their literal names (`flagQubit`), and array types by a plural (`measResults`).</span></span>
  <span data-ttu-id="fc860-289">对于 qubits 的数组，请考虑以某种方式引用此类类型， `Register` 其中名称是以某种方式密切相关的 qubits 序列。</span><span class="sxs-lookup"><span data-stu-id="fc860-289">For arrays of qubits in particular, consider denoting such types by `Register` where the name refers to a sequence of qubits that are closely related in some way.</span></span>
- <span data-ttu-id="fc860-290">用作数组索引的变量应以开头 `idx` ，并且应为单数（例如： `things[idxThing]` ）。</span><span class="sxs-lookup"><span data-stu-id="fc860-290">Variables used as indices into arrays should begin with `idx` and should be singular (e.g.: `things[idxThing]`).</span></span>
  <span data-ttu-id="fc860-291">具体而言，请特别避免使用单字母变量名作为索引;请考虑至少使用 `idx` 。</span><span class="sxs-lookup"><span data-stu-id="fc860-291">In particular, strongly avoid using single-letter variable names as indices; consider using `idx` at a minimum.</span></span>
- <span data-ttu-id="fc860-292">用于保存数组长度的变量应以开头 `n` ，并且应为复数（例如： `nThings` ）。</span><span class="sxs-lookup"><span data-stu-id="fc860-292">Variables used to hold lengths of arrays should begin with `n` and should be pluralized (e.g.: `nThings`).</span></span>

# <a name="examples"></a>[<span data-ttu-id="fc860-293">示例</span><span class="sxs-lookup"><span data-stu-id="fc860-293">Examples</span></span>](#tab/examples)

***

### <a name="user-defined-type-named-items"></a><span data-ttu-id="fc860-294">用户定义的名为 Items 的类型</span><span class="sxs-lookup"><span data-stu-id="fc860-294">User-Defined Type Named Items</span></span> ###

<span data-ttu-id="fc860-295">用户定义类型中的命名项应命名为 `CamelCase` ，即使是在对 UDT 构造函数的输入中。</span><span class="sxs-lookup"><span data-stu-id="fc860-295">Named items in user-defined types should be named as `CamelCase`, even in input to UDT constructors.</span></span>
<span data-ttu-id="fc860-296">使用访问器表示法（例如： `callable::Apply` ）或复制和更新表示法（）时，这有助于清晰地将命名项与对本地范围变量的引用区分开来 `set arr w/= Data <- newData` 。</span><span class="sxs-lookup"><span data-stu-id="fc860-296">This helps in order to clearly separate named items from references to locally scoped variables when using accessor notation (e.g.: `callable::Apply`) or copy-and-update notation (`set arr w/= Data <- newData`).</span></span>

# <a name="guidance"></a>[<span data-ttu-id="fc860-297">指南</span><span class="sxs-lookup"><span data-stu-id="fc860-297">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="fc860-298">建议：</span><span class="sxs-lookup"><span data-stu-id="fc860-298">We suggest:</span></span>

- <span data-ttu-id="fc860-299">UDT 构造函数中的命名项应命名为 `CamelCase` ; 即，它们应以首字母大写开头。</span><span class="sxs-lookup"><span data-stu-id="fc860-299">Named items in UDT constructors should be named as `CamelCase`; that is, they should begin with an initial uppercase.</span></span>
- <span data-ttu-id="fc860-300">解析为操作的已命名项应命名为谓词阶段。</span><span class="sxs-lookup"><span data-stu-id="fc860-300">Named items that resolve to operations should be named as verb phases.</span></span>
- <span data-ttu-id="fc860-301">不解析为操作的已命名项应命名为名词短语。</span><span class="sxs-lookup"><span data-stu-id="fc860-301">Named items that do not resolve to operations should be named as noun phrases.</span></span>
- <span data-ttu-id="fc860-302">对于包装操作的 Udt，应定义名为的单个名为的项 `Apply` 。</span><span class="sxs-lookup"><span data-stu-id="fc860-302">For UDTs that wrap operations, a single named item called `Apply` should be defined.</span></span>

# <a name="examples"></a>[<span data-ttu-id="fc860-303">示例</span><span class="sxs-lookup"><span data-stu-id="fc860-303">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="fc860-304">片段</span><span class="sxs-lookup"><span data-stu-id="fc860-304">Snippet</span></span> | <span data-ttu-id="fc860-305">描述</span><span class="sxs-lookup"><span data-stu-id="fc860-305">Description</span></span> |
|---|---------|-------------|
| <span data-ttu-id="fc860-306">☑</span><span class="sxs-lookup"><span data-stu-id="fc860-306">☑</span></span> | `newtype Oracle = (Apply : Qubit[] => Unit is Adj + Ctl)` | <span data-ttu-id="fc860-307">该名称 `Apply` 是一个 `CamelCase` 格式的谓词短语，建议指定的项是操作。</span><span class="sxs-lookup"><span data-stu-id="fc860-307">The name `Apply` is a `CamelCase`-formatted verb phrase, suggesting that the named item is an operation.</span></span> |
| <span data-ttu-id="fc860-308">☒</span><span class="sxs-lookup"><span data-stu-id="fc860-308">☒</span></span> | <s>`newtype Oracle = (apply : Qubit[] => Unit is Adj + Ctl) `</s> | <span data-ttu-id="fc860-309">命名项的开头应为大写字母。</span><span class="sxs-lookup"><span data-stu-id="fc860-309">Named items should begin with an initial uppercase letter.</span></span> |
| <span data-ttu-id="fc860-310">☒</span><span class="sxs-lookup"><span data-stu-id="fc860-310">☒</span></span> | <s>`newtype Collection = (Length : Int, Get : Int -> (Qubit => Unit)) `</s> | <span data-ttu-id="fc860-311">解析为函数的命名项应命名为名词短语，而不是谓词短语。</span><span class="sxs-lookup"><span data-stu-id="fc860-311">Named items which resolve to functions should be named as noun phrases, not as verb phrases.</span></span> |

***

## <a name="input-conventions"></a><span data-ttu-id="fc860-312">输入约定</span><span class="sxs-lookup"><span data-stu-id="fc860-312">Input Conventions</span></span> ##

<span data-ttu-id="fc860-313">当开发人员调入操作或函数时，必须按特定顺序指定对该操作或函数的各种输入，从而增加开发人员所面临的认知负载以便使用库。</span><span class="sxs-lookup"><span data-stu-id="fc860-313">When a developer calls into an operation or function, the various inputs to that operation or function must be specified in a particular order, increasing the cognitive load that a developer faces in order to make use of a library.</span></span>
<span data-ttu-id="fc860-314">特别是，记住输入排序的任务通常是任务的一项干扰：对量程算法的实现进行编程。</span><span class="sxs-lookup"><span data-stu-id="fc860-314">In particular, the task of remembering input orderings is often a distraction from the task at hand: programming an implementation of a quantum algorithm.</span></span>
<span data-ttu-id="fc860-315">尽管丰富的 IDE 支持可以将这种情况缓解到很大的作用，但很好的设计和遵从常见约定也有助于最大程度地减少 API 施加的认知负载。</span><span class="sxs-lookup"><span data-stu-id="fc860-315">Though rich IDE support can mitigate this to a large extent, good design and adherence to common conventions can also help to minimize the cognitive load imposed by an API.</span></span>

<span data-ttu-id="fc860-316">在可能的情况下，减少操作或函数预期的输入数量可能会很有帮助，因此，每个输入的角色对于调用到该操作或函数中的开发人员和以后读取该代码的开发人员来说都是非常明显的。</span><span class="sxs-lookup"><span data-stu-id="fc860-316">Where possible, it can be helpful to reduce the number of inputs expected by an operation or function, so that the role of each input is more immediately obvious both to developers calling into that operation or function, and to developers reading that code later.</span></span>
<span data-ttu-id="fc860-317">特别是在不可能或不合理地减少操作或函数的参数数量时，必须具有一致的顺序，以便在预测输入顺序时最大程度地减少用户面临的意外情况。</span><span class="sxs-lookup"><span data-stu-id="fc860-317">Especially when it is not possible or reasonable to reduce the number of arguments to an operation or function, it is important to have a consistent ordering that minimizes the surprise that a user faces when predicting the order of inputs.</span></span>

<span data-ttu-id="fc860-318">我们建议使用部分应用程序，这种类型的排序约定主要是为了 currying f （x，y）≡ f （x）（y）的泛化。</span><span class="sxs-lookup"><span data-stu-id="fc860-318">We recommend an input ordering conventions that largely derives from thinking of partial application as a generalization of currying 𝑓(𝑥, 𝑦) ≡ 𝑓(𝑥)(𝑦).</span></span>
<span data-ttu-id="fc860-319">因此，部分应用第一个参数应该导致可调用的，只要这种方法合理，就会很有用。</span><span class="sxs-lookup"><span data-stu-id="fc860-319">Thus, partially applying the first arguments should result in a callable that is useful in its own right whenever that is reasonable.</span></span>
<span data-ttu-id="fc860-320">遵循此原则时，请考虑使用以下参数顺序：</span><span class="sxs-lookup"><span data-stu-id="fc860-320">Following this principle, consider using the following order of arguments:</span></span>

- <span data-ttu-id="fc860-321">传统的不可调用的参数，如角度、动力向量等。</span><span class="sxs-lookup"><span data-stu-id="fc860-321">Classical non-callable arguments such as angles, vectors of powers, etc.</span></span>
- <span data-ttu-id="fc860-322">可调用参数（函数和参数）。</span><span class="sxs-lookup"><span data-stu-id="fc860-322">Callable arguments (functions and arguments).</span></span>
  <span data-ttu-id="fc860-323">如果函数和操作都作为参数执行，请考虑在函数后放置运算。</span><span class="sxs-lookup"><span data-stu-id="fc860-323">If both functions and operations are taken as arguments, consider placing operations after functions.</span></span>
- <span data-ttu-id="fc860-324">可调用参数对其进行操作的集合的方法与 `Map` 、 `Iter` 、和类似 `Enumerate` `Fold` 。</span><span class="sxs-lookup"><span data-stu-id="fc860-324">Collections acted upon by callable arguments in a similar way to `Map`, `Iter`, `Enumerate`, and `Fold`.</span></span>
- <span data-ttu-id="fc860-325">用作控件的 Qubit 参数。</span><span class="sxs-lookup"><span data-stu-id="fc860-325">Qubit arguments used as controls.</span></span>
- <span data-ttu-id="fc860-326">用作目标的 Qubit 参数。</span><span class="sxs-lookup"><span data-stu-id="fc860-326">Qubit arguments used as targets.</span></span>

<span data-ttu-id="fc860-327">考虑一个操作， `ApplyPhaseEstimationIteration` 该操作在采用角度和 oracle 的阶段估计中使用，传递 `Rz` 不同缩放因子数组所修改的角度，然后控制 oracle 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="fc860-327">Consider an operation `ApplyPhaseEstimationIteration` for use in phase estimation that takes an angle and an oracle, passes the angle to `Rz` modified by an array of different scaling factors, and then controls applications of the oracle.</span></span>
<span data-ttu-id="fc860-328">我们会按以下方式对输入进行排序 `ApplyPhaseEstimationIteration` ：</span><span class="sxs-lookup"><span data-stu-id="fc860-328">We would order the inputs to `ApplyPhaseEstimationIteration` in the following fashion:</span></span>

```qsharp
operation ApplyPhaseEstimationIteration(
    angle : Double,
    callable : (Qubit => () is Ctl),
    scaleFactors : Double[],
    controlQubit : Qubit,
    targetQubits : Qubit[]
)
: Unit
...
```
<span data-ttu-id="fc860-329">作为最大程度地减少意外情况的一种特殊情况，一些函数和操作会模仿内置函子和的行为 `Adjoint` `Controlled` 。</span><span class="sxs-lookup"><span data-stu-id="fc860-329">As a special case of minimizing surprise, some functions and operations mimic the behavior of the built-in functors `Adjoint` and `Controlled`.</span></span>
<span data-ttu-id="fc860-330">例如， `ControlledOnInt<'T>` 具有类似于 `(Int, ('T => Unit is Adj + Ctl)) => ((Qubit[], 'T) => Unit is Adj + Ctl)` 函子的类型， `ControlledOnInt<Qubit[]>(5, _)` `Controlled` 但在控件寄存器表示状态 $ \ket {5} = \ket $ 的条件下 {101} 。</span><span class="sxs-lookup"><span data-stu-id="fc860-330">For instance, `ControlledOnInt<'T>` has type `(Int, ('T => Unit is Adj + Ctl)) => ((Qubit[], 'T) => Unit is Adj + Ctl)`, such that `ControlledOnInt<Qubit[]>(5, _)` acts like the `Controlled` functor, but on the condition that the control register represents the state $\ket{5} = \ket{101}$.</span></span>
<span data-ttu-id="fc860-331">这样一来，开发人员需要输入才能 `ControlledOnInt` 将正在转换的调用放在最后，并且生成的操作采用函子的 `(Qubit[], 'T)` 输出---相同的顺序 `Controlled` 。</span><span class="sxs-lookup"><span data-stu-id="fc860-331">Thus, a developer expects that the inputs to `ControlledOnInt` place the callable being transformed last, and that the resulting operation takes as its input `(Qubit[], 'T)` --- the same order as followed by the output of the `Controlled` functor.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="fc860-332">指南</span><span class="sxs-lookup"><span data-stu-id="fc860-332">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="fc860-333">建议：</span><span class="sxs-lookup"><span data-stu-id="fc860-333">We suggest:</span></span>

- <span data-ttu-id="fc860-334">与使用部分应用程序的使用一致的输入排序。</span><span class="sxs-lookup"><span data-stu-id="fc860-334">Use input orderings consistent with the use of partial application.</span></span>
- <span data-ttu-id="fc860-335">使用与内置函子一致的输入排序。</span><span class="sxs-lookup"><span data-stu-id="fc860-335">Use input orderings consistent with built-in functors.</span></span>
- <span data-ttu-id="fc860-336">将所有经典输入置于任何量子输入之前。</span><span class="sxs-lookup"><span data-stu-id="fc860-336">Place all classical inputs before any quantum inputs.</span></span>

# <a name="examples"></a>[<span data-ttu-id="fc860-337">示例</span><span class="sxs-lookup"><span data-stu-id="fc860-337">Examples</span></span>](#tab/examples)

***

## <a name="documentation-conventions"></a><span data-ttu-id="fc860-338">文档约定</span><span class="sxs-lookup"><span data-stu-id="fc860-338">Documentation Conventions</span></span> ##

<span data-ttu-id="fc860-339">使用 Q # 语言，可以通过使用特殊格式的文档注释，将文档附加到操作、函数和用户定义的类型。</span><span class="sxs-lookup"><span data-stu-id="fc860-339">The Q# language allows for attaching documentation to operations, functions, and user-defined types through the use of specially formatted documentation comments.</span></span>
<span data-ttu-id="fc860-340">这些文档注释由三斜杠（ `///` ）表示，这是[DocFX-风格 Markdown](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html)文档，可用于描述每个操作、函数和用户定义类型的用途、每个预期的输入，等等。</span><span class="sxs-lookup"><span data-stu-id="fc860-340">Denoted by triple-slashes (`///`), these documentation comments are small [DocFX-flavored Markdown](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html) documents that can be used to describing the purpose of each operation, function, and user-defined type, what inputs each expects, and so forth.</span></span>
<span data-ttu-id="fc860-341">使用量子开发工具包提供的编译器可提取这些注释，并使用它们来帮助录入文档，如中所示 https://docs.microsoft.com/quantum 。</span><span class="sxs-lookup"><span data-stu-id="fc860-341">The compiler provided with the Quantum Development Kit extracts these comments and uses them to help typeset documentation similar to that at https://docs.microsoft.com/quantum.</span></span>
<span data-ttu-id="fc860-342">同样，随量子开发工具包一起提供的语言服务器使用这些注释在用户将鼠标悬停在其 Q # 代码中的符号上方时向用户提供帮助。</span><span class="sxs-lookup"><span data-stu-id="fc860-342">Similarly, the language server provided with the Quantum Development Kit uses these comments to provide help to users when they hover over symbols in their Q# code.</span></span>
<span data-ttu-id="fc860-343">利用文档注释，可以通过提供有用的参考来帮助用户理解代码，这是使用本文档中的其他约定不容易表达的详细信息。</span><span class="sxs-lookup"><span data-stu-id="fc860-343">Making use of documentation comments can thus help users to make sense of code by providing a useful reference for details that are not easily expressed using the other conventions in this document.</span></span>

<div class="nextstepaction"><span data-ttu-id="fc860-344">
    [文档注释语法参考](xref:microsoft.quantum.guide.filestructure#documentation-comments)
</span><span class="sxs-lookup"><span data-stu-id="fc860-344">
    [Documentation comment syntax reference](xref:microsoft.quantum.guide.filestructure#documentation-comments)
</span></span></div>

<span data-ttu-id="fc860-345">为了有效地使用此功能来帮助用户，我们建议你在编写文档注释时，记住几个事项。</span><span class="sxs-lookup"><span data-stu-id="fc860-345">In order to effectively use this functionality to help users, we recommend keeping a few things in mind as you write documentation comments.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="fc860-346">指南</span><span class="sxs-lookup"><span data-stu-id="fc860-346">Guidance</span></span>](#tab/guidance)

<span data-ttu-id="fc860-347">建议：</span><span class="sxs-lookup"><span data-stu-id="fc860-347">We suggest:</span></span>

- <span data-ttu-id="fc860-348">每个公共函数、操作和用户定义的类型后面都应跟有文档注释。</span><span class="sxs-lookup"><span data-stu-id="fc860-348">Each public function, operation, and user-defined type should be immediately preceded by a documentation comment.</span></span>
- <span data-ttu-id="fc860-349">每个文档注释至少应包含以下部分：</span><span class="sxs-lookup"><span data-stu-id="fc860-349">At a minimum, each documentation comment should include the following sections:</span></span>
    - <span data-ttu-id="fc860-350">摘要</span><span class="sxs-lookup"><span data-stu-id="fc860-350">Summary</span></span>
    - <span data-ttu-id="fc860-351">输入</span><span class="sxs-lookup"><span data-stu-id="fc860-351">Input</span></span>
    - <span data-ttu-id="fc860-352">输出（如果适用）</span><span class="sxs-lookup"><span data-stu-id="fc860-352">Output (if applicable)</span></span>
- <span data-ttu-id="fc860-353">确保所有摘要都是两个句子或更少。</span><span class="sxs-lookup"><span data-stu-id="fc860-353">Ensure that all summaries are two sentences or less.</span></span> <span data-ttu-id="fc860-354">如果需要更多空间，请在 `# Description` 后面提供 `# Summary` 完整的详细信息部分。</span><span class="sxs-lookup"><span data-stu-id="fc860-354">If more room is needed, provide a `# Description` section immediately following `# Summary` with complete details.</span></span>
- <span data-ttu-id="fc860-355">如果合理，则不要在摘要中包含数学，因为并非所有客户端都支持摘要中的 TeX 表示法。</span><span class="sxs-lookup"><span data-stu-id="fc860-355">Where reasonable, do not include math in summaries, as not all clients support TeX notation in summaries.</span></span> <span data-ttu-id="fc860-356">请注意，在编写 prose 文档（例如 TeX 或 Markdown）时，最好使用较长的行长度。</span><span class="sxs-lookup"><span data-stu-id="fc860-356">Note that when writing prose documents (e.g. TeX or Markdown), it may be preferable to use longer line lengths.</span></span>
- <span data-ttu-id="fc860-357">在部分中提供所有相关的数学表达式 `# Description` 。</span><span class="sxs-lookup"><span data-stu-id="fc860-357">Provide all relevant mathematical expressions in the `# Description` section.</span></span>
- <span data-ttu-id="fc860-358">在描述输入时，请不要重复每个输入的类型，因为编译器可以推断这些类型，并且会导致不一致的风险。</span><span class="sxs-lookup"><span data-stu-id="fc860-358">When describing inputs, do not repeat the types of each input as these can be inferred by the compiler and risk introducing inconsistency.</span></span>
- <span data-ttu-id="fc860-359">提供相应的示例，每个示例都在各自的 `# Example` 部分中。</span><span class="sxs-lookup"><span data-stu-id="fc860-359">Provide examples as appropriate, each in their own `# Example` section.</span></span>
- <span data-ttu-id="fc860-360">在列出代码之前，请简要说明每个示例。</span><span class="sxs-lookup"><span data-stu-id="fc860-360">Briefly describe each example before listing code.</span></span>
- <span data-ttu-id="fc860-361">将所有相关学术出版物（例如：论文、诉讼、博客文章和替代实现）引用 `# References` 为一节中的链接列表。</span><span class="sxs-lookup"><span data-stu-id="fc860-361">Cite all relevant academic publications (e.g.: papers, proceedings, blog posts, and alternative implementations) in a `# References` section as a bulleted list of links.</span></span>
- <span data-ttu-id="fc860-362">请确保在可能的情况下，所有引文链接都是永久和不可变的标识符（DOIs 或版本控制的 arXiv 数字）。</span><span class="sxs-lookup"><span data-stu-id="fc860-362">Ensure that, where possible, all citation links are to permanent and immutable identifiers (DOIs or versioned arXiv numbers).</span></span>
- <span data-ttu-id="fc860-363">当某个操作或函数通过函子变体与其他操作或函数相关时，请将其他变体作为此部分中的项目符号列出 `# See Also` 。</span><span class="sxs-lookup"><span data-stu-id="fc860-363">When an operation or function is related to other operations or functions by functor variants, list other variants as bullets in the `# See Also` section.</span></span>
- <span data-ttu-id="fc860-364">在第1级（）节之间留空注释行 `/// #` ，但不要在第2级（）部分之间留有空行 `/// ##` 。</span><span class="sxs-lookup"><span data-stu-id="fc860-364">Leave a blank comment line between level-1 (`/// #`) sections, but do not leave a blank line between level-2 (`/// ##`) sections.</span></span>

# <a name="examples"></a>[<span data-ttu-id="fc860-365">示例</span><span class="sxs-lookup"><span data-stu-id="fc860-365">Examples</span></span>](#tab/examples)

#### <a name=""></a><span data-ttu-id="fc860-366">☑</span><span class="sxs-lookup"><span data-stu-id="fc860-366">☑</span></span> ####

```
/// # Summary
/// Applies a rotation about the X-axis by a given angle.
///
///
/// # Description
/// This operation rotates a single qubit by the unitary operation
/// \begin{align}
///     R_x(\theta) \mathrel{:=} e^{-i \theta \sigma_x / 2}.
/// \end{align}
///
/// # Input
/// ## theta
/// Angle about which the qubit is to be rotated.
/// ## qubit
/// Qubit to which the gate should be applied.
///
/// # Remarks
/// Equivalent to:
/// ```qsharp
/// R(PauliX, theta, qubit);
/// ```
///
/// # See Also
/// - Ry
/// - Rz
operation Rx(theta : Double, qubit : Qubit) : Unit
is Adj + Ctl {
    body (...) { R(PauliX, theta, qubit); }
    adjoint (...) { R(PauliX, -theta, qubit); }
}
```

***

## <a name="formatting-conventions"></a><span data-ttu-id="fc860-367">格式设置约定</span><span class="sxs-lookup"><span data-stu-id="fc860-367">Formatting Conventions</span></span> ##

<span data-ttu-id="fc860-368">除了上述建议外，还有助于使代码尽可能清晰地使用一致的格式设置规则。</span><span class="sxs-lookup"><span data-stu-id="fc860-368">In addition to the preceding suggestions, it is helpful to help make code as legible as possible to use consistent formatting rules.</span></span>
<span data-ttu-id="fc860-369">这种格式设置规则按性质，这种格式略有意义，并且是个人美观。</span><span class="sxs-lookup"><span data-stu-id="fc860-369">Such formatting rules by nature tend to be somewhat arbitrary and strongly up to personal aesthetics.</span></span>
<span data-ttu-id="fc860-370">尽管如此，我们建议在一组协作者内维护一组一致的格式设置约定，特别是对于较大的 Q # 项目（如量子开发工具包本身）。</span><span class="sxs-lookup"><span data-stu-id="fc860-370">Nonetheless, we recommend maintaining a consistent set of formatting conventions within a group of collaborators, and especially for large Q# projects such as the Quantum Development Kit itself.</span></span>
<span data-ttu-id="fc860-371">可以通过使用与 Q # 编译器集成的格式设置工具来自动应用这些规则。</span><span class="sxs-lookup"><span data-stu-id="fc860-371">These rules can be automatically applied by using the formatting tool integrated with the Q# compiler.</span></span>

# <a name="guidance"></a>[<span data-ttu-id="fc860-372">指南</span><span class="sxs-lookup"><span data-stu-id="fc860-372">Guidance</span></span>](#tab/guidance) 

<span data-ttu-id="fc860-373">建议：</span><span class="sxs-lookup"><span data-stu-id="fc860-373">We suggest:</span></span>

- <span data-ttu-id="fc860-374">使用四个空格而不是制表符来实现可移植性。</span><span class="sxs-lookup"><span data-stu-id="fc860-374">Use four spaces instead of tabs for portability.</span></span>
  <span data-ttu-id="fc860-375">例如，在 VS Code 中：</span><span class="sxs-lookup"><span data-stu-id="fc860-375">For instance, in VS Code:</span></span>
  ```json
    "editor.insertSpaces": true,
    "editor.tabSize": 4
  ```
- <span data-ttu-id="fc860-376">行在合理的位置换行79个字符。</span><span class="sxs-lookup"><span data-stu-id="fc860-376">Line wrap at 79 characters where reasonable.</span></span>
- <span data-ttu-id="fc860-377">在二元运算符周围使用空格。</span><span class="sxs-lookup"><span data-stu-id="fc860-377">Use spaces around binary operators.</span></span>
- <span data-ttu-id="fc860-378">使用用于类型批注的冒号两侧的空格。</span><span class="sxs-lookup"><span data-stu-id="fc860-378">Use spaces on either side of colons used for type annotations.</span></span>
- <span data-ttu-id="fc860-379">在数组和元组文本中使用逗号后使用单个空格（例如：在函数和操作的输入中）。</span><span class="sxs-lookup"><span data-stu-id="fc860-379">Use a single space after commas used in array and tuple literals (e.g.: in inputs to functions and operations).</span></span>
- <span data-ttu-id="fc860-380">在函数、操作或 UDT 名称后，或在属性声明后面不要使用空格 `@` 。</span><span class="sxs-lookup"><span data-stu-id="fc860-380">Do not use spaces after function, operation, or UDT names, or after the `@` in attribute declarations.</span></span>
- <span data-ttu-id="fc860-381">每个属性声明都应在自己的行上。</span><span class="sxs-lookup"><span data-stu-id="fc860-381">Each attribute declaration should be on its own line.</span></span>

# <a name="examples"></a>[<span data-ttu-id="fc860-382">示例</span><span class="sxs-lookup"><span data-stu-id="fc860-382">Examples</span></span>](#tab/examples)

|   | <span data-ttu-id="fc860-383">片段</span><span class="sxs-lookup"><span data-stu-id="fc860-383">Snippet</span></span> | <span data-ttu-id="fc860-384">描述</span><span class="sxs-lookup"><span data-stu-id="fc860-384">Description</span></span> |
|---|---------|-------------|
| <span data-ttu-id="fc860-385">☒</span><span class="sxs-lookup"><span data-stu-id="fc860-385">☒</span></span> | <s>`2+3`</s> | <span data-ttu-id="fc860-386">在二元运算符周围使用空格。</span><span class="sxs-lookup"><span data-stu-id="fc860-386">Use spaces around binary operators.</span></span> |
| <span data-ttu-id="fc860-387">☒</span><span class="sxs-lookup"><span data-stu-id="fc860-387">☒</span></span> | <s>`target:Qubit`</s> | <span data-ttu-id="fc860-388">在类型批注冒号前后使用空格。</span><span class="sxs-lookup"><span data-stu-id="fc860-388">Use spaces around type annotation colons.</span></span> |
| <span data-ttu-id="fc860-389">☑</span><span class="sxs-lookup"><span data-stu-id="fc860-389">☑</span></span> | `Example(a, b, c)` | <span data-ttu-id="fc860-390">输入元组中的项会正确地分隔以便于阅读。</span><span class="sxs-lookup"><span data-stu-id="fc860-390">Items in input tuple are correctly spaced for readability.</span></span> |
| <span data-ttu-id="fc860-391">☒</span><span class="sxs-lookup"><span data-stu-id="fc860-391">☒</span></span> | <s>`Example (a, b, c)`</s> | <span data-ttu-id="fc860-392">应在函数、操作或 UDT 名称后禁止显示空间。</span><span class="sxs-lookup"><span data-stu-id="fc860-392">Spaces should be suppressed after function, operation, or UDT names.</span></span> |

***
