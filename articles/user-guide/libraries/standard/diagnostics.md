---
title: '标准库中的诊断 :::no-loc(Q#):::'
description: '了解 :::no-loc(Q#)::: 用于在量程程序中捕获错误或错误的标准库中的诊断功能和操作。'
author: cgranade
uid: microsoft.quantum.libraries.diagnostics
ms.author: chgranad
ms.topic: article
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: 1ab9b77c7536a1860064110810371d3a68e95b40
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92690846"
---
# <a name="diagnostics"></a><span data-ttu-id="0d069-103">诊断</span><span class="sxs-lookup"><span data-stu-id="0d069-103">Diagnostics</span></span> #

<span data-ttu-id="0d069-104">与传统开发一样，能够在量程程序中诊断错误和错误非常重要。</span><span class="sxs-lookup"><span data-stu-id="0d069-104">As with classical development, it is important to be able to diagnose mistakes and errors in quantum programs.</span></span>
<span data-ttu-id="0d069-105">:::no-loc(Q#):::标准库提供各种不同的方法来确保量程程序的正确性，如中所述 <xref:microsoft.quantum.guide.testingdebugging> 。</span><span class="sxs-lookup"><span data-stu-id="0d069-105">The :::no-loc(Q#)::: standard libraries provide a variety of different ways to ensure the correctness of quantum programs, as detailed in <xref:microsoft.quantum.guide.testingdebugging>.</span></span>
<span data-ttu-id="0d069-106">很多情况下，这种支持采用函数和操作的形式，可指示目标计算机向宿主程序或开发人员提供额外的诊断信息，或强制执行由函数或操作调用表示的条件和固定条件的正确性。</span><span class="sxs-lookup"><span data-stu-id="0d069-106">Largely speaking, this support comes in the form of functions and operations that either instruct the target machine to provide additional diagnostic information to the host program or developer, or enforce the correctness of conditions and invariants expressed by the function or operation call.</span></span>

## <a name="machine-diagnostics"></a><span data-ttu-id="0d069-107">计算机诊断</span><span class="sxs-lookup"><span data-stu-id="0d069-107">Machine Diagnostics</span></span> ##

<span data-ttu-id="0d069-108">可以通过使用 <xref:Microsoft.Quantum.Intrinsic.Message> 函数以依赖于计算机的方式记录消息来获取有关传统值的诊断。</span><span class="sxs-lookup"><span data-stu-id="0d069-108">Diagnostics about classical values can be obtained by using the <xref:Microsoft.Quantum.Intrinsic.Message> function to log a message in a machine-dependent way.</span></span>
<span data-ttu-id="0d069-109">默认情况下，这会将字符串写入控制台。</span><span class="sxs-lookup"><span data-stu-id="0d069-109">By default, this writes the string to the console.</span></span>
<span data-ttu-id="0d069-110">与内插字符串一起使用， <xref:Microsoft.Quantum.Intrinsic.Message> 可以轻松地报告有关传统值的诊断信息：</span><span class="sxs-lookup"><span data-stu-id="0d069-110">Used together with interpolated strings, <xref:Microsoft.Quantum.Intrinsic.Message> makes it easy to report diagnostic information about classical values:</span></span>

```:::no-loc(Q#):::
let angle = Microsoft.Quantum.Math.PI() * 2.0 / 3.0;
Message($"About to rotate by an angle of {angle}...");
```

> [!NOTE]
> <span data-ttu-id="0d069-111">`Message` 具有签名 `(String -> Unit)` ，而不能在中观察发出调试日志消息的 :::no-loc(Q#)::: 。</span><span class="sxs-lookup"><span data-stu-id="0d069-111">`Message` has signature `(String -> Unit)`, again representing that emitting a debug log message cannot be observed from within :::no-loc(Q#):::.</span></span>

<span data-ttu-id="0d069-112"><xref:Microsoft.Quantum.Diagnostics.DumpMachine>和 <xref:Microsoft.Quantum.Diagnostics.DumpRegister> callables 指示目标计算机提供有关当前已分配的所有 qubits 的诊断信息，或分别提供有关 qubits 的特定寄存器的诊断信息。</span><span class="sxs-lookup"><span data-stu-id="0d069-112">The <xref:Microsoft.Quantum.Diagnostics.DumpMachine> and <xref:Microsoft.Quantum.Diagnostics.DumpRegister> callables instruct target machines to provide diagnostic information about all currently allocated qubits or about a specific register of qubits, respectively.</span></span>
<span data-ttu-id="0d069-113">每个目标计算机因提供的诊断信息而异，以响应转储指令。</span><span class="sxs-lookup"><span data-stu-id="0d069-113">Each target machine varies in what diagnostic information is provided in response to a dump instruction.</span></span>
<span data-ttu-id="0d069-114">例如， [完整状态模拟器](xref:microsoft.quantum.machines.full-state-simulator) 目标虚拟机为主机程序提供了其内部使用的状态向量，以表示寄存器 qubits。</span><span class="sxs-lookup"><span data-stu-id="0d069-114">The [full state simulator](xref:microsoft.quantum.machines.full-state-simulator) target machine, for instance, provides the host program with the state vector that it uses internally to represent a register of qubits.</span></span>
<span data-ttu-id="0d069-115">相比之下， [Toffoli 模拟器](xref:microsoft.quantum.machines.toffoli-simulator) 目标计算机为每个 qubit 提供一个传统位。</span><span class="sxs-lookup"><span data-stu-id="0d069-115">By comparison, the [Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator) target machine provides a single classical bit for each qubit.</span></span>

 <span data-ttu-id="0d069-116">若要了解有关 [完整状态模拟器的](xref:microsoft.quantum.machines.full-state-simulator)输出的详细信息 `DumpMachine` ，请参阅 [测试和调试一文](xref:microsoft.quantum.guide.testingdebugging#dump-functions)的 "转储函数" 一节。</span><span class="sxs-lookup"><span data-stu-id="0d069-116">To learn more about the [full state simulator's](xref:microsoft.quantum.machines.full-state-simulator) `DumpMachine` output, take a look at the dump functions section of our [testing and debugging article](xref:microsoft.quantum.guide.testingdebugging#dump-functions).</span></span>


## <a name="facts-and-assertions"></a><span data-ttu-id="0d069-117">事实和断言</span><span class="sxs-lookup"><span data-stu-id="0d069-117">Facts and Assertions</span></span> ##

<span data-ttu-id="0d069-118">如 [测试和调试](xref:microsoft.quantum.guide.testingdebugging)中所述，可以将具有签名的函数或操作 `Unit -> Unit` `Unit => Unit` 分别标记为 *单元测试* 。</span><span class="sxs-lookup"><span data-stu-id="0d069-118">As discussed in [Testing and Debugging](xref:microsoft.quantum.guide.testingdebugging), a function or operation with signature `Unit -> Unit` or `Unit => Unit`, respectively, can be marked as a *unit test* .</span></span>
<span data-ttu-id="0d069-119">每个单元测试通常包含一个小型量程计划，以及一个或多个检查该程序的正确性的条件。</span><span class="sxs-lookup"><span data-stu-id="0d069-119">Each unit test generally consists of a small quantum program, along with one or more conditions that check the correctness of that program.</span></span>
<span data-ttu-id="0d069-120">这些条件可采用以下两种形式之一：检查输入的值或 _断言_ ，这些 _事实_ 检查作为输入传递的一个或多个 qubits 的状态。</span><span class="sxs-lookup"><span data-stu-id="0d069-120">These conditions can come in the form of either _facts_ , which check the values of their inputs, or _assertions_ , which check the states of one or more qubits passed as input.</span></span>

<span data-ttu-id="0d069-121">例如， `EqualityFactI(1 + 1, 2, "1 + 1 != 2")` 表示 $1 + 1 = $2 的数学事实，而 `AssertQubit(One, qubit)` 表示测量 `qubit` 将返回具有确定性的条件的条件 `One` 。</span><span class="sxs-lookup"><span data-stu-id="0d069-121">For example, `EqualityFactI(1 + 1, 2, "1 + 1 != 2")` represents the mathematical fact that $1 + 1 = 2$, while `AssertQubit(One, qubit)` represents the condition that measuring `qubit` will return a `One` with certainty.</span></span>
<span data-ttu-id="0d069-122">在前一种情况下，我们可以检查只给定其值的条件的正确性，而在后一种情况下，我们必须知道 qubit 的状态，以便评估断言。</span><span class="sxs-lookup"><span data-stu-id="0d069-122">In the former case, we can check the correctness of the condition given only its values, while in the latter, we must know something about the state of the qubit in order to evaluate the assertion.</span></span>

<span data-ttu-id="0d069-123">:::no-loc(Q#):::标准库提供了若干不同的函数来表示事实，其中包括：</span><span class="sxs-lookup"><span data-stu-id="0d069-123">The :::no-loc(Q#)::: standard libraries provide several different functions for representing facts, including:</span></span>

- <xref:Microsoft.Quantum.Diagnostics.Fact>
- <xref:Microsoft.Quantum.Diagnostics.EqualityWithinToleranceFact>
- <xref:Microsoft.Quantum.Diagnostics.NearEqualityFactC>
- <xref:Microsoft.Quantum.Diagnostics.EqualityFactI>


### <a name="testing-qubit-states"></a><span data-ttu-id="0d069-124">测试 Qubit 状态</span><span class="sxs-lookup"><span data-stu-id="0d069-124">Testing Qubit States</span></span> ###

<span data-ttu-id="0d069-125">实际上，断言依赖于这一事实，即，对量子机制的传统模拟不需要遵循非 [克隆定理](https://arxiv.org/abs/quant-ph/9607018)，因此，我们可以在为目标计算机使用模拟器时进行 unphysical 测量和断言。</span><span class="sxs-lookup"><span data-stu-id="0d069-125">In practice, assertions rely on the fact that classical simulations of quantum mechanics need not obey the [no-cloning theorem](https://arxiv.org/abs/quant-ph/9607018), such that we can make unphysical measurements and assertions when using a simulator for our target machine.</span></span>
<span data-ttu-id="0d069-126">因此，可以在部署硬件之前，在传统模拟器上测试各个操作。</span><span class="sxs-lookup"><span data-stu-id="0d069-126">Thus, we can test individual operations on a classical simulator before deploying on hardware.</span></span>
<span data-ttu-id="0d069-127">在不允许评估断言的目标计算机上， <xref:Microsoft.Quantum.Diagnostics.AssertMeasurement> 可以安全地忽略对的调用。</span><span class="sxs-lookup"><span data-stu-id="0d069-127">On target machines which do not allow evaluation of assertions, calls to <xref:Microsoft.Quantum.Diagnostics.AssertMeasurement> can be safely ignored.</span></span>

<span data-ttu-id="0d069-128">更常见的情况是，在 <xref:Microsoft.Quantum.Diagnostics.AssertMeasurement> 给定 Pauli 基础上测量给定 qubits 的操作断言将始终具有给定的结果。</span><span class="sxs-lookup"><span data-stu-id="0d069-128">More generally, the <xref:Microsoft.Quantum.Diagnostics.AssertMeasurement> operation asserts that measuring the given qubits in the given Pauli basis will always have the given result.</span></span>
<span data-ttu-id="0d069-129">如果断言失败，则运行将通过调用 `fail` 给定的消息结束。</span><span class="sxs-lookup"><span data-stu-id="0d069-129">If the assertion fails, the run ends by calling `fail` with the given message.</span></span>
<span data-ttu-id="0d069-130">默认情况下，不实现此操作;可支持它的模拟器应该提供执行运行时检查的实现。</span><span class="sxs-lookup"><span data-stu-id="0d069-130">By default, this operation is not implemented; simulators that can support it should provide an implementation that performs runtime checking.</span></span>
<span data-ttu-id="0d069-131">`AssertMeasurement` 具有签名 `((Pauli[], Qubit[], Result, String) -> ())` 。</span><span class="sxs-lookup"><span data-stu-id="0d069-131">`AssertMeasurement` has signature `((Pauli[], Qubit[], Result, String) -> ())`.</span></span>
<span data-ttu-id="0d069-132">由于 `AssertMeasurement` 是一个带有空元组作为其输出类型的函数，因此不能在 `AssertMeasurement` 程序中使用具有调用的效果 :::no-loc(Q#)::: 。</span><span class="sxs-lookup"><span data-stu-id="0d069-132">Since `AssertMeasurement` is a function with an empty tuple as its output type, no effects from having called `AssertMeasurement` are observable within a :::no-loc(Q#)::: program.</span></span>

<span data-ttu-id="0d069-133">在 <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> 给定 Pauli 基础上测量给定 qubits 的操作函数断言在某种程度上具有给定概率的给定结果。</span><span class="sxs-lookup"><span data-stu-id="0d069-133">The <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> operation function asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.</span></span>
<span data-ttu-id="0d069-134">容差是加法 (例如 `abs(expected-actual) < tol`) 。</span><span class="sxs-lookup"><span data-stu-id="0d069-134">Tolerance is additive (for example, `abs(expected-actual) < tol`).</span></span>
<span data-ttu-id="0d069-135">如果断言失败，则运行将通过调用 `fail` 给定的消息结束。</span><span class="sxs-lookup"><span data-stu-id="0d069-135">If the assertion fails, the run ends by calling `fail` with the given message.</span></span>
<span data-ttu-id="0d069-136">默认情况下，不实现此操作;可支持它的模拟器应该提供执行运行时检查的实现。</span><span class="sxs-lookup"><span data-stu-id="0d069-136">By default, this operation is not implemented; simulators that can support it should provide an implementation that performs runtime checking.</span></span>
<span data-ttu-id="0d069-137">`AssertMeasurementProbability` 具有签名 `((Pauli[], Qubit[], Result, Double, String, Double) -> Unit)` 。</span><span class="sxs-lookup"><span data-stu-id="0d069-137">`AssertMeasurementProbability` has signature `((Pauli[], Qubit[], Result, Double, String, Double) -> Unit)`.</span></span> <span data-ttu-id="0d069-138">第一个 `Double` 参数提供所需的结果概率，第二个参数为容差。</span><span class="sxs-lookup"><span data-stu-id="0d069-138">The first of `Double` parameters gives the desired probability of the result, and the second one the tolerance.</span></span>

<span data-ttu-id="0d069-139">我们不仅可以使用断言单个度量值，还可以使用模拟器用来表示 qubit 的内部状态的传统信息适合复制，这样我们就不需要实际执行度量来测试断言。</span><span class="sxs-lookup"><span data-stu-id="0d069-139">We can do more than assert a single measurement, using that the classical information used by a simulator to represent the internal state of a qubit is amenable to copying, such that we do not need to actually perform a measurement to test our assertion.</span></span>
<span data-ttu-id="0d069-140">具体而言，这使我们能够考虑到在实际硬件上无法进行的 *不兼容* 指标。</span><span class="sxs-lookup"><span data-stu-id="0d069-140">In particular, this allows us to reason about *incompatible* measurements that would be impossible on actual hardware.</span></span>

<span data-ttu-id="0d069-141">假设 `P : Qubit => Unit` 是一项操作，用于在其输入处于状态 $ \ket $ 时准备状态 $ \ket{\psi} $ {0} 。</span><span class="sxs-lookup"><span data-stu-id="0d069-141">Suppose that `P : Qubit => Unit` is an operation intended to prepare the state $\ket{\psi}$ when its input is in the state $\ket{0}$.</span></span>
<span data-ttu-id="0d069-142">让 $ \ket{\psi '} $ 是准备的实际状态 `P` 。</span><span class="sxs-lookup"><span data-stu-id="0d069-142">Let $\ket{\psi'}$ be the actual state prepared by `P`.</span></span>
<span data-ttu-id="0d069-143">然后，当且仅当 $ \ket{\psi} $ 所描述的轴中的 $ \ket{\psi '} $ 度量 $ '} $ 时，$ \ket{\psi} = \ket{\psi '} $ 总是返回 `Zero` 。</span><span class="sxs-lookup"><span data-stu-id="0d069-143">Then, $\ket{\psi} = \ket{\psi'}$ if and only if measuring $\ket{\psi'}$ in the axis described by $\ket{\psi}$ always returns `Zero`.</span></span>
<span data-ttu-id="0d069-144">也就是说，如果且仅当} \braket{\psi | \psi '} = 1 时，\begin{align} \ket{\psi} = \ket{\psi '} \text{。</span><span class="sxs-lookup"><span data-stu-id="0d069-144">That is, \begin{align} \ket{\psi} = \ket{\psi'} \text{ if and only if } \braket{\psi | \psi'} = 1.</span></span>
<span data-ttu-id="0d069-145">\end{align} 使用在 prelude 中定义的基元运算，可以直接执行一个度量值，该度量值在 `Zero` $ \ket{\psi} $ 是 Pauli 运算符之一的 eigenstate 时返回。</span><span class="sxs-lookup"><span data-stu-id="0d069-145">\end{align} Using the primitive operations defined in the prelude, we can directly perform a measurement that returns `Zero` if $\ket{\psi}$ is an eigenstate of one of the Pauli operators.</span></span>


<span data-ttu-id="0d069-146">如果要 <xref:Microsoft.Quantum.Diagnostics.AssertQubit> 测试断言 $ \ket{\psi} = \ket $，该操作将提供一个特别有用的速记 {0} 。</span><span class="sxs-lookup"><span data-stu-id="0d069-146">The operation <xref:Microsoft.Quantum.Diagnostics.AssertQubit> provides a particularly useful shorthand to do so in the case that we wish to test the assertion $\ket{\psi} = \ket{0}$.</span></span>
<span data-ttu-id="0d069-147">这种情况很常见，例如，当我们 uncomputed 将 ancilla qubits 返回到 $ \ket {0} $ 之前，则将其释放。</span><span class="sxs-lookup"><span data-stu-id="0d069-147">This is common, for instance, when we have uncomputed to return ancilla qubits to $\ket{0}$ before releasing them.</span></span>
<span data-ttu-id="0d069-148">{0}如果希望断言两个状态准备 `P` 和 `Q` 操作都准备好相同的状态，并且在支持时，则可以对 $ \ket $ 进行断言 `Q` `Adjoint` 。</span><span class="sxs-lookup"><span data-stu-id="0d069-148">Asserting against $\ket{0}$ is also useful when we wish to assert that two state preparation `P` and `Q` operations both prepare the same state, and when `Q` supports `Adjoint`.</span></span>
<span data-ttu-id="0d069-149">特别是，</span><span class="sxs-lookup"><span data-stu-id="0d069-149">In particular,</span></span>

```qsharp
using (register = Qubit()) {
    P(register);
    Adjoint Q(register);

    AssertQubit(Zero, register);
}
```

<span data-ttu-id="0d069-150">但是，更常见的情况是，我们无法访问断言与 Pauli 运算符的 eigenstates 不一致的状态。</span><span class="sxs-lookup"><span data-stu-id="0d069-150">More generally, however, we may not have access to assertions about states that do not coincide with eigenstates of Pauli operators.</span></span>
<span data-ttu-id="0d069-151">例如，$ \ket{\psi} = ( \ket {0} + e ^ {i \pi/8} \ket {1}) /\sqrt {2} $ 不是任何 eigenstate 运算符的 Pauli，因此不能使用 <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> 唯一确定状态 $ \ket{\psi '} $ 等于 $ \ket{\psi} $。</span><span class="sxs-lookup"><span data-stu-id="0d069-151">For example, $\ket{\psi} = (\ket{0} + e^{i \pi / 8} \ket{1}) / \sqrt{2}$ is not an eigenstate of any Pauli operator, such that we cannot use <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> to uniquely determine that a state $\ket{\psi'}$ is equal to $\ket{\psi}$.</span></span>
<span data-ttu-id="0d069-152">相反，我们必须将断言 $ \ket{\psi '} = \ket{\psi} $ 分解为可使用模拟器支持的基元直接测试的假设。</span><span class="sxs-lookup"><span data-stu-id="0d069-152">Instead, we must decompose the assertion $\ket{\psi'} = \ket{\psi}$ into assumptions that can be directly tested using  the primitives supported by our simulator.</span></span>
<span data-ttu-id="0d069-153">为此，请将 $ \ket{\psi} = \alpha \ket {0} + \beta \ket {1} $ 用于复数 $ \alpha = a \_ r + a \_ i i $ 和 $ \beta $。</span><span class="sxs-lookup"><span data-stu-id="0d069-153">To do so, let $\ket{\psi} = \alpha \ket{0} + \beta \ket{1}$ for complex numbers $\alpha = a\_r + a\_i i$ and $\beta$.</span></span>
<span data-ttu-id="0d069-154">请注意，此表达式需要四个实数 $ \{ a \_ r、 \_ i、b \_ r、b \_ i \} $ 来指定，因为每个复数都可以表示为实部和虚部的总和。</span><span class="sxs-lookup"><span data-stu-id="0d069-154">Note that this expression requires four real numbers $\{a\_r, a\_i, b\_r, b\_i\}$ to specify, as each complex number can be expressed as the sum of a real and imaginary part.</span></span>
<span data-ttu-id="0d069-155">不过，由于全局阶段，我们可以选择 $a \_ i = $0，因此，我们只需三个实数即可唯一指定 qubit 状态。</span><span class="sxs-lookup"><span data-stu-id="0d069-155">Due to the global phase, however, we can choose $a\_i = 0$, such that we only need three real numbers to uniquely specify a single-qubit state.</span></span>

<span data-ttu-id="0d069-156">因此，需要指定三个断言，它们彼此独立，以便断言所需的状态。</span><span class="sxs-lookup"><span data-stu-id="0d069-156">Thus, we need to specify three assertions which are independent of each other in order to assert the state that we expect.</span></span>
<span data-ttu-id="0d069-157">为此，我们需要找 `Zero` 出每个 Pauli 度量值为 $ \alpha $ 和 $ \beta $ 的观察概率，并分别对每个度量值进行断言。</span><span class="sxs-lookup"><span data-stu-id="0d069-157">We do so by finding the probability of observing `Zero` for each Pauli measurement given $\alpha$ and $\beta$, and asserting each independently.</span></span>
<span data-ttu-id="0d069-158">允许 $x $、$y $ 和 $z， `Result` 分别为 Pauli $X $、$Y $ 和 $Z $ 度量值。</span><span class="sxs-lookup"><span data-stu-id="0d069-158">Let $x$, $y$, and $z$ be `Result` values for Pauli $X$, $Y$, and $Z$ measurements respectively.</span></span>
<span data-ttu-id="0d069-159">然后，对量子度量使用可能性函数 \begin{align} \Pr (x = \texttt{Zero} |\alpha，\beta) & = \frac12 + a \_ r b \_ r + a \_ i b \_ i \\ \\ \Pr (y = \texttt{Zero} | \alpha，\beta) & = \frac12 + a \_ r b \_ i a \_ i b \_ r \\ \\ \Pr (z = \texttt{Zero} | \alpha，\beta) & = \frac12\left ( 1 + a \_ r ^ 2 + a i ^ 2 \_ + b \_ r ^ 2 + b \_ i ^ 2 \right) 。</span><span class="sxs-lookup"><span data-stu-id="0d069-159">Then, using the likelihood function for quantum measurements, \begin{align} \Pr(x = \texttt{Zero} | \alpha, \beta) & = \frac12 + a\_r b\_r + a\_i b\_i \\\\ \Pr(y = \texttt{Zero} | \alpha, \beta) & = \frac12 + a\_r b\_i - a\_i b\_r \\\\ \Pr(z = \texttt{Zero} | \alpha, \beta) & = \frac12\left( 1 + a\_r^2 + a\_i^2 + b\_r^2 + b\_i^2 \right).</span></span>
<span data-ttu-id="0d069-160">\end{align}</span><span class="sxs-lookup"><span data-stu-id="0d069-160">\end{align}</span></span>

<span data-ttu-id="0d069-161"><xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance>操作以类型的值的形式实现了 $ \alpha $ 和 $ \beta $ 的表示形式 <xref:Microsoft.Quantum.Math.Complex> 。</span><span class="sxs-lookup"><span data-stu-id="0d069-161">The <xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance> operation implements these assertions given representations of $\alpha$ and $\beta$ as values of type <xref:Microsoft.Quantum.Math.Complex>.</span></span>
<span data-ttu-id="0d069-162">当预期状态可数学计算时，这非常有用。</span><span class="sxs-lookup"><span data-stu-id="0d069-162">This is helpful when the expected state can be computed mathematically.</span></span>

### <a name="asserting-equality-of-quantum-operations"></a><span data-ttu-id="0d069-163">断言量程运算的相等性</span><span class="sxs-lookup"><span data-stu-id="0d069-163">Asserting Equality of Quantum Operations</span></span> ###

<span data-ttu-id="0d069-164">到目前为止，我们关注的是用于准备特定状态的测试操作。</span><span class="sxs-lookup"><span data-stu-id="0d069-164">Thus far, we have been concerned with testing operations which are intended to prepare particular states.</span></span>
<span data-ttu-id="0d069-165">不过，通常情况下，我们对操作如何处理任意输入（而不是单个固定的输入）感兴趣。</span><span class="sxs-lookup"><span data-stu-id="0d069-165">Often, however, we are interested in how an operation acts for arbitrary inputs rather than for a single fixed input.</span></span>
<span data-ttu-id="0d069-166">例如，假设我们实现了 `U : ((Double, Qubit[]) => () : Adjoint)` 与一系列单一运算符对应的操作 $U (t) $，并且提供了一个显式块， `adjoint` 而不是使用 `adjoint auto` 。</span><span class="sxs-lookup"><span data-stu-id="0d069-166">For example, suppose we have implemented an operation `U : ((Double, Qubit[]) => () : Adjoint)` corresponding to a family of unitary operators $U(t)$, and have provided an explicit `adjoint` block instead of using `adjoint auto`.</span></span>
<span data-ttu-id="0d069-167">如果) $ 表示演化时间，我们可能会有兴趣断言 $U ^ \dagger (t) = U (-t $t $。</span><span class="sxs-lookup"><span data-stu-id="0d069-167">We may be interested in asserting that $U^\dagger(t) = U(-t)$, as expected if $t$ represents an evolution time.</span></span>

<span data-ttu-id="0d069-168">广泛地说，有两种不同的策略，我们可以在使断言成为两个操作并执行相同的操作 `U` `V` 。</span><span class="sxs-lookup"><span data-stu-id="0d069-168">Broadly speaking, there are two different strategies that we can follow in making the assertion that two operations `U` and `V` act identically.</span></span>
<span data-ttu-id="0d069-169">首先，可以检查 `U(target); (Adjoint V)(target);` 以给定的方式保留每个状态。</span><span class="sxs-lookup"><span data-stu-id="0d069-169">First, we can check that `U(target); (Adjoint V)(target);` preserves each state in a given basis.</span></span>
<span data-ttu-id="0d069-170">其次，我们可以检查是否 `U(target); (Adjoint V)(target);` 在放大状态的一半上，是否保留了牵连。</span><span class="sxs-lookup"><span data-stu-id="0d069-170">Second, we can check that `U(target); (Adjoint V)(target);` acting on half of an entangled state preserves that entanglement.</span></span>
<span data-ttu-id="0d069-171">这些策略是通过 canon 操作 <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace> 和分别实现的 <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced> 。</span><span class="sxs-lookup"><span data-stu-id="0d069-171">These strategies are implemented by the canon operations <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace> and <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced>, respectively.</span></span>

> [!NOTE]
> <span data-ttu-id="0d069-172">上面所述的引用断言基于 [Choi – Jamiłkowski isomorphism](https://en.wikipedia.org/wiki/Channel-state_duality)，这是一个数学框架，该框架将 $n $ qubits 上的操作与 $ 2n $ 放大上的 qubits 状态关联起来。</span><span class="sxs-lookup"><span data-stu-id="0d069-172">The referenced assertion discussed above works based on the [Choi–Jamiłkowski isomorphism](https://en.wikipedia.org/wiki/Channel-state_duality), a mathematical framework which relates operations on $n$ qubits to entangled states on $2n$ qubits.</span></span>
> <span data-ttu-id="0d069-173">具体而言，$n $ qubits 上的标识操作由放大状态 $ \ket{\ beta_ {00} } \mathrel{： =} ( \ket {00} + \ket {11}) /\sqrt $ $n $ 副本表示 {2} 。</span><span class="sxs-lookup"><span data-stu-id="0d069-173">In particular, the identity operation on $n$ qubits is represented by $n$ copies of the entangled state $\ket{\beta_{00}} \mathrel{:=} (\ket{00} + \ket{11}) / \sqrt{2}$.</span></span>
> <span data-ttu-id="0d069-174">操作 <xref:Microsoft.Quantum.Preparation.PrepareChoiState> 实现此 isomorphism，并准备一个表示给定操作的状态。</span><span class="sxs-lookup"><span data-stu-id="0d069-174">The operation <xref:Microsoft.Quantum.Preparation.PrepareChoiState> implements this isomorphism, preparing a state that represents a given operation.</span></span>

<span data-ttu-id="0d069-175">大致而言，这些策略可通过时间空间平衡来区分。</span><span class="sxs-lookup"><span data-stu-id="0d069-175">Roughly, these strategies are distinguished by a time–space tradeoff.</span></span>
<span data-ttu-id="0d069-176">循环访问每个输入状态需要额外的时间，而使用牵连作为引用需要存储其他 qubits。</span><span class="sxs-lookup"><span data-stu-id="0d069-176">Iterating through each input state takes additional time, while using entanglement as a reference requires storing additional qubits.</span></span>
<span data-ttu-id="0d069-177">如果某个操作实现可逆的传统操作，使其只对计算基础状态的行为感兴趣，则 <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlaceCompBasis> 测试此限制的一组输入的相等性。</span><span class="sxs-lookup"><span data-stu-id="0d069-177">In cases where an operation implements a reversible classical operation, such that we are only interested in its behavior on computational basis states, <xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlaceCompBasis> tests equality on this restricted set of inputs.</span></span>

> [!TIP]
> <span data-ttu-id="0d069-178">对输入状态的迭代由枚举操作和进行处理 <xref:Microsoft.Quantum.Canon.IterateThroughCartesianProduct> <xref:Microsoft.Quantum.Canon.IterateThroughCartesianPower> 。</span><span class="sxs-lookup"><span data-stu-id="0d069-178">The iteration over input states is handled by the enumeration operations <xref:Microsoft.Quantum.Canon.IterateThroughCartesianProduct> and <xref:Microsoft.Quantum.Canon.IterateThroughCartesianPower>.</span></span>
> <span data-ttu-id="0d069-179">这些操作更适用于将操作应用于两个或多个集之间笛卡尔积的每个元素。</span><span class="sxs-lookup"><span data-stu-id="0d069-179">These operations are useful more generally for applying an operation to each element of the Cartesian product between two or more sets.</span></span>

<span data-ttu-id="0d069-180">但更严重的是，这两种方法测试正在检查的操作的不同属性。</span><span class="sxs-lookup"><span data-stu-id="0d069-180">More critically, however, the two approaches test different properties of the operations under examination.</span></span>
<span data-ttu-id="0d069-181">由于就地断言多次调用每个操作，因此对每个输入状态一次，任何随机选项和测量结果可能在调用之间发生变化。</span><span class="sxs-lookup"><span data-stu-id="0d069-181">Since the in-place assertion calls each operation multiple times, once for each input state, any random choices and measurement results might change between calls.</span></span>
<span data-ttu-id="0d069-182">与此相反，引用的断言只调用一次每个操作一次，以便 *在一个拍摄中* 检查操作是否相等。</span><span class="sxs-lookup"><span data-stu-id="0d069-182">By contrast, the referenced assertion calls each operation exactly once, such that it checks that the operations are equal *in a single shot* .</span></span>
<span data-ttu-id="0d069-183">这两个测试可用于确保量程程序的正确性。</span><span class="sxs-lookup"><span data-stu-id="0d069-183">Both of these tests are useful in ensuring the correctness of quantum programs.</span></span>


## <a name="further-reading"></a><span data-ttu-id="0d069-184">深入阅读</span><span class="sxs-lookup"><span data-stu-id="0d069-184">Further Reading</span></span> ##

- <xref:microsoft.quantum.guide.testingdebugging>
- <xref:Microsoft.Quantum.Diagnostics>
