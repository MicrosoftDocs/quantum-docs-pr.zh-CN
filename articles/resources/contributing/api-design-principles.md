---
title: 'Q # API 设计原则'
description: 'Q # API 设计原则'
author: cgranade
ms.author: chgranad
ms.date: 3/9/2020
ms.topic: article
uid: microsoft.quantum.contributing.api-design
ms.openlocfilehash: def6a9f12accfa399fd4db3783b9899fc743f025
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274384"
---
# <a name="q-api-design-principles"></a><span data-ttu-id="fa3f4-103">Q # API 设计原则</span><span class="sxs-lookup"><span data-stu-id="fa3f4-103">Q# API Design Principles</span></span>

## <a name="introduction"></a><span data-ttu-id="fa3f4-104">简介</span><span class="sxs-lookup"><span data-stu-id="fa3f4-104">Introduction</span></span>

<span data-ttu-id="fa3f4-105">作为一种语言和平台，Q # 使用户能够编写、运行、了解和探索量程应用程序。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-105">As a language and as a platform, Q# empowers users to write, run, understand, and explore quantum applications.</span></span>
<span data-ttu-id="fa3f4-106">若要为用户提供支持，请在设计 Q # 库时，按照一组 API 设计原则来指导我们的设计，并帮助我们为量子开发社区提供可用库。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-106">In order to empower users, when we design Q# libraries, we follow a set of API design principles to guide our designs and to help us make usable libraries for the the quantum development community.</span></span>
<span data-ttu-id="fa3f4-107">本文列出了这些原则，并提供示例来帮助指导如何在设计 Q # Api 时应用这些原则。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-107">This article lists these principles, and gives examples to help guide how to apply them when designing Q# APIs.</span></span>

> [!TIP]
> <span data-ttu-id="fa3f4-108">这是一个相当详细的文档，旨在帮助指导库开发和深度库内容。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-108">This is a fairly detailed document that's intended to help guide library development and in-depth library contributions.</span></span>
> <span data-ttu-id="fa3f4-109">如果你在 Q # 中编写自己的库，或者如果你要将更大的功能提供给[q # 库存储库](https://github.com/microsoft/QuantumLibraries)，则可能会发现它最有用。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-109">You'll probably find it most useful if you're writing your own libraries in Q#, or if you're contributing larger features to the [Q# libraries repository](https://github.com/microsoft/QuantumLibraries).</span></span>
>
> <span data-ttu-id="fa3f4-110">另一方面，如果你想要了解如何更常见地参与量程开发工具包，则建议从[贡献指南](xref:microsoft.quantum.contributing)开始。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-110">On the other hand, if you're looking to learn how to contribute to the Quantum Development Kit more generally, we suggest starting with the [contribution guide](xref:microsoft.quantum.contributing).</span></span>
> <span data-ttu-id="fa3f4-111">如果你要查找有关我们建议如何设置你的 Q # 代码格式的更多常规信息，你可能会对签出[样式指南](xref:microsoft.quantum.contributing.style)感兴趣。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-111">If you're looking for more general information about how we recommend formatting your Q# code, you may be interested in checking out the [style guide](xref:microsoft.quantum.contributing.style).</span></span>

## <a name="general-principles"></a><span data-ttu-id="fa3f4-112">一般原则</span><span class="sxs-lookup"><span data-stu-id="fa3f4-112">General Principles</span></span>

<span data-ttu-id="fa3f4-113">**关键原则：** 公开将焦点放在量程应用程序上的 Api。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-113">**Key principle:** Expose APIs that places the focus on quantum applications.</span></span>

- <span data-ttu-id="fa3f4-114">✅**选择反映**算法和应用程序的高级结构的操作和函数名称。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-114">✅ **DO** choose operation and function names that reflect the   high-level structure of algorithms and applications.</span></span>
- <span data-ttu-id="fa3f4-115">⛔️**不**公开主要依赖于低级别实现细节的 api。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-115">⛔️ **DON'T** expose APIs that focus primarily on low-level   implementation details.</span></span>

<span data-ttu-id="fa3f4-116">**关键原则：** 使用示例用例启动每个 API 设计，以确保 Api 直观地使用。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-116">**Key principle:** Start each API design with sample use cases to ensure that APIs are intuitive to use.</span></span>

- <span data-ttu-id="fa3f4-117">✅**请确保公共**API 的每个组件都有相应的用例，而不是尝试针对所有可能的用法进行设计。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-117">✅ **DO** ensure that each component of a public API has a corresponding use case, rather than trying to design for all possible uses from the start.</span></span>
    <span data-ttu-id="fa3f4-118">以不同的方式进行设置，如果它们很有用，请不要引入公共 Api，但请确保 API 的每个部分都有一个*具体*的示例。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-118">Put differently, don't introduce public APIs in case they are useful, but make sure that each part of an API has a *concrete* example in which it will be useful.</span></span>

  <span data-ttu-id="fa3f4-119">*示例：*</span><span class="sxs-lookup"><span data-stu-id="fa3f4-119">*Examples:*</span></span>
  - <span data-ttu-id="fa3f4-120">@"microsoft.quantum.canon.applytoeachca"可用作 `ApplyToEachCA(H, _)` 以统一 superposition 状态准备寄存器，这是许多量程算法中的常见任务。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-120">@"microsoft.quantum.canon.applytoeachca" can be used as `ApplyToEachCA(H, _)` to prepare registers in a uniform superposition state, a common task in many quantum algorithms.</span></span> <span data-ttu-id="fa3f4-121">同样的操作还可用于准备、数字和基于 oracle 的算法中的许多其他任务。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-121">The same operation can also be used for many other tasks in preparation, numerics, and oracle-based algorithms.</span></span>

- <span data-ttu-id="fa3f4-122">✅**进行**集体讨论和研讨会新的 API 设计，以仔细检查它们是否直观，并满足建议的用例。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-122">✅ **DO** brainstorm and workshop new API designs to double-check   that they are intuitive and meet proposed use cases.</span></span>

  <span data-ttu-id="fa3f4-123">*示例：*</span><span class="sxs-lookup"><span data-stu-id="fa3f4-123">*Examples:*</span></span>
  - <span data-ttu-id="fa3f4-124">检查当前 \# 的问答代码，了解新的 API 设计如何简化和阐明现有实现。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-124">Inspect current Q\# code to see how new API designs could   simplify and clarify existing implementations.</span></span>
  - <span data-ttu-id="fa3f4-125">查看建议的 API 设计与主要受众的代表。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-125">Review proposed API designs with representatives of primary   audiences.</span></span>

<span data-ttu-id="fa3f4-126">**关键原则：** 设计 Api 以支持和鼓励可读代码。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-126">**Key principle:** Design APIs to support and encourage readable code.</span></span>

- <span data-ttu-id="fa3f4-127">✅**请确保代码**可供域专家和非专家使用。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-127">✅ **DO** ensure that code is readable by domain experts and   non-experts alike.</span></span>
- <span data-ttu-id="fa3f4-128">✅**请将重点放在**高级算法中的每个操作和功能的效果上，并使用文档深入了解具体的实现细节。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-128">✅ **DO** place the focus on the effects of each operation and   function within the high-level algorithm, using documentation to   delve into implementation details as appropriate.</span></span>
- <span data-ttu-id="fa3f4-129">✅如果适用，**请遵循常见**的[Q \# 样式指南](xref:microsoft.quantum.contributing.style)。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-129">✅ **DO** follow the common [Q\# style guide](xref:microsoft.quantum.contributing.style) whenever applicable.</span></span>

<span data-ttu-id="fa3f4-130">**关键原则：** 设计稳定的 Api，提供向前兼容性。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-130">**Key principle:** Design APIs to be stable and to provide forward compatibility.</span></span>

- <span data-ttu-id="fa3f4-131">✅如果需要进行重大更改，**请**正常弃用旧 api。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-131">✅ **DO** deprecate old APIs gracefully when breaking changes are   required.</span></span>

- <span data-ttu-id="fa3f4-132">✅**请**提供 "填充程序" 操作和函数，使现有用户代码在弃用期间能够正常运行。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-132">✅ **DO** provide "shim" operations and functions that allow   existing user code to operate correctly during deprecation.</span></span>

  <span data-ttu-id="fa3f4-133">*示例：*</span><span class="sxs-lookup"><span data-stu-id="fa3f4-133">*Examples:*</span></span>
  - <span data-ttu-id="fa3f4-134">将调用的操作重命名 `EstimateExpectation` 为时 `EstimateAverage` ，引入一个名为的新操作， `EstimateExpectation` 该操作在其新名称上调用原始操作，以便现有代码可以继续正常工作。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-134">When renaming an operation called `EstimateExpectation` to   `EstimateAverage`, introduce a new operation called   `EstimateExpectation` that calls the original operation at   its new name, so that existing code can continue to work   correctly.</span></span>

- <span data-ttu-id="fa3f4-135">✅**使用**属性将 @"microsoft.quantum.core.deprecated" 弃用功能传达给用户。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-135">✅ **DO** use the @"microsoft.quantum.core.deprecated" attribute to communicate deprecations to the user.</span></span>

- <span data-ttu-id="fa3f4-136">✅重命名操作或函数**时，请**将新名称提供为的字符串输入 `@Deprecated` 。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-136">✅ When renaming an operation or function, **DO** provide the new   name as a string input to `@Deprecated`.</span></span>

- <span data-ttu-id="fa3f4-137">⛔️不会在预览版本至少包含六个月的时间内删除现有的函数或操作，也**不能**删除至少两年的支持版本。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-137">⛔️ **DON'T** remove existing functions or operations without a   deprecation period of at least six months for preview releases,   or at least two years for supported releases.</span></span>

## <a name="functions-and-operations"></a><span data-ttu-id="fa3f4-138">函数和操作</span><span class="sxs-lookup"><span data-stu-id="fa3f4-138">Functions and Operations</span></span>

<span data-ttu-id="fa3f4-139">**关键原则：** 确保每个函数和操作在 API 中都有一个明确定义的用途。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-139">**Key principle:** ensure that every function and operation has a single well-defined purpose within the API.</span></span>

- <span data-ttu-id="fa3f4-140">⛔️**不**公开执行多个不相关任务的函数和操作。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-140">⛔️ **DON'T** expose functions and operations that perform multiple   unrelated tasks.</span></span>

<span data-ttu-id="fa3f4-141">**关键原则：** 设计函数和操作以尽可能地重复使用，并预测将来的需求。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-141">**Key principle:** design functions and operations to be as reusable as possible, and to anticipate future needs.</span></span>

- <span data-ttu-id="fa3f4-142">✅在同一 API 和之前的现有库中，**请设计函数**和操作，使其与其他函数和操作很好地结合。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-142">✅ **DO** design functions and operations to compose well with other   functions and operations, both in the same API and in previously   existing libraries.</span></span>

  <span data-ttu-id="fa3f4-143">*示例：*</span><span class="sxs-lookup"><span data-stu-id="fa3f4-143">*Examples:*</span></span>
  - <span data-ttu-id="fa3f4-144">此 @"microsoft.quantum.canon.delay" 操作对其输入做出最小假设，因此可用于延迟 Q # 标准库或用户定义的操作的应用程序。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-144">The @"microsoft.quantum.canon.delay" operation makes minimal assumptions about its input, and thus can be used to delay applications of either operations across the Q# standard library or as defined by users.</span></span>
    <!-- TODO: define bad example. -->

- <span data-ttu-id="fa3f4-145">✅将纯粹确定的传统逻辑作为函数**而不是操作公开。**</span><span class="sxs-lookup"><span data-stu-id="fa3f4-145">✅ **DO** expose purely deterministic classical logic as   as functions rather than operations.</span></span>

  <span data-ttu-id="fa3f4-146">*示例：*</span><span class="sxs-lookup"><span data-stu-id="fa3f4-146">*Examples:*</span></span>
  - <span data-ttu-id="fa3f4-147">可以确定如何以确定性的方式写入其浮点输入的子例程，因此应将其公开给用户， `Squared : Double -> Double` 而不是作为一个操作公开给用户 `Square : Double => Double` 。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-147">A subroutine which squares its floating-point input can be written deterministically, and so should be exposed to the user as `Squared : Double -> Double` rather than as an operation `Square : Double => Double`.</span></span> <span data-ttu-id="fa3f4-148">这允许在更多位置（例如，在其他函数中）调用子例程，并向编译器提供有用的优化信息，从而影响性能和优化。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-148">This allows for the subroutine to be called in more places (e.g.: inside of other functions), and provides useful optimization information to the compiler that can affect performance and optimizations.</span></span>
  - <span data-ttu-id="fa3f4-149">`ForEach<'TInput, 'TOutput>('TInput => 'TOutput, 'TInput[]) => 'TOutput[]`与 `Mapped<'TInput, 'TOutput>('TInput -> 'TOutput, 'TInput[]) -> 'TOutput[]` 确定性有关的保证不同; 两者在不同情况下都很有用。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-149">`ForEach<'TInput, 'TOutput>('TInput => 'TOutput, 'TInput[]) => 'TOutput[]` and `Mapped<'TInput, 'TOutput>('TInput -> 'TOutput, 'TInput[]) -> 'TOutput[]` differ in the guarantees made with respect to   determinism; both are useful in different circumstances.</span></span>
  - <span data-ttu-id="fa3f4-150">转换量程操作应用程序的 API 例程经常以确定性的方式执行，因此可作为函数提供 `CControlled<'T>(op : 'T => Unit) => ((Bool, 'T) => Unit)` 。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-150">API routines that transform the application of quantum   operations can often be carried out in a deterministic     fashion and hence can be made available as functions such as   `CControlled<'T>(op : 'T => Unit) => ((Bool, 'T) => Unit)`.</span></span>

- <span data-ttu-id="fa3f4-151">✅根据需要使用类型参数，对每个函数和操作尽可能多**地通用化输入**类型。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-151">✅ **DO** generalize the input type as much as reasonable for each   function and operation, using type parameters as needed.</span></span>

  <span data-ttu-id="fa3f4-152">*示例：*</span><span class="sxs-lookup"><span data-stu-id="fa3f4-152">*Examples:*</span></span>
  - <span data-ttu-id="fa3f4-153">`ApplyToEach`具有类型 `<'T>(('T => Unit), 'T[]) => Unit` ，而不是其最常见的应用程序的特定类型 `((Qubit => Unit), Qubit[]) => Unit` 。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-153">`ApplyToEach` has type `<'T>(('T => Unit), 'T[]) => Unit` rather than the specific type of its most common   application, `((Qubit => Unit), Qubit[]) => Unit`.</span></span>

> [!TIP]
> <span data-ttu-id="fa3f4-154">务必要预测未来需求，但解决用户的具体问题也很重要。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-154">It is important to anticipate future needs, but it is also important to solve concrete problems for your users.</span></span>
> <span data-ttu-id="fa3f4-155">因此，在这种关键原则上，始终需要仔细考虑和平衡，以避免开发 Api "以防万一"。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-155">Acting on this key principle thus always requires careful consideration and balancing to avoid developing APIs "just in case."</span></span>

<span data-ttu-id="fa3f4-156">**关键原则：** 选择可预测的函数和操作的输入和输出类型，并传达可调用的用途。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-156">**Key principle:** choose input and output types for functions and operations that are predictable, and that communicate the purpose of a callable.</span></span>

- <span data-ttu-id="fa3f4-157">✅**请**使用元组类型对输入和输出进行逻辑分组，这些输入和输出在一起被视为非常重要。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-157">✅ **DO** use tuple types to logically group inputs and outputs that are only significant when considered together.</span></span> <span data-ttu-id="fa3f4-158">在这些情况下，请考虑使用用户定义的类型。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-158">Consider using a user-defined type in these cases.</span></span>

  <span data-ttu-id="fa3f4-159">*示例：*</span><span class="sxs-lookup"><span data-stu-id="fa3f4-159">*Examples:*</span></span>
  - <span data-ttu-id="fa3f4-160">用于输出另一个函数的本地最小值的函数可能需要将搜索间隔的界限作为输入，以使 `LocalMinima(fn : (Double -> Double), (left : Double, right : Double)) : Double` 其成为适当的签名。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-160">A function to output the local minima of another function   may need to take bounds of a search interval as input, such   that `LocalMinima(fn : (Double -> Double), (left : Double, right : Double)) : Double` may be an appropriate signature.</span></span>
  - <span data-ttu-id="fa3f4-161">使用参数移位技术估算机器学习分类器衍生的操作可能需要将移位和 unshifted 参数向量作为输入。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-161">An operation to estimate a derivative of a machine learning classifier using the parameter shift technique may need to take both the shifted and unshifted parameter vectors as inputs.</span></span> <span data-ttu-id="fa3f4-162">`(unshifted : Double[], shifted : Double[])`在这种情况下，可能适合使用类似于的输入。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-162">An input similar to `(unshifted : Double[], shifted : Double[])` may be appropriate in this case.</span></span>

- <span data-ttu-id="fa3f4-163">✅在不同的函数和操作中一致地对输入和输出元组中的项**进行**排序。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-163">✅ **DO** order items in input and output tuples consistently   across different functions and operations.</span></span>

  <span data-ttu-id="fa3f4-164">*示例：*</span><span class="sxs-lookup"><span data-stu-id="fa3f4-164">*Examples:*</span></span>
  - <span data-ttu-id="fa3f4-165">如果考虑每个或函数或操作分别采用旋转角度和目标 qubit 作为输入，请确保在每个输入元组中对它们进行排序。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-165">If considering two or functions or operations that each take a rotation angle and a target qubit as inputs, ensure that they are ordered the same in each input tuple.</span></span> <span data-ttu-id="fa3f4-166">也就是说，使用和 `ApplyRotation(angle : Double, target : Qubit) : Unit is Adj + Ctl` `DelayedRotation(angle : Double, target : Qubit) : (Unit => Unit is Adj + Ctl)` `ApplyRotation(target : Qubit, angle : Double) : Unit is Adj + Ctl` `DelayedRotation(angle : Double, target : Qubit) : (Unit => Unit is Adj + Ctl)` 。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-166">That is, prefer `ApplyRotation(angle : Double, target : Qubit) : Unit is Adj + Ctl` and `DelayedRotation(angle : Double, target : Qubit) : (Unit => Unit is Adj + Ctl)` to `ApplyRotation(target : Qubit, angle : Double) : Unit is Adj + Ctl` and `DelayedRotation(angle : Double, target : Qubit) : (Unit => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="fa3f4-167">**关键原则：** 设计函数和操作，以便与 \# 部分应用程序等 Q 语言功能正常工作。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-167">**Key principle:** design functions and operations to work well with Q\# language features such as partial application.</span></span>

- <span data-ttu-id="fa3f4-168">✅在输入元组中对项**进行**排序，以便首先发生最常应用的输入（即：使部分应用程序的行为类似于 currying）。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-168">✅ **DO** order items in input tuples such that the most commonly   applied inputs occur first (i.e.: so that partial application   acts similarly to currying).</span></span>

  <span data-ttu-id="fa3f4-169">*示例：*</span><span class="sxs-lookup"><span data-stu-id="fa3f4-169">*Examples:*</span></span>
  - <span data-ttu-id="fa3f4-170">`ApplyRotation`采用浮点数和 qubit 作为输入的操作通常可能会部分应用于浮点输入，后者首先与需要类型输入的操作一起使用 `Qubit => Unit` 。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-170">An operation `ApplyRotation` that takes a floating-point number and a qubit as inputs may often be partially applied with the floating-point input first for use with operations that expect an input of type `Qubit => Unit`.</span></span> <span data-ttu-id="fa3f4-171">因此，签名为`operation ApplyRotation(angle : Double, target : Qubit) : Unit is Adj + Ctl`</span><span class="sxs-lookup"><span data-stu-id="fa3f4-171">Thus, a signature of `operation ApplyRotation(angle : Double, target : Qubit) : Unit is Adj + Ctl`</span></span>
      <span data-ttu-id="fa3f4-172">与部分应用程序的工作方式最一致。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-172">would work most consistently with partial application.</span></span>
  - <span data-ttu-id="fa3f4-173">通常，此指导是指将所有的传统数据放在输入元组中的所有 qubits 之前，但使用合理的判断，并检查如何在实践中调用 API。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-173">Typically, this guidance means placing all classical data   before all qubits in input tuples, but use good judgment and   examine how your API is called in practice.</span></span>

## <a name="user-defined-types"></a><span data-ttu-id="fa3f4-174">用户定义类型</span><span class="sxs-lookup"><span data-stu-id="fa3f4-174">User-Defined Types</span></span>

<span data-ttu-id="fa3f4-175">**关键原则：** 使用用户定义的类型来帮助使 api 更具表现力且便于使用。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-175">**Key principle:** use user-defined types to help make APIs more expressive and convenient to use.</span></span>

- <span data-ttu-id="fa3f4-176">✅**请**引入新的用户定义类型，为长和/或复杂类型提供有用的速记。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-176">✅ **DO** introduce new user-defined types to provide helpful   shorthand for long and/or complicated types.</span></span>

  <span data-ttu-id="fa3f4-177">*示例：*</span><span class="sxs-lookup"><span data-stu-id="fa3f4-177">*Examples:*</span></span>
  - <span data-ttu-id="fa3f4-178">在以下情况下，具有三个 qubit 数组输入的操作类型通常作为输入或作为输出返回，提供 UDT，如`newtype TimeDependentBlockEncoding = ((Qubit[], Qubit[], Qubit[]) => Unit is Adj + Ctl)`</span><span class="sxs-lookup"><span data-stu-id="fa3f4-178">In cases where an operation type with three qubit array inputs is commonly taken as an input or returned as an output, providing a UDT such as `newtype TimeDependentBlockEncoding = ((Qubit[], Qubit[], Qubit[]) => Unit is Adj + Ctl)`</span></span>
      <span data-ttu-id="fa3f4-179">有助于提供有用的速记。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-179">can help provide a useful shorthand.</span></span>

- <span data-ttu-id="fa3f4-180">✅**请**引入新的用户定义类型，以指示给定的基类型仅应在非常特殊的意义上使用。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-180">✅ **DO** introduce new user-defined types to indicate that a given   base type should only be used in a very particular sense.</span></span>

  <span data-ttu-id="fa3f4-181">*示例：*</span><span class="sxs-lookup"><span data-stu-id="fa3f4-181">*Examples:*</span></span>
  - <span data-ttu-id="fa3f4-182">应专门将操作解释为将古典数据编码为量程寄存器的操作，可能适合使用用户定义类型进行标记 `newtype InputEncoder = (Apply : (Qubit[] => Unit))` 。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-182">An operation that should be interpreted specifically as an   operation that encodes classical data into a quantum   register may be appropriate to label with a user-defined   type `newtype InputEncoder = (Apply : (Qubit[] => Unit))`.</span></span>

- <span data-ttu-id="fa3f4-183">✅**确实**会引入新的用户定义类型，其中包含允许将来可扩展性的命名项（例如：以后可能包含其他命名项的结果结构）。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-183">✅ **DO** introduce new user-defined types with named items that   allow for future extensibility (e.g.: a results structure that   may contain additional named items in the future).</span></span>

  <span data-ttu-id="fa3f4-184">*示例：*</span><span class="sxs-lookup"><span data-stu-id="fa3f4-184">*Examples:*</span></span>
  - <span data-ttu-id="fa3f4-185">当某个操作 `TrainModel` 公开大量配置选项时，将这些选项公开为新的 `TrainingOptions` UDT 并提供新函数， `DefaultTrainingOptions : Unit -> TrainingOptions` 使用户能够在 TrainingOptions UDT 值中重写特定的已命名项，同时仍允许库开发人员根据需要添加新的 UDT 项。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-185">When an operation `TrainModel` exposes a large number of   configuration options, exposing these options as a new   `TrainingOptions` UDT and providing a new function   `DefaultTrainingOptions : Unit -> TrainingOptions` allows   users to override specific named items in TrainingOptions   UDT values while still allowing library developers to add   new UDT items as appropriate.</span></span>

- <span data-ttu-id="fa3f4-186">✅为要求用户了解正确的元组析构，**请**为新的用户定义类型声明命名项。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-186">✅ **DO** declare named items for new user-defined types in   preference to requiring users to know the correct tuple   deconstruction.</span></span>

  <span data-ttu-id="fa3f4-187">*示例：*</span><span class="sxs-lookup"><span data-stu-id="fa3f4-187">*Examples:*</span></span>
  - <span data-ttu-id="fa3f4-188">如果在其极坐标分解中表示复数，则优先使用 `newtype ComplexPolar = (Magnitude: Double, Argument: Double)` `newtype ComplexPolar = (Double, Double)` 。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-188">When representing a complex number in its polar   decomposition, prefer   `newtype ComplexPolar = (Magnitude: Double, Argument: Double)` to   `newtype ComplexPolar = (Double, Double)`.</span></span>

<span data-ttu-id="fa3f4-189">**关键原则：** 通过使用用户定义的类型来降低认知负载，无需用户了解其他概念和命名法。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-189">**Key principle:** use user-defined types in ways reduce  cognitive load and that don't require the user to learn additional concepts and nomenclature.</span></span>

- <span data-ttu-id="fa3f4-190">⛔️**不**会引入要求用户频繁使用解包运算符（）的用户定义类型 `!` ，也不会引入通常需要多个解包级别的用户定义类型。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-190">⛔️ **DON'T** introduce user-defined types that require the user to make frequent use of the unwrap operator (`!`), or that commonly require multiple levels of unwrapping.</span></span> <span data-ttu-id="fa3f4-191">可能的缓解策略包括：</span><span class="sxs-lookup"><span data-stu-id="fa3f4-191">Possible mitigation strategies include:</span></span>

  - <span data-ttu-id="fa3f4-192">使用单个项公开用户定义类型时，请考虑定义该项的名称。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-192">When exposing a user-defined type with a single item, consider defining a name for that item.</span></span> <span data-ttu-id="fa3f4-193">例如， `newtype Encoder = (Apply : (Qubit[] => Unit is Adj + Ctl))` 将优先考虑到 `newtype Encoder = (Qubit[] => Unit is Adj + Ctl)` 。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-193">For instance, consider `newtype Encoder = (Apply : (Qubit[] => Unit is Adj + Ctl))` in preference to `newtype Encoder = (Qubit[] => Unit is Adj + Ctl)`.</span></span>

  - <span data-ttu-id="fa3f4-194">确保其他函数和操作可以直接接受 "包装的" UDT 实例。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-194">Ensuring that other functions and operations can accept   "wrapped" UDT instances directly.</span></span>

- <span data-ttu-id="fa3f4-195">⛔️**不**会引入重复内置类型的新用户定义类型，而不提供其他表现力。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-195">⛔️ **DON'T** introduce new user-defined types that duplicate   built-in types without providing additional expressiveness.</span></span>

  <span data-ttu-id="fa3f4-196">*示例：*</span><span class="sxs-lookup"><span data-stu-id="fa3f4-196">*Examples:*</span></span>
  - <span data-ttu-id="fa3f4-197">UDT `newtype QubitRegister = Qubit[]` 不提供任何其他表现力 `Qubit[]` ，因此更难使用而无明显权益。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-197">A UDT `newtype QubitRegister = Qubit[]` provides no   additional expressiveness over `Qubit[]`, and is thus harder   to use with no discernable benefit.</span></span>
  - <span data-ttu-id="fa3f4-198">UDT `newtype LittleEndian = Qubit[]` 记录了如何使用和解释基础寄存器，从而提供了超出其基类型的其他表现力。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-198">A UDT `newtype LittleEndian = Qubit[]` documents how the   underlying register is to be used and interpreted, and thus   provides additional expressiveness over its base type.</span></span>

- <span data-ttu-id="fa3f4-199">除非严格要求，否则⛔️**不**引入访问器函数;  在这种情况下，强烈喜欢命名项。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-199">⛔️ **DON'T** introduce accessor functions unless strictly required;   strongly prefer named items in this case.</span></span>

  <span data-ttu-id="fa3f4-200">*示例：*</span><span class="sxs-lookup"><span data-stu-id="fa3f4-200">*Examples:*</span></span>
  - <span data-ttu-id="fa3f4-201">引入 UDT 时 `newtype Complex = (Double, Double)` ，最好将定义修改为 `newtype Complex = (Real : Double, Imag : Double)` 以引入函数 `GetReal : Complex -> Double` 和 `GetImag : Complex -> Double` 。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-201">When introducing a UDT `newtype Complex = (Double, Double)`,   prefer modifying the definition to   `newtype Complex = (Real : Double, Imag : Double)` to introducing   functions `GetReal : Complex -> Double` and   `GetImag : Complex -> Double`.</span></span>

## <a name="namespaces-and-organization"></a><span data-ttu-id="fa3f4-202">命名空间和组织</span><span class="sxs-lookup"><span data-stu-id="fa3f4-202">Namespaces and Organization</span></span>

<span data-ttu-id="fa3f4-203">**关键原则：** 选择可预测的命名空间名称，并在每个命名空间中清楚地传达函数、操作和用户定义类型的用途。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-203">**Key principle:** choose namespace names that are predictable and that clearly communicate the purpose of functions, operations, and user-defined types in each namespace.</span></span>

- <span data-ttu-id="fa3f4-204">✅将命名**空间命名为** `Publisher.Product.DomainArea` 。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-204">✅ **DO** name namespaces as `Publisher.Product.DomainArea`.</span></span>

  <span data-ttu-id="fa3f4-205">*示例：*</span><span class="sxs-lookup"><span data-stu-id="fa3f4-205">*Examples:*</span></span>
  - <span data-ttu-id="fa3f4-206">作为量程开发工具包的量程模拟功能的一部分，由 Microsoft 发布的函数、操作和 Udt 置于 `Microsoft.Quantum.Simulation` 命名空间中。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-206">Functions, operations, and UDTs published by Microsoft as a   part of the quantum simulation feature of the Quantum   Development Kit are placed in the   `Microsoft.Quantum.Simulation` namespace.</span></span>
  - <span data-ttu-id="fa3f4-207">`Microsoft.Quantum.Math`表示由 Microsoft 发布的命名空间，它是与数学域区相关的量程开发工具包的一部分。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-207">`Microsoft.Quantum.Math` represents a namespace   published by Microsoft as part of the Quantum Development   Kit pertaining to the mathematics domain area.</span></span>

- <span data-ttu-id="fa3f4-208">✅将用于特定功能的操作、函数和用户定义类型放置到描述该功能的命名空间中，即使在不同的问题域中使用该功能，也**是如此。**</span><span class="sxs-lookup"><span data-stu-id="fa3f4-208">✅ **DO** place operations, functions, and user-defined types used   for specific functionality into a namespace that describes that   functionality, even when that functionality is used across   different problem domains.</span></span>

  <span data-ttu-id="fa3f4-209">*示例：*</span><span class="sxs-lookup"><span data-stu-id="fa3f4-209">*Examples:*</span></span>
  - <span data-ttu-id="fa3f4-210">作为量程开发工具包的一部分，由 Microsoft 发布的状态准备 Api 将放入中 `Microsoft.Quantum.Preparation` 。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-210">State preparation APIs published by Microsoft as a part of   the Quantum Development Kit would be placed into   `Microsoft.Quantum.Preparation`.</span></span>
  - <span data-ttu-id="fa3f4-211">将 Microsoft 发布的量程模拟 Api 作为量程开发工具包的一部分进行放置 `Microsoft.Quantum.Simulation` 。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-211">Quantum simulation APIs published by Microsoft as a part of the Quantum   Development Kit would be placed into   `Microsoft.Quantum.Simulation`.</span></span>

- <span data-ttu-id="fa3f4-212">✅**将仅**在特定域中使用的操作、函数和用户定义类型放入命名空间，以指示其实用工具的域。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-212">✅ **DO** place operations, functions, and user-defined types used only within specific domains into namespaces indicating their domain of utility.</span></span> <span data-ttu-id="fa3f4-213">如果需要，请使用子命名空间来指示每个特定于域的命名空间中的焦点任务。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-213">If needed, use subnamespaces to indicate focused tasks within each domain-specific namespace.</span></span>

  <span data-ttu-id="fa3f4-214">*示例：*</span><span class="sxs-lookup"><span data-stu-id="fa3f4-214">*Examples:*</span></span>
  - <span data-ttu-id="fa3f4-215">Microsoft 发布的量程机器学习库主要放在 @"microsoft.quantum.machinelearning" 命名空间中，但示例数据集由 @"microsoft.quantum.machinelearning.datasets" 命名空间提供。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-215">The quantum machine learning library published by Microsoft is largely   placed into the @"microsoft.quantum.machinelearning" namespace, but example   datasets are provided by the @"microsoft.quantum.machinelearning.datasets"   namespace.</span></span>
  - <span data-ttu-id="fa3f4-216">作为量程开发工具包的一部分，由 Microsoft 发布的量程化学 Api 应置于 `Microsoft.Quantum.Chemistry` 。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-216">Quantum chemistry APIs published by Microsoft as a part of the Quantum Development Kit should be placed into `Microsoft.Quantum.Chemistry`.</span></span> <span data-ttu-id="fa3f4-217">用于实现约旦--Wigner 分解的特定功能可能会放在中 `Microsoft.Quantum.Chemistry.JordanWigner` ，因此，适用于量程化学域区域的主接口不涉及实现。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-217">Functionality specific to implementing the Jordan--Wigner decomposition may be placed in `Microsoft.Quantum.Chemistry.JordanWigner`, so that the primary interface for the quantum chemistry domain area is not concerned with implementations.</span></span>

<span data-ttu-id="fa3f4-218">**关键原则：** 将命名空间和访问修饰符一起用于蓄意向用户公开的 API 图面，并隐藏与 Api 实现和测试相关的内部详细信息。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-218">**Key principle:** Use namespaces and access modifiers together to be intentional about the API surface exposed to users, and to hide internal details related to implementation and testing of your APIs.</span></span>

- <span data-ttu-id="fa3f4-219">✅只要合理，就会将实现 API 所需的所有函数和操作放入与正在实现的 API 相同的命名空间中，但使用 "private" 或 "internal"**关键字进行标记**，以指示它们不属于库的公共 API 图面。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-219">✅ Whenever reasonable, **DO** place all functions and operations needed to implement an API into the same namespace as the API being implemented, but marked with the "private" or "internal" keywords to indicate that they are not part of the public API surface for a library.</span></span> <span data-ttu-id="fa3f4-220">使用以下划线（）开头的名称 `_` ，以直观区分公共 callables 中的私有和内部操作和函数。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-220">Use a name beginning with an underscore (`_`) to visually distinguish private and internal operations and functions from public callables.</span></span>

  <span data-ttu-id="fa3f4-221">*示例：*</span><span class="sxs-lookup"><span data-stu-id="fa3f4-221">*Examples:*</span></span>
  - <span data-ttu-id="fa3f4-222">操作名称 `_Features` 指示一个专用于给定命名空间和程序集的函数，并且应带有 `internal` 关键字。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-222">The operation name `_Features` indicates a function that is   private to a given namespace and assembly, and should be   accompanied by either the `internal` keyword.</span></span>

- <span data-ttu-id="fa3f4-223">✅在极少数情况下，若要实现给定命名空间的**API，需要**使用一组丰富的私有函数或操作，请将它们放在一个与正在实现和结束的命名空间相匹配的新命名空间中 `.Private` 。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-223">✅ In the rare case that an extensive set of private functions or operations are needed to implement the API for a given namespace, **DO** place them in a new namespace matching the namespace being implemented and ending in `.Private`.</span></span>

- <span data-ttu-id="fa3f4-224">✅**将所有**单元测试置于与受测命名空间匹配的命名空间中，并以结尾 `.Tests` 。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-224">✅ **DO** place all unit tests into namespaces matching the     namespace under test and ending in `.Tests`.</span></span>

## <a name="naming-conventions-and-vocabulary"></a><span data-ttu-id="fa3f4-225">命名约定和词汇</span><span class="sxs-lookup"><span data-stu-id="fa3f4-225">Naming Conventions and Vocabulary</span></span>

<span data-ttu-id="fa3f4-226">**关键原则：** 跨各种受众（包括量子新手和专家），选择清晰、可访问和可读取的名称和术语。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-226">**Key principle:** Choose names and terminology that are clear, accessible, and readable across a diverse range of audiences, including both quantum novices and experts.</span></span>

- <span data-ttu-id="fa3f4-227">⛔️**请勿**使用歧视或 exclusionary 标识符名称，也不会在 API 文档注释中使用术语。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-227">⛔️ **DON'T** use discriminatory or exclusionary identifier names,   nor terminology in API documentation comments.</span></span>

- <span data-ttu-id="fa3f4-228">✅**使用 API**文档注释来提供相关的上下文、示例和引用，尤其是对于更难的概念。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-228">✅ **DO** use API documentation comments to provide relevant   context, examples, and references, especially for more difficult   concepts.</span></span>

- <span data-ttu-id="fa3f4-229">⛔️**不**会使用不必要的深奥或需要大量的量程算法知识来读取的标识符名称。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-229">⛔️ **DON'T** use identifier names that are unnecessarily esoteric,   or that require significant quantum algorithms knowledge to   read.</span></span>

  <span data-ttu-id="fa3f4-230">*示例：*</span><span class="sxs-lookup"><span data-stu-id="fa3f4-230">*Examples:*</span></span>
  - <span data-ttu-id="fa3f4-231">首选 "调幅放大迭代" 到 "Grover 迭代"。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-231">Prefer "amplitude amplification iteration" to "Grover   iteration."</span></span>

- <span data-ttu-id="fa3f4-232">✅**选择操作**和函数名称可以清楚地传达可调用的预期效果，而不是其实现。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-232">✅ **DO** choose operations and function names that clearly communicate the intended effect of a callable, and not its implementation.</span></span> <span data-ttu-id="fa3f4-233">请注意，可在[API 文档注释](xref:microsoft.quantum.guide.filestructure#documentation-comments)中记录实现。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-233">Note that the implementation can and should be documented in [API documentation comments](xref:microsoft.quantum.guide.filestructure#documentation-comments).</span></span>

  <span data-ttu-id="fa3f4-234">*示例：*</span><span class="sxs-lookup"><span data-stu-id="fa3f4-234">*Examples:*</span></span>
  - <span data-ttu-id="fa3f4-235">由于后者传达了前者的实现方式，因此更喜欢 "估计重叠" 到 "Hadamard 测试"。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-235">Prefer "estimate overlap" to "Hadamard test," as the latter   communicates how the former is implemented.</span></span>

- <span data-ttu-id="fa3f4-236">✅在所有 Q api 中以一致的**方式使用字词** \# ：</span><span class="sxs-lookup"><span data-stu-id="fa3f4-236">✅ **DO** use words in a consistent fashion across all Q\# APIs:</span></span>

  - <span data-ttu-id="fa3f4-237">**谓词**</span><span class="sxs-lookup"><span data-stu-id="fa3f4-237">**Verbs:**</span></span>

    - <span data-ttu-id="fa3f4-238">**断言**：检查有关目标计算机及其 qubits 的状态的假设，可能是通过使用 unphysical 资源来保存。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-238">**Assert**: Check that an assumption about the state of a target machine and its qubits holds, possibly by using unphysical resources.</span></span> <span data-ttu-id="fa3f4-239">使用此谓词的操作应始终安全删除，而不会影响库和可执行程序的功能。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-239">Operations using this verb should always be safely removable without affecting the functionality of libraries and executable programs.</span></span> <span data-ttu-id="fa3f4-240">请注意，与事实不同，断言可能一般取决于外部状态，如 qubit 寄存器的状态、执行环境等。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-240">Note that unlike facts, assertions may in general depend on external state, such as the state of a qubit register, the execution environment or so forth.</span></span> <span data-ttu-id="fa3f4-241">由于与外部状态的依赖关系是一种副作用，因此必须将断言作为运算公开，而不是作为函数公开。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-241">As dependency on external state is a kind of side effect, assertions must be exposed as operations rather than functions.</span></span>

    - <span data-ttu-id="fa3f4-242">**估计**：使用一个或多个可能重复的度量，从度量结果中估计一个传统的数量。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-242">**Estimate**: Using one or more possibly repeated   measurements, estimate a classical quantity from   measurement results.</span></span>

      <span data-ttu-id="fa3f4-243">*示例：*</span><span class="sxs-lookup"><span data-stu-id="fa3f4-243">*Examples:*</span></span>
      - @"microsoft.quantum.characterization.estimatefrequency"
      - @"microsoft.quantum.characterization.estimateoverlapbetweenstates"

    - <span data-ttu-id="fa3f4-244">**准备**：将量程操作或一系列操作应用到一个或多个 qubits （通常是 $ \ket{00\cdots 0} $），这会导致这些 qubits 的状态发展到所需的结束状态。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-244">**Prepare**: Apply a quantum operation or sequence of operations to one or more qubits assumed to start in a particular initial state (typically $\ket{00\cdots 0}$), causing the state of those qubits to evolve to a desired end state.</span></span> <span data-ttu-id="fa3f4-245">通常，在给定的开始状态以外的其他状态下，**可能会**导致未定义的单一转换，但仍**应**保留操作及其 adjoint "取消"，并应用无操作。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-245">In general, acting on states other than the given starting state **MAY** result in an undefined unitary transformation, but **SHOULD** still preserve that an operation and its adjoint "cancel out" and apply a no-op.</span></span>

      <span data-ttu-id="fa3f4-246">*示例：*</span><span class="sxs-lookup"><span data-stu-id="fa3f4-246">*Examples:*</span></span>
      - @"microsoft.quantum.preparation.preparearbitrarystate"
      - @"microsoft.quantum.preparation.prepareuniformsuperposition"

    - <span data-ttu-id="fa3f4-247">**Measure**：向一个或多个 qubits 应用量程操作或一系列操作，读取传统数据。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-247">**Measure**: Apply a quantum operation or sequence of   operations to one or more qubits, reading classical data   back out.</span></span>

      <span data-ttu-id="fa3f4-248">*示例：*</span><span class="sxs-lookup"><span data-stu-id="fa3f4-248">*Examples:*</span></span>
      - @"microsoft.quantum.intrinsic.measure"
      - @"microsoft.quantum.arithmetic.measurefxp"
      - @"microsoft.quantum.arithmetic.measureinteger"

    - <span data-ttu-id="fa3f4-249">**Apply**：向一个或多个 qubits 应用量程运算或一系列操作，从而使这些 qubits 的状态以一致的方式进行更改。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-249">**Apply**: Apply a quantum operation or sequence of operations to one or more qubits, causing the state of those qubits to change in a coherent fashion.</span></span> <span data-ttu-id="fa3f4-250">此谓词是 Q 命名法中最常见的动词 \# ，**不应**在更具体的动词更直接相关时使用。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-250">This verb is the most general verb in Q\# nomenclature, and **SHOULD NOT BE** used when a more specific verb is more directly relevant.</span></span>

  - <span data-ttu-id="fa3f4-251">**名词**：</span><span class="sxs-lookup"><span data-stu-id="fa3f4-251">**Nouns**:</span></span>

    - <span data-ttu-id="fa3f4-252">**事实**：一个布尔条件，它仅依赖于其输入，而不依赖于目标计算机、其环境或计算机的 qubits 的状态。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-252">**Fact**: A Boolean condition which depends only on its inputs and not on the state of a target machine, its environment, or the state of the machine's qubits.</span></span> <span data-ttu-id="fa3f4-253">与断言相比，事实只是对为该事实提供的*值*敏感。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-253">By contrast with an assertion, a fact is only sensitive to the *values* provided to that fact.</span></span> <span data-ttu-id="fa3f4-254">例如：</span><span class="sxs-lookup"><span data-stu-id="fa3f4-254">For example:</span></span>

      <span data-ttu-id="fa3f4-255">*示例：*</span><span class="sxs-lookup"><span data-stu-id="fa3f4-255">*Examples:*</span></span>
      - <span data-ttu-id="fa3f4-256">@"microsoft.quantum.diagnostics.equalityfacti"：表示大约两个整数输入的相等性事实;作为输入提供的整数彼此相等，或不依赖于任何其他程序状态。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-256">@"microsoft.quantum.diagnostics.equalityfacti": represents an equality fact about two integer inputs; either the integers provided as input are equal to each other, or they are not, independent of any other program state.</span></span>

    - <span data-ttu-id="fa3f4-257">**选项：** 一个 UDT，其中包含多个可充当函数或操作的 "可选参数" 的命名项。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-257">**Options:** A UDT containing several named items that can act as "optional arguments" to a function or operation.</span></span> <span data-ttu-id="fa3f4-258">例如：</span><span class="sxs-lookup"><span data-stu-id="fa3f4-258">For example:</span></span>

      <span data-ttu-id="fa3f4-259">*示例：*</span><span class="sxs-lookup"><span data-stu-id="fa3f4-259">*Examples:*</span></span>
      - <span data-ttu-id="fa3f4-260">@"microsoft.quantum.machinelearning.trainingoptions"UDT 包含用于学习速率、minibatch 大小和用于 ML 培训的其他可配置参数的命名项。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-260">The @"microsoft.quantum.machinelearning.trainingoptions" UDT includes named items for learning rate, minibatch size, and other configurable parameters for ML training.</span></span>

  - <span data-ttu-id="fa3f4-261">**形容词**：</span><span class="sxs-lookup"><span data-stu-id="fa3f4-261">**Adjectives**:</span></span>

    - <span data-ttu-id="fa3f4-262">⛔️ **New**：**不应**使用此形容词，因为这样可以避免在许多编程语言（例如 c + +、c #、Java、TypeScript、PowerShell）中将其用法与谓词混淆。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-262">⛔️ **New**: This adjective **SHOULD NOT** be used, as to avoid confusion   with its usage as a verb in many   programming languages (e.g.: C++, C#, Java, TypeScript, PowerShell).</span></span>

  - <span data-ttu-id="fa3f4-263">**介词：** 在某些情况下，介词可用于进一步消除或阐明函数和操作名称中的名词和动词的角色。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-263">**Prepositions:** In some cases, prepositions can be used to further disambiguate or clarify the roles of nouns and verbs in function and operation names.</span></span> <span data-ttu-id="fa3f4-264">不过，请注意，这种情况并不一致。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-264">Care should be taken to do so sparingly and consistently, however.</span></span>

    - <span data-ttu-id="fa3f4-265">**如下：** 表示函数的输入和输出表示相同的信息，但输出将该信息表示**为** *X*而不是其原始表示形式。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-265">**As:** Represents that a function's input and output represent the same information, but that the output represents that information **as** an *X* instead of its original representation.</span></span> <span data-ttu-id="fa3f4-266">这对于类型转换函数尤其常见。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-266">This is especially common for type conversion functions.</span></span>

      <span data-ttu-id="fa3f4-267">*示例：*</span><span class="sxs-lookup"><span data-stu-id="fa3f4-267">*Examples:*</span></span>
      - <span data-ttu-id="fa3f4-268">`IntAsDouble(2)`指示输入（ `2` ）和输出（ `2.0` ）表示定性的信息相同，但使用不同的 Q \# 数据类型执行此操作。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-268">`IntAsDouble(2)` indicates that both the input (`2`) and the output (`2.0`)   represent qualitatively the same information, but using   different Q\# data types to do so.</span></span>

    - <span data-ttu-id="fa3f4-269">**源：** 为了确保一致性，**不应**使用此介词来指示类型转换函数或任何其他**适合的情况**。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-269">**From:** To ensure consistency, this preposition   **SHOULD NOT** be used to indicate type conversion   functions or any other case where **As** is appropriate.</span></span>

    - <span data-ttu-id="fa3f4-270">⛔️ **：** **不应**使用此介词，因为这样可以避免在许多编程语言中将其用法与谓词混淆。</span><span class="sxs-lookup"><span data-stu-id="fa3f4-270">⛔️ **To:** This preposition **SHOULD NOT** be used, as to   avoid confusion with its usage as a verb in many   programming languages.</span></span>
