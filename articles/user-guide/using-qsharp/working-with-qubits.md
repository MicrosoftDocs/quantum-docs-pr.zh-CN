---
title: 使用量子位
description: '了解如何在中使用 qubits Q#'
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.qubits
no-loc:
- 'Q#'
- '$$v'
ms.openlocfilehash: 9a3d7e03016332a04ac9d1610428b6fcd546d1f6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92691586"
---
# <a name="working-with-qubits"></a><span data-ttu-id="82146-103">使用量子位</span><span class="sxs-lookup"><span data-stu-id="82146-103">Working with qubits</span></span>

<span data-ttu-id="82146-104">Qubits 是量程计算中信息的基础对象。</span><span class="sxs-lookup"><span data-stu-id="82146-104">Qubits are the fundamental object of information in quantum computing.</span></span> <span data-ttu-id="82146-105">有关 qubits 的常规介绍，请参阅 [了解量程计算](xref:microsoft.quantum.overview.understanding)，若要深入了解其数学表示形式，请参阅 [Qubit](xref:microsoft.quantum.concepts.qubit)。</span><span class="sxs-lookup"><span data-stu-id="82146-105">For a general introduction to qubits, see [Understanding quantum computing](xref:microsoft.quantum.overview.understanding), and to dive deeper into their mathematical representation, see [The Qubit](xref:microsoft.quantum.concepts.qubit).</span></span> 

<span data-ttu-id="82146-106">本文介绍如何在程序中使用和使用 qubits Q# 。</span><span class="sxs-lookup"><span data-stu-id="82146-106">This article explores how to use and work with qubits in a Q# program.</span></span> 

> [!IMPORTANT]
><span data-ttu-id="82146-107">本文中所述的所有语句在函数体中均无效。</span><span class="sxs-lookup"><span data-stu-id="82146-107">None of the statements discussed in this article are valid within the body of a function.</span></span> <span data-ttu-id="82146-108">它们仅在操作内有效。</span><span class="sxs-lookup"><span data-stu-id="82146-108">They are only valid within operations.</span></span>

## <a name="allocating-qubits"></a><span data-ttu-id="82146-109">分配 Qubits</span><span class="sxs-lookup"><span data-stu-id="82146-109">Allocating Qubits</span></span>

<span data-ttu-id="82146-110">由于物理 qubits 是量程计算机中宝贵的资源，因此，编译器的一项工作是确保它们尽可能有效地使用。</span><span class="sxs-lookup"><span data-stu-id="82146-110">Because physical qubits are a precious resource in a quantum computer, part of the compiler's job is to make sure they are being used as efficiently as possible.</span></span>
<span data-ttu-id="82146-111">因此，您需要 Q# 指定在特定语句块内 *分配* qubits 以供使用。</span><span class="sxs-lookup"><span data-stu-id="82146-111">As such, you need to tell Q# to *allocate* qubits for use within a particular statement block.</span></span>
<span data-ttu-id="82146-112">可以将 qubits 分配为单一 qubit，也可以将其分配为 qubits 数组（称为 *寄存器* ）。</span><span class="sxs-lookup"><span data-stu-id="82146-112">You can allocate qubits as a single qubit, or as an array of qubits, known as a *register* .</span></span> 

### <a name="clean-qubits"></a><span data-ttu-id="82146-113">清理 qubits</span><span class="sxs-lookup"><span data-stu-id="82146-113">Clean qubits</span></span>

<span data-ttu-id="82146-114">使用 `using` 语句可分配新的 qubits，以便在语句块期间使用。</span><span class="sxs-lookup"><span data-stu-id="82146-114">Use the `using` statement to allocate new qubits for use during a statement block.</span></span>

<span data-ttu-id="82146-115">语句包含关键字 `using` ，后跟括在括号中的绑定 `( )` 和 qubits 可用的语句块。</span><span class="sxs-lookup"><span data-stu-id="82146-115">The statement consists of the keyword `using`, followed by a binding enclosed in parentheses `( )` and the statement block within which the qubits are available.</span></span>
<span data-ttu-id="82146-116">绑定遵循与语句相同的模式 `let` ：单个符号或符号元组，后跟一个等号 `=` ，一个值或匹配 *项* 的匹配元组。</span><span class="sxs-lookup"><span data-stu-id="82146-116">The binding follows the same pattern as `let` statements: either a single symbol or a tuple of symbols, followed by an equals sign `=`, and either a single value or a matching tuple of *initializers* .</span></span>

<span data-ttu-id="82146-117">初始值设定项可用于单个 qubit （表示为 `Qubit()` ）或 qubits 的数组， `Qubit[n]` 其中 `n` 是一个 `Int` 表达式。</span><span class="sxs-lookup"><span data-stu-id="82146-117">Initializers are available either for a single qubit, indicated as `Qubit()`, or an array of qubits, `Qubit[n]`, where `n` is an `Int` expression.</span></span>
<span data-ttu-id="82146-118">例如，</span><span class="sxs-lookup"><span data-stu-id="82146-118">For example,</span></span>

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```

<span data-ttu-id="82146-119">以这种方式分配的任何 qubits 在 $ \ket {0} $ 状态下开始。</span><span class="sxs-lookup"><span data-stu-id="82146-119">Any qubits allocated in this way start off in the $\ket{0}$ state.</span></span> <span data-ttu-id="82146-120">因此，在前面的示例中， `auxiliary` 是处于状态 $ \ket $ 的单个 qubit {0} ，位于 `register` qubit 状态 $ \ket {00000} = \ket \otimes {0} {0} {0} \ket \otimes \cdots \otimes $ 中。</span><span class="sxs-lookup"><span data-stu-id="82146-120">Thus in the previous example, `auxiliary` is a single qubit in the state $\ket{0}$, and `register` is in the five-qubit state $\ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$.</span></span>
<span data-ttu-id="82146-121">在块的末尾 `using` ，该块分配的任何 qubits 将立即解除分配，并且无法进一步使用。</span><span class="sxs-lookup"><span data-stu-id="82146-121">At the end of the `using` block, any qubits allocated by that block are immediately deallocated and cannot be used further.</span></span>

> [!WARNING]
> <span data-ttu-id="82146-122">目标计算机可以重复使用已释放的 qubits，并将其提供给其他 `using` 块进行分配。</span><span class="sxs-lookup"><span data-stu-id="82146-122">Target machines can reuse deallocated qubits and offer them to other `using` blocks for allocation.</span></span> <span data-ttu-id="82146-123">因此，在释放之前，目标计算机期望 qubits 处于 $ \ket {0} $ 状态。</span><span class="sxs-lookup"><span data-stu-id="82146-123">As such, the target machine expects that qubits are in the $\ket{0}$ state immediately before deallocation.</span></span>
> <span data-ttu-id="82146-124">请尽可能使用单一操作将分配的任何 qubits 返回到 $ \ket {0} $。</span><span class="sxs-lookup"><span data-stu-id="82146-124">Whenever possible, use unitary operations to return any allocated qubits to $\ket{0}$.</span></span>
> <span data-ttu-id="82146-125">如果需要，可以使用 @"microsoft.quantum.intrinsic.reset" 操作，该操作通过测量将 qubit 返回 $ \ket {0} $，并根据结果有条件地执行操作。</span><span class="sxs-lookup"><span data-stu-id="82146-125">If need be, you can use the @"microsoft.quantum.intrinsic.reset" operation, which returns the qubit to $\ket{0}$ by measuring it and conditionally performing an operation based on the result.</span></span> <span data-ttu-id="82146-126">此类度量会销毁剩余 qubits 的所有牵连，从而影响计算。</span><span class="sxs-lookup"><span data-stu-id="82146-126">Such a measurement destroys any entanglement with the remaining qubits and can thus impact the computation.</span></span>


### <a name="borrowed-qubits"></a><span data-ttu-id="82146-127">借用 Qubits</span><span class="sxs-lookup"><span data-stu-id="82146-127">Borrowed Qubits</span></span>

<span data-ttu-id="82146-128">使用 `borrowing` 语句可将 qubits 分配为临时使用，无需处于特定状态。</span><span class="sxs-lookup"><span data-stu-id="82146-128">Use the `borrowing` statement to allocate qubits for temporary use, which do not need to be in a specific state.</span></span>

<span data-ttu-id="82146-129">在计算过程中，可以使用借用 qubits 作为暂存空间。</span><span class="sxs-lookup"><span data-stu-id="82146-129">You can use borrowed qubits as scratch space during a computation.</span></span>
<span data-ttu-id="82146-130">这些 qubits 通常不处于干净状态，也就是说，它们不一定在已知状态（如 $ \ket $）中进行初始化 {0} 。</span><span class="sxs-lookup"><span data-stu-id="82146-130">These qubits are generally not in a clean state, that is, they are not necessarily initialized in a known state such as $\ket{0}$.</span></span>
<span data-ttu-id="82146-131">这通常称为 "脏" qubits，因为它们的状态未知，甚至可以与量程计算机内存的其他部分放大。</span><span class="sxs-lookup"><span data-stu-id="82146-131">These are often referred to as "dirty" qubits because their state is unknown and can even be entangled with other parts of the quantum computer's memory.</span></span>

<span data-ttu-id="82146-132">绑定遵循与语句相同的模式和规则 `using` 。</span><span class="sxs-lookup"><span data-stu-id="82146-132">The binding follows the same pattern and rules as the `using` statement.</span></span>
<span data-ttu-id="82146-133">例如，</span><span class="sxs-lookup"><span data-stu-id="82146-133">For example,</span></span>
```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```
<span data-ttu-id="82146-134">借 qubits 处于未知状态，在语句块结束时超出范围。</span><span class="sxs-lookup"><span data-stu-id="82146-134">The borrowed qubits are in an unknown state and go out of scope at the end of the statement block.</span></span>
<span data-ttu-id="82146-135">借款人提交 qubits，使其在其借出时处于相同状态;也就是说，它们在语句块的开头和结尾处的状态应相同。</span><span class="sxs-lookup"><span data-stu-id="82146-135">The borrower commits to leaving the qubits in the same state they were in when they borrowed them; that is, their state at the beginning and the end of the statement block should be the same.</span></span>
<span data-ttu-id="82146-136">由于此状态不一定是经典状态，因此在大多数情况下，借款范围不应包含度量值。</span><span class="sxs-lookup"><span data-stu-id="82146-136">Because this state is not necessarily a classical state, in most cases borrowing scopes should not contain measurements.</span></span> 

<span data-ttu-id="82146-137">在借用 qubits 时，系统首先会尝试从正在使用的 qubits 中填充请求，但在语句体中不会访问该请求 `borrowing` 。</span><span class="sxs-lookup"><span data-stu-id="82146-137">When borrowing qubits, the system first tries to fill the request from qubits that are in use but not accessed during the body of the `borrowing` statement.</span></span>
<span data-ttu-id="82146-138">如果没有足够的 qubits，则会分配新的 qubits 来完成请求。</span><span class="sxs-lookup"><span data-stu-id="82146-138">If there aren't enough such qubits, then it allocates new qubits to complete the request.</span></span>

<span data-ttu-id="82146-139">在脏 qubits 的已知用例中，是多控制 CNOT-CONTAINS 入口的实现，只需很少的 qubits 和实现 incrementers。</span><span class="sxs-lookup"><span data-stu-id="82146-139">Among the known use cases of dirty qubits are implementations of multi-controlled CNOT gates that require only very few qubits and implementation of incrementers.</span></span>
<span data-ttu-id="82146-140">有关如何在中使用的示例 Q# ，请参阅本文中的 [借用 Qubits 示例](#borrowing-qubits-example) ，或使用 2n + 2 Qubits （对于使用借用 Roetteler 的算法， [*使用 2n + 2*](https://arxiv.org/abs/1611.07995)) 2017 和 (Toffoli）进行。</span><span class="sxs-lookup"><span data-stu-id="82146-140">For an example of their use in Q#, see [Borrowing Qubits Example](#borrowing-qubits-example) in this article, or the paper [*Factoring using 2n+2 qubits with Toffoli based modular multiplication*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler, and Svore 2017) for an algorithm which utilizes borrowed qubits.</span></span>

## <a name="intrinsic-operations"></a><span data-ttu-id="82146-141">内部操作</span><span class="sxs-lookup"><span data-stu-id="82146-141">Intrinsic Operations</span></span>

<span data-ttu-id="82146-142">分配后，可以将 qubit 传递到函数和操作。</span><span class="sxs-lookup"><span data-stu-id="82146-142">Once allocated, you can pass a qubit to functions and operations.</span></span>
<span data-ttu-id="82146-143">在某种意义上，这是 Q# 程序可以对 qubit 执行的所有操作，因为可执行的操作全部定义为操作。</span><span class="sxs-lookup"><span data-stu-id="82146-143">In some sense, this is all that a Q# program can do with a qubit, as the actions that can be taken are all defined as operations.</span></span>

<span data-ttu-id="82146-144">本文介绍 Q# 可用于与 qubits 交互的几个有用操作。</span><span class="sxs-lookup"><span data-stu-id="82146-144">This article discusses a few useful Q# operations that you can use to interact with qubits.</span></span>
<span data-ttu-id="82146-145">有关这些和其他的详细信息，请参阅 [内部操作和函数](xref:microsoft.quantum.libraries.standard.prelude)。</span><span class="sxs-lookup"><span data-stu-id="82146-145">For more detail about these and others, see [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude).</span></span> 

<span data-ttu-id="82146-146">首先，qubit Pauli 运算符 $X $、$Y $ 和 $Z $ Q# 由内部操作 [`X`](xref:Microsoft.Quantum.Intrinsic.X) 、和表示， [`Y`](xref:Microsoft.Quantum.Intrinsic.Y) [`Z`](xref:Microsoft.Quantum.Intrinsic.Z) 其中每个都具有类型 `(Qubit => Unit is Adj + Ctl)` 。</span><span class="sxs-lookup"><span data-stu-id="82146-146">First, the single-qubit Pauli operators $X$, $Y$, and $Z$ are represented in Q# by the intrinsic operations [`X`](xref:Microsoft.Quantum.Intrinsic.X), [`Y`](xref:Microsoft.Quantum.Intrinsic.Y), and [`Z`](xref:Microsoft.Quantum.Intrinsic.Z), each of which has type `(Qubit => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="82146-147">如 [内部操作和函数](xref:microsoft.quantum.libraries.standard.prelude)中所述，请将 $X $， `X` 以作为位翻转操作，而不是入口。</span><span class="sxs-lookup"><span data-stu-id="82146-147">As described in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), think of $X$ and hence of `X` as a bit-flip operation or NOT gate.</span></span>
<span data-ttu-id="82146-148">您可以使用该 `X` 操作来为某些传统位字符串 $s $ s_0 \ket{s_1 \dots .. s_n} $ 的形式准备状态：</span><span class="sxs-lookup"><span data-stu-id="82146-148">You can use the `X` operation to prepare states of the form $\ket{s_0 s_1 \dots s_n}$ for some classical bit string $s$:</span></span>

```qsharp
operation PrepareBitString(bitstring : Bool[], register : Qubit[]) : Unit
is Adj + Ctl {
    let nQubits = Length(register);
    for (idxQubit in 0..nQubits - 1) {
        if (bitstring[idxQubit]) {
            X(register[idxQubit]);
        }
    }
}

operation RunExample() : Unit {
    using (register = Qubit[8]) {
        PrepareBitString(
            [true, true, false, false, true, false, false, true],
            register
        );
        // At this point, register now has the state |11001001〉.
        // Remember to reset the qubits before deallocation:
        ResetAll(register);
    }
}
```

> [!TIP]
> <span data-ttu-id="82146-149">稍后，您将看到更简洁的方式来编写不需要手动控制流的操作。</span><span class="sxs-lookup"><span data-stu-id="82146-149">Later, you will see more compact ways of writing this operation that do not require manual control flow.</span></span>

<span data-ttu-id="82146-150">你还可以通过使用 \Right 转换 $H $ 来准备状态，例如 $ \ket{+} = \left ( \ket {0} + \ket {1} \sqrt) /\ket {2} $ and $ \left {-} = \ket ( \ket {0} -\right {1} \sqrt) /Hadamard {2} $，该转换 ($，该转换由 Q# 内部操作 [`H`](xref:Microsoft.Quantum.Intrinsic.H) (">") ) ：</span><span class="sxs-lookup"><span data-stu-id="82146-150">You can also prepare states such as $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ and $\ket{-} = \left(\ket{0} - \ket{1}\right) / \sqrt{2}$ by using the Hadamard transform $H$, which is represented in Q# by the intrinsic operation [`H`](xref:Microsoft.Quantum.Intrinsic.H) (also of type (Qubit => Unit is Adj + Ctl)\`):</span></span>

```qsharp
operation PreparePlusMinusState(bitstring : Bool[], register : Qubit[]) : Unit {
    // First, get a computational basis state of the form
    // |s_0 s_1 ... s_n〉 by using PrepareBitString in the earlier example.
    PrepareBitString(bitstring, register);
    // Next, use that |+〉 = H|0〉 and |-〉 = H|1〉 to
    // prepare the desired state.
    for (idxQubit in IndexRange(register)) {
        H(register[idxQubit]);
    }
}
```

## <a name="measurements"></a><span data-ttu-id="82146-151">度量</span><span class="sxs-lookup"><span data-stu-id="82146-151">Measurements</span></span>

<span data-ttu-id="82146-152">可以在不同的基础上执行单个 qubits 的度量值，每个度量值由 [Bloch 球体](xref:microsoft.quantum.glossary#bloch-sphere)上的 Pauli 轴表示。</span><span class="sxs-lookup"><span data-stu-id="82146-152">Measurements of individual qubits can be performed in different bases, each represented by a Pauli axis on the [Bloch sphere](xref:microsoft.quantum.glossary#bloch-sphere).</span></span>
<span data-ttu-id="82146-153">*计算基础* 是指 `PauliZ` 基础，是用于度量的最常见的基础。</span><span class="sxs-lookup"><span data-stu-id="82146-153">The *computational basis* refers to the `PauliZ` basis, and is the most common basis used for measurement.</span></span>

### <a name="measure-a-single-qubit-in-the-pauliz-basis"></a><span data-ttu-id="82146-154">基于单个 qubit 度量 `PauliZ`</span><span class="sxs-lookup"><span data-stu-id="82146-154">Measure a single qubit in the `PauliZ` basis</span></span>

<span data-ttu-id="82146-155">使用 " [`M`](xref:Microsoft.Quantum.Intrinsic.M) 操作"，它是一个内置的非单一的非单一操作，用于度量单个 qubit 并为 `PauliZ` 结果分配一个传统值。</span><span class="sxs-lookup"><span data-stu-id="82146-155">Use the [`M`](xref:Microsoft.Quantum.Intrinsic.M) operation, which is a built-in intrinsic non-unitary operation, to measure a single qubit in the `PauliZ` basis and assign a classical value to the result.</span></span>
<span data-ttu-id="82146-156">`M` 具有保留的返回类型， `Result` 它只能接受值 `Zero` 或 `One` 对应于已测量状态 $ \ket {0} $ 或 $ \ket {1} $-指示结果不再是量程状态。</span><span class="sxs-lookup"><span data-stu-id="82146-156">`M` has a reserved return type, `Result`, which can only take values `Zero` or `One` corresponding to the measured states $\ket{0}$ or $\ket{1}$ - indicating that the result is no longer a quantum state.</span></span>

<span data-ttu-id="82146-157">一个简单的示例是以下操作，它在 $ \ket $ 状态下分配一个 qubit {0} ，然后对其应用一个 Hadamard 操作， `H` 并根据结果测量结果 `PauliZ` 。</span><span class="sxs-lookup"><span data-stu-id="82146-157">A simple example is the following operation, which allocates one qubit in the $\ket{0}$ state, then applies a Hadamard operation `H` to it and measures the result in the `PauliZ` basis.</span></span>

```qsharp
operation MeasureOneQubit() : Result {
    // The following using block creates a fresh qubit and initializes it
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // Apply a Hadamard operation H to the state, thereby preparing the
        // state 1 / sqrt(2) (|0〉 + |1〉).
        H(qubit);
        // Now measure the qubit in Z-basis.
        let result = M(qubit);
        // As the qubit is now in an eigenstate of the measurement operator,
        // reset the qubit before releasing it.
        if (result == One) { X(qubit); }
        // Finally, return the result of the measurement.
        return result;
    }
}
```

### <a name="measure-one-or-more-qubits-in-specific-bases"></a><span data-ttu-id="82146-158">度量特定基准中的一个或多个 qubits</span><span class="sxs-lookup"><span data-stu-id="82146-158">Measure one or more qubits in specific bases</span></span>

<span data-ttu-id="82146-159">若要测量特定基数的一个或多个 qubits 数组，可以使用 [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) 操作。</span><span class="sxs-lookup"><span data-stu-id="82146-159">To measure an array of one or more qubits in specific bases, you can use the [`Measure`](xref:Microsoft.Quantum.Intrinsic.Measure) operation.</span></span>

<span data-ttu-id="82146-160">的输入 `Measure` 是一组 `Pauli` 类型 (例如， `[PauliX, PauliZ, PauliZ]`) 和 qubits 的数组。</span><span class="sxs-lookup"><span data-stu-id="82146-160">The inputs to `Measure` are an array of `Pauli` types (for example, `[PauliX, PauliZ, PauliZ]`) and an array of qubits.</span></span>

<span data-ttu-id="82146-161">下面的操作将提供一个稍微复杂的示例， `true` 如果 `Qubit[]` 在指定的 Pauli 基础上测量时，类型寄存器中的所有 qubits 都处于状态零，则返回布尔值; `false` 否则返回。</span><span class="sxs-lookup"><span data-stu-id="82146-161">A slightly more complicated example is given by the following operation, which returns the Boolean value `true` if all qubits in a register of type `Qubit[]` are in the state zero when measured in a specified Pauli basis, and which returns `false` otherwise.</span></span>

```qsharp
operation MeasureIfAllQubitsAreZero(qubits : Qubit[], pauli : Pauli) : Bool {
    mutable value = true;
    for (qubit in qubits) {
        if (Measure([pauli], [qubit]) == One) {
            set value = false;
        }
    }
    return value;
}
```

<span data-ttu-id="82146-162">请注意，此示例 `Measure` 每次仅在单个 qubits 上执行一次，但可以将该操作扩展到多个 qubits 上的联合度量。</span><span class="sxs-lookup"><span data-stu-id="82146-162">Note that this example still only performs `Measure` on individual qubits one at a time, but the operation can be extended to joint measurements on multiple qubits.</span></span>

## <a name="borrowing-qubits-example"></a><span data-ttu-id="82146-163">借款 Qubits 示例</span><span class="sxs-lookup"><span data-stu-id="82146-163">Borrowing Qubits Example</span></span>

<span data-ttu-id="82146-164">使用关键字的 canon 中有一些示例 `borrowing` ，如以下函数 `MultiControlledXBorrow` 。</span><span class="sxs-lookup"><span data-stu-id="82146-164">There are examples in the canon that use the `borrowing` keyword, such as the following function `MultiControlledXBorrow`.</span></span> <span data-ttu-id="82146-165">如果 `controls` 表示要添加到操作的控件 qubits `X` ，则该实现添加的脏 [ancillas](xref:microsoft.quantum.glossary#ancilla) 的数量为 `Length(controls)-2` 。</span><span class="sxs-lookup"><span data-stu-id="82146-165">If `controls` denotes the control qubits to add to an `X` operation, then the number of dirty [ancillas](xref:microsoft.quantum.glossary#ancilla) added by this implementation is `Length(controls)-2`.</span></span>

```qsharp
operation MultiControlledXBorrow ( controls : Qubit[] , target : Qubit ) : Unit
is Adj + Ctl {

    body (...) {
        ... // skipping some case handling here
        let numberOfDirtyQubits = numberOfControls - 2;
        borrowing( dirtyQubits = Qubit[ numberOfDirtyQubits ] ) {

            let allQubits = [ target ] + dirtyQubits + controls;
            let lastDirtyQubit = numberOfDirtyQubits;
            let totalNumberOfQubits = Length(allQubits);

            let outerOperation1 = 
                CCNOTByIndexLadder(
                    numberOfDirtyQubits + 1, 1, 0, numberOfDirtyQubits , _ );
            
            let innerOperation = 
                CCNOTByIndex(
                    totalNumberOfQubits - 1, totalNumberOfQubits - 2, lastDirtyQubit, _ );
            
            WithA(outerOperation1, innerOperation, allQubits);
            
            let outerOperation2 = 
                CCNOTByIndexLadder(
                    numberOfDirtyQubits + 2, 2, 1, numberOfDirtyQubits - 1 , _ );
            
            WithA(outerOperation2, innerOperation, allQubits);
        }
    }

    controlled(extraControls, ...) {
        MultiControlledXBorrow( extraControls + controls, target );
    }
}
```

<span data-ttu-id="82146-166">请注意，此示例使用了连结符的广泛使用 `With` 方式，其形式适用于支持 adjoint 的操作，例如 `WithA` 。</span><span class="sxs-lookup"><span data-stu-id="82146-166">Note that this example used extensive use of the `With` combinator, in its form that is applicable for operations that support adjoint, for example, `WithA`.</span></span>
<span data-ttu-id="82146-167">这是一种很好的编程风格，因为将控件添加到结构涉及 `With` 仅将控制传播到内部操作。</span><span class="sxs-lookup"><span data-stu-id="82146-167">This is good programming style, because adding control to structures involving `With` propagates control only to the inner operation.</span></span>
<span data-ttu-id="82146-168">另请注意，除 `body` 操作的外， `controlled` 显式提供操作的主体的实现，而不是使用 `controlled auto` 语句。</span><span class="sxs-lookup"><span data-stu-id="82146-168">Also note that, in addition to the `body` of the operation, an implementation of the `controlled` body of the operation was explicitly provided, rather than resorting to a `controlled auto` statement.</span></span>
<span data-ttu-id="82146-169">出现这种情况的原因是，由于线路的结构，可以很容易地添加进一步的控件，这与向中的每个入口添加控件相比，这一点更有利 `body` 。</span><span class="sxs-lookup"><span data-stu-id="82146-169">The reason for this is that, because of the structure of the circuit, it is easy to add further controls, which is beneficial compared to adding control to each gate in the `body`.</span></span> 

<span data-ttu-id="82146-170">此代码可用于将此代码与另一个 canon 函数进行比较，该函数可实现 `MultiControlledXClean` 按操作控制的操作的相同目标 `X` ，不过，这种方法使用了多个 clean qubits `using` 机制。</span><span class="sxs-lookup"><span data-stu-id="82146-170">It is instructive to compare this code with another canon function `MultiControlledXClean` which achieves the same goal of implementing a multiply-controlled `X` operation, however, which uses several clean qubits using the `using` mechanism.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="82146-171">后续步骤</span><span class="sxs-lookup"><span data-stu-id="82146-171">Next steps</span></span>

<span data-ttu-id="82146-172">了解中的 [控制流](xref:microsoft.quantum.guide.controlflow) Q# 。</span><span class="sxs-lookup"><span data-stu-id="82146-172">Learn about [Control Flow](xref:microsoft.quantum.guide.controlflow) in Q#.</span></span>