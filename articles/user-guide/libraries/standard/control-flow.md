---
title: 'Q # standard libararies 中的流控制'
description: '了解 Microsoft Q # 标准库中的流控制操作和函数。'
author: QuantumWriter
uid: microsoft.quantum.concepts.control-flow
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: b41b3edd7a3e3ac13dbda106a869f4cba8183600
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274417"
---
# <a name="higher-order-control-flow"></a><span data-ttu-id="b6b56-103">高阶控制流</span><span class="sxs-lookup"><span data-stu-id="b6b56-103">Higher-Order Control Flow</span></span> #

<span data-ttu-id="b6b56-104">标准库的主要角色之一是，更轻松地将高级算法想法作为[量程程序](https://en.wikipedia.org/wiki/Quantum_programming)进行表达。</span><span class="sxs-lookup"><span data-stu-id="b6b56-104">One of the primary roles of the standard library is to make it easier to express high-level algorithmic ideas as [quantum programs](https://en.wikipedia.org/wiki/Quantum_programming).</span></span>
<span data-ttu-id="b6b56-105">因此，Q # canon 提供各种不同的流控制构造，每个构造使用函数和操作的部分应用程序实现。</span><span class="sxs-lookup"><span data-stu-id="b6b56-105">Thus, the Q# canon provides a variety of different flow control constructs, each implemented using partial application of functions and operations.</span></span>
<span data-ttu-id="b6b56-106">立即跳转到一个示例，请考虑要在收银机上构造 "CNOT-CONTAINS 阶梯" 的情况：</span><span class="sxs-lookup"><span data-stu-id="b6b56-106">Jumping immediately into an example, consider the case in which one wants to construct a "CNOT ladder" on a register:</span></span>

```qsharp
let nQubits = Length(register);
CNOT(register[0], register[1]);
CNOT(register[1], register[2]);
// ...
CNOT(register[nQubits - 2], register[nQubits - 1]);
```

<span data-ttu-id="b6b56-107">可以通过使用迭代和循环来表示此模式 `for` ：</span><span class="sxs-lookup"><span data-stu-id="b6b56-107">We can express this pattern by using iteration and `for` loops:</span></span>

```qsharp
for (idxQubit in 0..nQubits - 2) {
    CNOT(register[idxQubit], register[idxQubit + 1]);
}
```

<span data-ttu-id="b6b56-108">以 <xref:microsoft.quantum.canon.applytoeachca> 和数组操作函数（如）表示， <xref:microsoft.quantum.arrays.zip> 但这更简短且更易于阅读：</span><span class="sxs-lookup"><span data-stu-id="b6b56-108">Expressed in terms of <xref:microsoft.quantum.canon.applytoeachca> and array manipulation functions such as <xref:microsoft.quantum.arrays.zip>, however, this is much shorter and easier to read:</span></span>

```qsharp
ApplyToEachCA(CNOT, Zip(register[0..nQubits - 2], register[1..nQubits - 1]));
```

<span data-ttu-id="b6b56-109">在本部分的其余部分，我们将提供一些示例，说明如何使用 canon 提供的各种流控制操作和功能简洁地 express 量程程序。</span><span class="sxs-lookup"><span data-stu-id="b6b56-109">In the rest of this section, we will provide a number of examples of how to use the various flow control operations and functions provided by the canon to compactly express quantum programs.</span></span>

## <a name="applying-operations-and-functions-over-arrays-and-ranges"></a><span data-ttu-id="b6b56-110">对数组和范围应用操作和函数</span><span class="sxs-lookup"><span data-stu-id="b6b56-110">Applying Operations and Functions over Arrays and Ranges</span></span> ##

<span data-ttu-id="b6b56-111">Canon 提供的一项主要抽象是迭代的一部分。</span><span class="sxs-lookup"><span data-stu-id="b6b56-111">One of the primary abstractions provided by the canon is that of iteration.</span></span>
<span data-ttu-id="b6b56-112">例如，对于单 qubit 单一 $U $，请考虑窗体的单一窗体 $U \otimes U \otimes \cdots \otimes U $。</span><span class="sxs-lookup"><span data-stu-id="b6b56-112">For instance, consider a unitary of the form $U \otimes U \otimes \cdots \otimes U$ for a single-qubit unitary $U$.</span></span>
<span data-ttu-id="b6b56-113">在 Q # 中，我们可能会使用 <xref:microsoft.quantum.arrays.indexrange> 将此表示为 `for` 某个寄存器上的循环：</span><span class="sxs-lookup"><span data-stu-id="b6b56-113">In Q#, we might use <xref:microsoft.quantum.arrays.indexrange> to represent this as as a `for` loop over a register:</span></span>

```qsharp
/// # Summary
/// Applies $H$ to all qubits in a register.
operation ApplyHadamardToAll(
    register : Qubit[])
: Unit is Adj + Ctl {
    for (qubit in register) {
        H(qubit);
    }
}
```

<span data-ttu-id="b6b56-114">然后，可以使用此新操作作为 `HAll(register)` 应用 $H \Otimes H \otimes \cdots \Otimes h $。</span><span class="sxs-lookup"><span data-stu-id="b6b56-114">We can then use this new operation as `HAll(register)` to apply $H \otimes H \otimes \cdots \otimes H$.</span></span>

<span data-ttu-id="b6b56-115">但这样做很麻烦，尤其是在较大的算法中。</span><span class="sxs-lookup"><span data-stu-id="b6b56-115">This is cumbersome to do, however, especially in a larger algorithm.</span></span>
<span data-ttu-id="b6b56-116">此外，此方法专用于要应用于每个 qubit 的特定操作。</span><span class="sxs-lookup"><span data-stu-id="b6b56-116">Moreover, this approach is specialized to the particular operation that we wish to apply to each qubit.</span></span>
<span data-ttu-id="b6b56-117">我们可以使用这一事实，即，操作是第一类来更明确地表达此算法概念：</span><span class="sxs-lookup"><span data-stu-id="b6b56-117">We can use the fact that operations are first-class to express this algorithmic concept more explicitly:</span></span>

```qsharp
ApplyToEachCA(H, register);
```

<span data-ttu-id="b6b56-118">此处的后缀 `CA` 指示对的调用 `ApplyToEach` 本身 adjointable 并可控制。</span><span class="sxs-lookup"><span data-stu-id="b6b56-118">Here, the suffix `CA` indicates that the call to `ApplyToEach` is itself adjointable and controllable.</span></span>
<span data-ttu-id="b6b56-119">因此，如果 `U` 支持 `Adjoint` 和 `Controlled` ，则以下行是等效的：</span><span class="sxs-lookup"><span data-stu-id="b6b56-119">Thus, if `U` supports `Adjoint` and `Controlled`, the following lines are equivalent:</span></span>

```qsharp
Adjoint ApplyToEachCA(U, register);
ApplyToEachCA(Adjoint U, register);
```

<span data-ttu-id="b6b56-120">具体而言，这意味着对的调用 `ApplyToEachCA` 可以出现在自动生成 adjoint 专用化的操作中。</span><span class="sxs-lookup"><span data-stu-id="b6b56-120">In particular, this means that calls to `ApplyToEachCA` can appear in operations for which an adjoint specialization is auto-generated.</span></span>
<span data-ttu-id="b6b56-121">同样， <xref:microsoft.quantum.canon.applytoeachindex> 可用于表示窗体的模式 `U(0, targets[0]); U(1, targets[1]); ...` ，并为其输入支持的函子的每个组合提供版本。</span><span class="sxs-lookup"><span data-stu-id="b6b56-121">Similarly, <xref:microsoft.quantum.canon.applytoeachindex> is useful for representing patterns of the form `U(0, targets[0]); U(1, targets[1]); ...`, and offers versions for each combination of functors supported by its input.</span></span>

> [!TIP]
> <span data-ttu-id="b6b56-122">`ApplyToEach`已参数化，因此它可以与接受除以外的输入的操作一起使用 `Qubit` 。</span><span class="sxs-lookup"><span data-stu-id="b6b56-122">`ApplyToEach` is type-parameterized such that it can be used with operations that take inputs other than `Qubit`.</span></span>
> <span data-ttu-id="b6b56-123">例如，假设 `codeBlocks` 是 <xref:microsoft.quantum.errorcorrection.logicalregister> 需要恢复的值数组。</span><span class="sxs-lookup"><span data-stu-id="b6b56-123">For example, suppose that `codeBlocks` is an array of <xref:microsoft.quantum.errorcorrection.logicalregister> values that need to be recovered.</span></span>
> <span data-ttu-id="b6b56-124">然后， `ApplyToEach(Recover(code, recoveryFn, _), codeBlocks)` 将错误更正代码 `code` 和恢复函数独立应用于 `recoveryFn` 每个块。</span><span class="sxs-lookup"><span data-stu-id="b6b56-124">Then `ApplyToEach(Recover(code, recoveryFn, _), codeBlocks)` will apply the error-correcting code `code` and recovery function `recoveryFn` to each block independently.</span></span>
> <span data-ttu-id="b6b56-125">即使对于传统输入，此操作也是如此： `ApplyToEach(R(_, _, qubit), [(PauliX, PI() / 2.0); (PauliY(), PI() / 3.0]))` 将应用 $ \pi/$2 的旋转约 $X $，后跟 $pi/$3 的旋转 $Y $。</span><span class="sxs-lookup"><span data-stu-id="b6b56-125">This holds even for classical inputs: `ApplyToEach(R(_, _, qubit), [(PauliX, PI() / 2.0); (PauliY(), PI() / 3.0]))` will apply a rotation of $\pi / 2$ about $X$ followed by a rotation of $pi / 3$ about $Y$.</span></span>

<span data-ttu-id="b6b56-126">Q # canon 还提供对函数编程熟悉的传统枚举模式的支持。</span><span class="sxs-lookup"><span data-stu-id="b6b56-126">The Q# canon also provides support for classical enumeration patterns familiar to functional programming.</span></span>
<span data-ttu-id="b6b56-127">例如， <xref:microsoft.quantum.arrays.fold> 实现模式 $f （f （f （s \_ {\text{initial}}，x \_ 0），x \_ 1），\dots ..） $，以在列表中减少函数。</span><span class="sxs-lookup"><span data-stu-id="b6b56-127">For instance, <xref:microsoft.quantum.arrays.fold> implements the pattern $f(f(f(s\_{\text{initial}}, x\_0), x\_1), \dots)$ for reducing a function over a list.</span></span>
<span data-ttu-id="b6b56-128">此模式可用于实现 sum、products、最小值、最大值和其他此类函数：</span><span class="sxs-lookup"><span data-stu-id="b6b56-128">This pattern can be used to implement sums, products, minima, maxima and other such functions:</span></span>

```qsharp
open Microsoft.Quantum.Arrays;
function Plus(a : Int, b : Int) : Int { return a + b; }
function Sum(xs : Int[]) {
    return Fold(Sum, 0, xs);
}
```

<span data-ttu-id="b6b56-129">同样，类似于 <xref:microsoft.quantum.arrays.mapped> 和的函数 <xref:microsoft.quantum.arrays.mappedbyindex> 可用于在 Q # 中表达函数编程概念。</span><span class="sxs-lookup"><span data-stu-id="b6b56-129">Similarly, functions like <xref:microsoft.quantum.arrays.mapped> and <xref:microsoft.quantum.arrays.mappedbyindex> can be used to express functional programming concepts in Q#.</span></span>

## <a name="composing-operations-and-functions"></a><span data-ttu-id="b6b56-130">编写操作和函数</span><span class="sxs-lookup"><span data-stu-id="b6b56-130">Composing Operations and Functions</span></span> ##

<span data-ttu-id="b6b56-131">由 canon 提供的控制流构造作为其输入，以便能够将多个操作或函数组合到一个可调用中。</span><span class="sxs-lookup"><span data-stu-id="b6b56-131">The control flow constructs offered by the canon take operations and functions as their inputs, such that it is helpful to be able to compose several operations or functions into a single callable.</span></span>
<span data-ttu-id="b6b56-132">例如，模式 $UVU ^ {\dagger} $ 在量程编程中非常常见，因此 canon 将操作 <xref:microsoft.quantum.canon.applywith> 作为此模式的抽象提供。</span><span class="sxs-lookup"><span data-stu-id="b6b56-132">For instance, the pattern $UVU^{\dagger}$ is extremely common in quantum programming, such that the canon provides the operation <xref:microsoft.quantum.canon.applywith> as an abstraction for this pattern.</span></span>
<span data-ttu-id="b6b56-133">此抽象还允许更有效地 compliation 线路，因为 `Controlled` 在序列上的 `U(qubit); V(qubit); Adjoint U(qubit);` 操作无需对每个线路执行操作 `U` 。</span><span class="sxs-lookup"><span data-stu-id="b6b56-133">This abstraction also allows for more efficient compliation into circuits, as `Controlled` acting on the sequence `U(qubit); V(qubit); Adjoint U(qubit);` does not need to act on each `U`.</span></span>
<span data-ttu-id="b6b56-134">为此，请将 $c （U） $ 指定为代表 `Controlled U([control], target)` ，并让 $c （V） $ 按相同方式定义。</span><span class="sxs-lookup"><span data-stu-id="b6b56-134">To see this, let $c(U)$ be the unitary representing `Controlled U([control], target)` and let $c(V)$ be defined in the same way.</span></span>
<span data-ttu-id="b6b56-135">然后针对任意状态 $ \ket{\psi} $，\begin{align} c （u） c （V） c （U） ^ \dagger \ket {1} \otimes \ket{\psi} & = \ket {1} \OTIMES （UVU ^ {\dagger} \ket{\psi}） \\ \\ & = （\boldone \otimes u）（c （V））（\boldone \otimes u ^ \dagger） \ket {1} \otimes \ket{\psi}。</span><span class="sxs-lookup"><span data-stu-id="b6b56-135">Then for an arbitrary state $\ket{\psi}$, \begin{align} c(U) c(V) c(U)^\dagger \ket{1} \otimes \ket{\psi} & = \ket{1} \otimes (UVU^{\dagger} \ket{\psi}) \\\\ & = (\boldone \otimes U) (c(V)) (\boldone \otimes U^\dagger) \ket{1} \otimes \ket{\psi}.</span></span>
<span data-ttu-id="b6b56-136">\end{align} 的定义 `Controlled` 。</span><span class="sxs-lookup"><span data-stu-id="b6b56-136">\end{align} by the definition of `Controlled`.</span></span>
<span data-ttu-id="b6b56-137">另一方面，\begin{align} c （U） c （V） c （U） ^ \dagger \ket {0} \otimes \ket{\psi} & = \ket {0} \otimes \ket{\psi} \\ \\ & = \ket {0} \otimes （UU ^ \dagger \ket{\psi}） \\ \\ & = （\Boldone \otimes u）（c （V））（\boldone \otimes u ^ \dagger） \ket {0} \otimes \ket{\psi}。</span><span class="sxs-lookup"><span data-stu-id="b6b56-137">On the other hand, \begin{align} c(U) c(V) c(U)^\dagger \ket{0} \otimes \ket{\psi} & = \ket{0} \otimes \ket{\psi} \\\\ & = \ket{0} \otimes (UU^\dagger \ket{\psi}) \\\\ & = (\boldone \otimes U) (c(V)) (\boldone \otimes U^\dagger) \ket{0} \otimes \ket{\psi}.</span></span>
<span data-ttu-id="b6b56-138">通过线性 \end{align}，我们可以通过这种方式将对所有输入状态 $U $ out。</span><span class="sxs-lookup"><span data-stu-id="b6b56-138">\end{align} By linearity, we can conclude that we can factor $U$ out in this way for all input states.</span></span>
<span data-ttu-id="b6b56-139">也就是说，$c （UVU ^ \dagger） = U c （V） U ^ \dagger $。</span><span class="sxs-lookup"><span data-stu-id="b6b56-139">That is, $c(UVU^\dagger) = U c(V) U^\dagger$.</span></span>
<span data-ttu-id="b6b56-140">由于控制操作的总体开销可能很高，因此使用受控变体（如 `WithC` 和） `WithCA` 可帮助减少需要应用的控件函子的数量。</span><span class="sxs-lookup"><span data-stu-id="b6b56-140">Since controlling operations can be expensive in general, using controlled variants such as `WithC` and `WithCA` can help reduce the number of control functors that need to be applied.</span></span>

> [!NOTE]
> <span data-ttu-id="b6b56-141">分解 $U $ 的另一个结果是，我们甚至不必知道如何将函子应用于 `Controlled` `U` 。</span><span class="sxs-lookup"><span data-stu-id="b6b56-141">One other consequence of factoring out $U$ is that we need not even know how to apply the `Controlled` functor to `U`.</span></span>
> <span data-ttu-id="b6b56-142">`ApplyWithCA`因此，签名比预期的更弱：</span><span class="sxs-lookup"><span data-stu-id="b6b56-142">`ApplyWithCA` therefore has a weaker signature than might be expected:</span></span>
> ```qsharp
> ApplyWithCA<'T> : (('T => Unit is Adj),
>     ('T => Unit is Adj + Ctl), 'T) => Unit
> ```

<span data-ttu-id="b6b56-143">同样，会 <xref:microsoft.quantum.canon.bound> 生成应用其他操作序列的操作。</span><span class="sxs-lookup"><span data-stu-id="b6b56-143">Similarly, <xref:microsoft.quantum.canon.bound> produces operations which apply a sequence of other operations in turn.</span></span>
<span data-ttu-id="b6b56-144">例如，以下项是等效的：</span><span class="sxs-lookup"><span data-stu-id="b6b56-144">For instance, the following are equivalent:</span></span>

```qsharp
H(qubit); X(qubit);
Bound([H, X], qubit);
```

<span data-ttu-id="b6b56-145">与迭代模式合并会使此方法特别有用：</span><span class="sxs-lookup"><span data-stu-id="b6b56-145">Combining with iteration patterns can make this especially useful:</span></span>

```qsharp
// Bracket the quantum Fourier transform with $XH$ on each qubit.
ApplyWith(ApplyToEach(Bound([H, X]), _), QFT, _);
```

### <a name="time-ordered-composition"></a><span data-ttu-id="b6b56-146">有序组合</span><span class="sxs-lookup"><span data-stu-id="b6b56-146">Time-Ordered Composition</span></span> ###

<span data-ttu-id="b6b56-147">我们还可以通过在部分应用程序和传统函数方面考虑 flow 控制来进一步进一步了解，并且还可以根据古典 flow 控制来建模相当复杂的量程概念。</span><span class="sxs-lookup"><span data-stu-id="b6b56-147">We can go still further by thinking of flow control in terms of partial application and classical functions, and can model even fairly sophisticated quantum concepts in terms of classical flow control.</span></span>
<span data-ttu-id="b6b56-148">这种类比是通过识别来精确进行的，即，单一运算符与调用操作的副作用完全一致，以便在其他单一运算符方面对单一运算符进行的任何分解都对应于为传统子例程构造特定调用序列，这将发出说明作为特定单一运算符。</span><span class="sxs-lookup"><span data-stu-id="b6b56-148">This analogy is made precise by the recognition that unitary operators correspond exactly to the side effects of calling operations, such that any decomposition of unitary operators in terms of other unitary operators corresponds to constructing a particular calling sequence for classical subroutines which emit instructions to act as particular unitary operators.</span></span>
<span data-ttu-id="b6b56-149">在此视图下， `Bound` 是矩阵产品的精确表示形式，因为 `Bound([A, B])(target)` 等效于 `A(target); B(target);` ，后者又是对应于 $BA $ 的调用序列。</span><span class="sxs-lookup"><span data-stu-id="b6b56-149">Under this view, `Bound` is precisely the representation of the matrix product, since `Bound([A, B])(target)` is equivalent to `A(target); B(target);`, which in turn is the calling sequence corresponding to $BA$.</span></span>

<span data-ttu-id="b6b56-150">更复杂的示例是[Trotter – Suzuki 扩展](https://arxiv.org/abs/math-ph/0506007v1)。</span><span class="sxs-lookup"><span data-stu-id="b6b56-150">A more sophisticated example is the [Trotter–Suzuki expansion](https://arxiv.org/abs/math-ph/0506007v1).</span></span>
<span data-ttu-id="b6b56-151">如[数据结构](xref:microsoft.quantum.libraries.data-structures)的 "Dynamical 生成器表示" 部分所述，Trotter – Suzuki 扩展提供了一种表示矩阵指数的特别有用的方式。</span><span class="sxs-lookup"><span data-stu-id="b6b56-151">As discussed in the Dynamical Generator Representation section of [data structures](xref:microsoft.quantum.libraries.data-structures), the Trotter–Suzuki expansion provides a particularly useful way of expressing matrix exponentials.</span></span>
<span data-ttu-id="b6b56-152">例如，以最低顺序应用扩展时，会生成任何运算符 $A $ 和 $B $，$A = A ^ \dagger $ 和 $B = B ^ \dagger $，\begin{align} \tag{★} \label{eq： trotter-suzuki-0} \exp （i [A + B] t） = \ lim_ {n\to\infty} \left （\exp （i A t/n） \exp （i B t/n） \right） ^ n。</span><span class="sxs-lookup"><span data-stu-id="b6b56-152">For instance, applying the expansion at its lowest order yields that for any operators $A$ and $B$ such that $A = A^\dagger$ and $B = B^\dagger$, \begin{align} \tag{★} \label{eq:trotter-suzuki-0} \exp(i [A + B] t) = \lim_{n\to\infty} \left(\exp(i A t / n) \exp(i B t / n)\right)^n.</span></span>
<span data-ttu-id="b6b56-153">\end{align} 俗称，这意味着我们可以通过在 $A $ 和 $B $ 单独的情况下进行发展，在 $A + B $ 下提高状态。</span><span class="sxs-lookup"><span data-stu-id="b6b56-153">\end{align} Colloquially, this says that we can approximately evolve a state under $A + B$ by alternately evolving under $A$ and $B$ alone.</span></span>
<span data-ttu-id="b6b56-154">如果我们在 `A : (Double, Qubit[]) => Unit` 应用 $e ^ {i t A} $ 的操作下，通过 $A $ 来表示进化，则在重新排列调用序列方面，Trotter – Suzuki 扩展的表示形式就变得清晰。</span><span class="sxs-lookup"><span data-stu-id="b6b56-154">If we represent evolution under $A$ by an operation `A : (Double, Qubit[]) => Unit` that applies $e^{i t A}$, then the representation of the Trotter–Suzuki expansion in terms of rearranging calling sequences becomes clear.</span></span>
<span data-ttu-id="b6b56-155">具体而言，在给定操作 `U : ((Int, Double, Qubit[]) => Unit is Adj + Ctl` 的情况下， `A = U(0, _, _)` `B = U(1, _, _)` 我们可以 `U` 通过生成窗体的序列来定义一个新的操作，该操作表示一次 $t $ 的整数</span><span class="sxs-lookup"><span data-stu-id="b6b56-155">Concretely, given an operation `U : ((Int, Double, Qubit[]) => Unit is Adj + Ctl` such that `A = U(0, _, _)` and `B = U(1, _, _)`, we can define a new operation representing the integral of `U` at time $t$ by generating sequences of the form</span></span>

```qsharp
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
U(0, time / Float(nSteps), target);
U(1, time / Float(nSteps), target);
// ...
```

<span data-ttu-id="b6b56-156">此时，我们现在可以了解 Trotter – Suzuki 扩展，*根本不需引用量程机制*。</span><span class="sxs-lookup"><span data-stu-id="b6b56-156">At this point, we can now reason about the Trotter–Suzuki expansion *without reference to quantum mechanics at all*.</span></span>
<span data-ttu-id="b6b56-157">此扩展实际上是一个由 $ \eqref{eq： trotter-suzuki-0} $ 使用的特殊迭代模式。</span><span class="sxs-lookup"><span data-stu-id="b6b56-157">The expansion is effectively a very particular iteration pattern motivated by $\eqref{eq:trotter-suzuki-0}$.</span></span>
<span data-ttu-id="b6b56-158">此迭代模式的实现方式 <xref:microsoft.quantum.canon.decomposeintotimestepsca> 如下：</span><span class="sxs-lookup"><span data-stu-id="b6b56-158">This iteration pattern is implemented by <xref:microsoft.quantum.canon.decomposeintotimestepsca>:</span></span>

```qsharp
// The 2 indicates how many terms we need to decompose,
// while the 1 indicates that we are using the
// first-order Trotter–Suzuki decomposoition.
DecomposeIntoTimeStepsCA((2, U), 1);
```

<span data-ttu-id="b6b56-159">的签名 `DecomposeIntoTimeStepsCA` 遵循 Q # 中的一种常见模式，其中，可以通过数组或动态计算元素进行备份的集合由其第一个元素是指示其长度的值的元组表示 `Int` 。</span><span class="sxs-lookup"><span data-stu-id="b6b56-159">The signature of `DecomposeIntoTimeStepsCA` follows a common pattern in Q#, where collections that may be backed either by arrays or by something which compute elements on the fly are represented by tuples whose first elements are `Int` values indicating their lengths.</span></span>

## <a name="putting-it-together-controlling-operations"></a><span data-ttu-id="b6b56-160">将其放在一起：控制操作</span><span class="sxs-lookup"><span data-stu-id="b6b56-160">Putting it Together: Controlling Operations</span></span> ##

<span data-ttu-id="b6b56-161">最后，canon 将 `Controlled` 通过提供额外的条件量程运算方法，在函子上构建。</span><span class="sxs-lookup"><span data-stu-id="b6b56-161">Finally, the canon builds on the `Controlled` functor by providing additional ways to condition quantum operations.</span></span>
<span data-ttu-id="b6b56-162">对于除 $ \ket{0\cdots 0} $ 之外的计算基础状态，通常情况下，尤其是在量程算法中。</span><span class="sxs-lookup"><span data-stu-id="b6b56-162">It is common, especially in quantum arithmetic, to condition operations on computational basis states other than $\ket{0\cdots 0}$.</span></span>
<span data-ttu-id="b6b56-163">使用上述控制操作和函数，我们可以在单个语句中使用更常见的量程情况。</span><span class="sxs-lookup"><span data-stu-id="b6b56-163">Using the control operations and functions introduced above, we can more general quantum conditions in a single statement.</span></span>
<span data-ttu-id="b6b56-164">接下来，我们来看看它是如何 <xref:microsoft.quantum.canon.controlledonbitstring> （sans 类型参数）的，接下来我们将逐一细分。</span><span class="sxs-lookup"><span data-stu-id="b6b56-164">Let's jump in to how <xref:microsoft.quantum.canon.controlledonbitstring> does it (sans type parameters), then we'll break down the pieces one by one.</span></span>
<span data-ttu-id="b6b56-165">我们需要做的第一件事就是定义一个操作，该操作实际上会在任意计算基础状态上实现控件的负载大幅提升。</span><span class="sxs-lookup"><span data-stu-id="b6b56-165">The first thing we'll need to do is to define an operation which actually does the heavy lifting of implementing the control on arbitrary computational basis states.</span></span>
<span data-ttu-id="b6b56-166">但我们不会直接调用此操作，因此我们将添加 `_` 到名称的开头，以指示它是其他地方构造的实现。</span><span class="sxs-lookup"><span data-stu-id="b6b56-166">We won't call this operation directly, however, and so we add `_` to the beginning of the name to indicate that it's an implementation of another construct elsewhere.</span></span>

```qsharp
operation _ControlledOnBitString(
    bits : Bool[],
    oracle: (Qubit[] => Unit is Adj + Ctl),
    controlRegister : Qubit[],
    targetRegister: Qubit[])
: Unit is Adj + Ctl
```

<span data-ttu-id="b6b56-167">请注意，我们采用一个表示为数组的位字符串 `Bool` ，用于指定要应用于我们所提供的操作的调节 `oracle` 。</span><span class="sxs-lookup"><span data-stu-id="b6b56-167">Note that we take a string of bits, represented as a `Bool` array, that we use to specify the conditioning that we want to apply to the operation `oracle` that we are given.</span></span>
<span data-ttu-id="b6b56-168">由于此操作实际上是直接执行应用程序，因此我们还需要获取控件和目标寄存器，这两者都在此处表示为 `Qubit[]` 。</span><span class="sxs-lookup"><span data-stu-id="b6b56-168">Since this operation actually does the application directly, we also need to take the control and target registers, both represented here as `Qubit[]`.</span></span>

<span data-ttu-id="b6b56-169">接下来，我们注意到，通过将 $ \ket{\vec{s}} $ 转换为 $ \ket{0\cdots 0} $，在计算基础状态 $ \ket{\vec{s}} = \ket{s \_ 0 s \_ 1 \dots .. s \_ {n-1}} $ 上控制可实现位字符串 $ \vec{s} $。</span><span class="sxs-lookup"><span data-stu-id="b6b56-169">Next, we note that controlling on the computational basis state $\ket{\vec{s}} = \ket{s\_0 s\_1 \dots s\_{n - 1}}$ for a bit string $\vec{s}$ can be realized by transforming $\ket{\vec{s}}$ into $\ket{0\cdots 0}$.</span></span>
<span data-ttu-id="b6b56-170">具体而言，$ \ket{\vec{s}} = X ^ {s \_ 0} \Otimes x ^ {s \_ 1} \otimes \Cdots \otimes x ^ {s \_ {n-1}} \ket{0\cdots 0} $。</span><span class="sxs-lookup"><span data-stu-id="b6b56-170">In particular, $\ket{\vec{s}} = X^{s\_0} \otimes X^{s\_1} \otimes \cdots \otimes X^{s\_{n - 1}} \ket{0\cdots 0}$.</span></span>
<span data-ttu-id="b6b56-171">由于 $X ^ {\dagger} = X $，这意味着 $ \ket{0\dots 0} = X ^ {s \_ 0} \Otimes X ^ {s \_ } \otimes \Cdots \otimes x ^ {s \_ {n-1}} \ket{\vec{s}} $。</span><span class="sxs-lookup"><span data-stu-id="b6b56-171">Since $X^{\dagger} = X$, this implies that $\ket{0\dots 0} = X^{s\_0} \otimes X^{s\_1} \otimes \cdots \otimes X^{s\_{n - 1}} \ket{\vec{s}}$.</span></span>
<span data-ttu-id="b6b56-172">因此，我们可以应用 $P = X ^ {s \_ 0} \Otimes x ^ {s \_ 1} \otimes \Cdots \otimes x ^ {s \_ {n-1}} $，应用 `Controlled oracle` 并转换回 $ \vec{s} $。</span><span class="sxs-lookup"><span data-stu-id="b6b56-172">Thus, we can apply $P = X^{s\_0} \otimes X^{s\_1} \otimes \cdots \otimes X^{s\_{n - 1}}$, apply `Controlled oracle`, and transform back to $\vec{s}$.</span></span>
<span data-ttu-id="b6b56-173">此构造是准确的 `ApplyWith` ，因此，我们会相应地编写新操作的正文：</span><span class="sxs-lookup"><span data-stu-id="b6b56-173">This construction is precisely `ApplyWith`, so we write the body of our new operation accordingly:</span></span>

```qsharp
{
    ApplyWithCA(
        ApplyPauliFromBitString(PauliX, false, bits, _),
        (Controlled oracle)(_, targetRegister),
        controlRegister
    );
}
```

<span data-ttu-id="b6b56-174">在这里，我们已使用 <xref:microsoft.quantum.canon.applypaulifrombitstring> 应用 $P $，在其目标上进行部分应用，以便与一起使用 `ApplyWith` 。</span><span class="sxs-lookup"><span data-stu-id="b6b56-174">Here, we have used <xref:microsoft.quantum.canon.applypaulifrombitstring> to apply $P$, partially applying over its target for use with `ApplyWith`.</span></span>
<span data-ttu-id="b6b56-175">但请注意，我们需要将*控制*寄存器转换为所需的格式，因此我们 `(Controlled oracle)` 在*目标*上部分应用内部操作。</span><span class="sxs-lookup"><span data-stu-id="b6b56-175">Note, however, that we need to transform the *control* register to our desired form, so we partially apply the inner operation `(Controlled oracle)` on the *target*.</span></span>
<span data-ttu-id="b6b56-176">这会使 `ApplyWith` 控制寄存器与 $P $ 的方括号完全相同。</span><span class="sxs-lookup"><span data-stu-id="b6b56-176">This leaves `ApplyWith` acting to bracket the control register with $P$, exactly as we desired.</span></span>

<span data-ttu-id="b6b56-177">此时，我们可以这样做，但我们的新操作并不像应用函子，unsatisfying `Controlled` 。</span><span class="sxs-lookup"><span data-stu-id="b6b56-177">At this point, we could be done, but it is somehow unsatisfying that our new operation does not "feel" like applying the `Controlled` functor.</span></span>
<span data-ttu-id="b6b56-178">因此，我们通过编写一个函数来控制新的控制流概念，该函数将 oracle 控制在一起并返回一个新的操作。</span><span class="sxs-lookup"><span data-stu-id="b6b56-178">Thus, we finish defining our new control flow concept by writing a function that takes the oracle to be controlled and that returns a new operation.</span></span>
<span data-ttu-id="b6b56-179">通过这种方式，我们的新函数的外观和感觉非常类似 `Controlled` ，其中阐释了使用 Q # 和 canon 可以轻松定义功能强大的新控制流构造：</span><span class="sxs-lookup"><span data-stu-id="b6b56-179">In this way, our new function looks and feels very much like `Controlled`, illustrating that we can easily define powerful new control flow constructs using Q# and the canon together:</span></span>

```qsharp
function ControlledOnBitString(
    bits : Bool[],
    oracle: (Qubit[] => Unit is Adj + Ctl))
: ((Qubit[], Qubit[]) => Unit is Adj + Ctl) {
    return _ControlledOnBitString(bits, oracle, _, _);
}
```
