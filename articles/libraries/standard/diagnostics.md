---
title: 'Q # 标准库-诊断 |Microsoft Docs'
description: 'Q # 标准库-诊断'
author: cgranade
uid: microsoft.quantum.libraries.diagnostics
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: 67ec6780d8cbbda7223d46026a9df97cebc92b33
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820974"
---
# <a name="diagnostics"></a><span data-ttu-id="fa18c-103">诊断</span><span class="sxs-lookup"><span data-stu-id="fa18c-103">Diagnostics</span></span> #

<span data-ttu-id="fa18c-104">与传统开发一样，能够在量程程序中诊断错误和错误非常重要。</span><span class="sxs-lookup"><span data-stu-id="fa18c-104">As with classical development, it is important to be able to diagnose mistakes and errors in quantum programs.</span></span>
<span data-ttu-id="fa18c-105">Q # 标准库提供了各种不同的方法来确保量程程序的正确性，如 <xref:microsoft.quantum.techniques.testing-and-debugging>中所述。</span><span class="sxs-lookup"><span data-stu-id="fa18c-105">The Q# standard libraries provide a variety of different ways to ensure the correctness of quantum programs, as detailed in <xref:microsoft.quantum.techniques.testing-and-debugging>.</span></span>
<span data-ttu-id="fa18c-106">在很大程度上说，这种支持是函数和操作的形式，它们指示目标计算机向宿主程序或开发人员提供额外的诊断信息，或强制执行所表示的条件和固定条件的正确性通过函数或操作调用。</span><span class="sxs-lookup"><span data-stu-id="fa18c-106">Largely speaking, this support comes in the form of functions and operations that either instruct the target machine to provide additional diagnostic information to the host program or developer, or enforce the correctness of conditions and invariants expressed by the function or operation call.</span></span>

## <a name="machine-diagnostics"></a><span data-ttu-id="fa18c-107">计算机诊断</span><span class="sxs-lookup"><span data-stu-id="fa18c-107">Machine Diagnostics</span></span> ##

<span data-ttu-id="fa18c-108">可以通过使用 <xref:microsoft.quantum.intrinsic.message> 函数以计算机相关的方式记录消息，从而获取有关传统值的诊断。</span><span class="sxs-lookup"><span data-stu-id="fa18c-108">Diagnostics about classical values can be obtained by using the <xref:microsoft.quantum.intrinsic.message> function to log a message in a machine-dependent way.</span></span>
<span data-ttu-id="fa18c-109">默认情况下，这会将字符串写入控制台。</span><span class="sxs-lookup"><span data-stu-id="fa18c-109">By default, this writes the string to the console.</span></span>
<span data-ttu-id="fa18c-110">与内插字符串一起使用时，<xref:microsoft.quantum.intrinsic.message> 可以轻松地报告有关传统值的诊断信息：</span><span class="sxs-lookup"><span data-stu-id="fa18c-110">Used together with interpolated strings, <xref:microsoft.quantum.intrinsic.message> makes it easy to report diagnostic information about classical values:</span></span>

```Q#
let angle = Microsoft.Quantum.Math.PI() * 2.0 / 3.0;
Message($"About to rotate by an angle of {angle}...");
```

> [!NOTE]
> <span data-ttu-id="fa18c-111">`Message` 具有签名 `(String -> Unit)`，则无法从 Q # 内观察发出调试日志消息的。</span><span class="sxs-lookup"><span data-stu-id="fa18c-111">`Message` has signature `(String -> Unit)`, again representing that emitting a debug log message cannot be observed from within Q#.</span></span>

<span data-ttu-id="fa18c-112"><xref:microsoft.quantum.diagnostics.dumpmachine> 和 <xref:microsoft.quantum.diagnostics.dumpregister> callables 指示目标计算机提供有关当前已分配的所有 qubits 的诊断信息，或分别提供有关 qubits 的特定寄存器的诊断信息。</span><span class="sxs-lookup"><span data-stu-id="fa18c-112">The <xref:microsoft.quantum.diagnostics.dumpmachine> and <xref:microsoft.quantum.diagnostics.dumpregister> callables instruct target machines to provide diagnostic information about all currently allocated qubits or about a specific register of qubits, respectively.</span></span>
<span data-ttu-id="fa18c-113">每个目标计算机因提供的诊断信息而异，以响应转储指令。</span><span class="sxs-lookup"><span data-stu-id="fa18c-113">Each target machine varies in what diagnostic information is provided in response to a dump instruction.</span></span>
<span data-ttu-id="fa18c-114">例如，[完整状态模拟器](xref:microsoft.quantum.machines.full-state-simulator)目标虚拟机为主机程序提供了其内部使用的状态向量，以表示寄存器 qubits。</span><span class="sxs-lookup"><span data-stu-id="fa18c-114">The [full state simulator](xref:microsoft.quantum.machines.full-state-simulator) target machine, for instance, provides the host program with the state vector that it uses internally to represent a register of qubits.</span></span>
<span data-ttu-id="fa18c-115">相比之下， [Toffoli 模拟器](xref:microsoft.quantum.machines.toffoli-simulator)目标计算机为每个 qubit 提供一个传统位。</span><span class="sxs-lookup"><span data-stu-id="fa18c-115">By comparison, the [Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator) target machine provides a single classical bit for each qubit.</span></span>

 <span data-ttu-id="fa18c-116">若要详细了解[完整状态模拟器的](xref:microsoft.quantum.machines.full-state-simulator)`DumpMachine` 输出，请参阅我们的[测试和调试一文](xref:microsoft.quantum.techniques.testing-and-debugging#dump-functions)的 "转储函数" 一节。</span><span class="sxs-lookup"><span data-stu-id="fa18c-116">To learn more about the [full state simulator's](xref:microsoft.quantum.machines.full-state-simulator) `DumpMachine` output, take a look at the dump functions section of our [testing and debugging article](xref:microsoft.quantum.techniques.testing-and-debugging#dump-functions).</span></span>


## <a name="facts-and-assertions"></a><span data-ttu-id="fa18c-117">事实和断言</span><span class="sxs-lookup"><span data-stu-id="fa18c-117">Facts and Assertions</span></span> ##

<span data-ttu-id="fa18c-118">如[测试和调试](xref:microsoft.quantum.techniques.testing-and-debugging)中所述，可以将签名 `Unit -> Unit` 或 `Unit => Unit`的函数或操作分别标记为*单元测试*。</span><span class="sxs-lookup"><span data-stu-id="fa18c-118">As discussed in [Testing and Debugging](xref:microsoft.quantum.techniques.testing-and-debugging), a function or operation with signature `Unit -> Unit` or `Unit => Unit`, respectively, can be marked as a *unit test*.</span></span>
<span data-ttu-id="fa18c-119">每个单元测试通常包含一个小型量程计划，以及一个或多个检查该程序的正确性的条件。</span><span class="sxs-lookup"><span data-stu-id="fa18c-119">Each unit test generally consists of a small quantum program, along with one or more conditions that check the correctness of that program.</span></span>
<span data-ttu-id="fa18c-120">这些条件可采用以下两种形式之一：检查输入的值或_断言_，这些_事实_检查作为输入传递的一个或多个 qubits 的状态。</span><span class="sxs-lookup"><span data-stu-id="fa18c-120">These conditions can come in the form of either _facts_, which check the values of their inputs, or _assertions_, which check the states of one or more qubits passed as input.</span></span>

<span data-ttu-id="fa18c-121">例如，`EqualityFactI(1 + 1, 2, "1 + 1 != 2")` 表示 $1 + 1 = $2 的数学事实，而 `AssertQubit(One, qubit)` 表示衡量 `qubit` 将以确定性返回 `One` 的条件。</span><span class="sxs-lookup"><span data-stu-id="fa18c-121">For example, `EqualityFactI(1 + 1, 2, "1 + 1 != 2")` represents the mathematical fact that $1 + 1 = 2$, while `AssertQubit(One, qubit)` represents the condition that measuring `qubit` will return a `One` with certainty.</span></span>
<span data-ttu-id="fa18c-122">在前一种情况下，我们可以检查只给定其值的条件的正确性，而在后一种情况下，我们必须知道 qubit 的状态，以便评估断言。</span><span class="sxs-lookup"><span data-stu-id="fa18c-122">In the former case, we can check the correctness of the condition given only its values, while in the latter, we must know something about the state of the qubit in order to evaluate the assertion.</span></span>

<span data-ttu-id="fa18c-123">Q # 标准库提供了若干不同的函数来表示事实，其中包括：</span><span class="sxs-lookup"><span data-stu-id="fa18c-123">The Q# standard libraries provide several different functions for representing facts, including:</span></span>

- <xref:microsoft.quantum.diagnostics.fact>
- <xref:microsoft.quantum.diagnostics.equalitywithintolerancefact>
- <xref:microsoft.quantum.diagnostics.nearequalityfactc>
- <xref:microsoft.quantum.diagnostics.equalityfacti>


### <a name="testing-qubit-states"></a><span data-ttu-id="fa18c-124">测试 Qubit 状态</span><span class="sxs-lookup"><span data-stu-id="fa18c-124">Testing Qubit States</span></span> ###

<span data-ttu-id="fa18c-125">实际上，断言依赖于这一事实，即，对量子机制的传统模拟不需要遵循非[克隆定理](https://arxiv.org/abs/quant-ph/9607018)，因此，我们可以在为目标计算机使用模拟器时进行 unphysical 测量和断言。</span><span class="sxs-lookup"><span data-stu-id="fa18c-125">In practice, assertions rely on the fact that classical simulations of quantum mechanics need not obey the [no-cloning theorem](https://arxiv.org/abs/quant-ph/9607018), such that we can make unphysical measurements and assertions when using a simulator for our target machine.</span></span>
<span data-ttu-id="fa18c-126">因此，可以在部署硬件之前，在传统模拟器上测试各个操作。</span><span class="sxs-lookup"><span data-stu-id="fa18c-126">Thus, we can test individual operations on a classical simulator before deploying on hardware.</span></span>
<span data-ttu-id="fa18c-127">在不允许评估断言的目标计算机上，可以安全地忽略对 <xref:microsoft.quantum.intrinsic.assert> 的调用。</span><span class="sxs-lookup"><span data-stu-id="fa18c-127">On target machines which do not allow evaluation of assertions, calls to <xref:microsoft.quantum.intrinsic.assert> can be safely ignored.</span></span>

<span data-ttu-id="fa18c-128">更常见的情况是，<xref:microsoft.quantum.intrinsic.assert> 运算断言，测量给定 Pauli 基础中的给定 qubits 将始终具有给定的结果。</span><span class="sxs-lookup"><span data-stu-id="fa18c-128">More generally, the <xref:microsoft.quantum.intrinsic.assert> operation asserts that measuring the given qubits in the given Pauli basis will always have the given result.</span></span>
<span data-ttu-id="fa18c-129">如果断言失败，则将通过使用给定的消息调用 `fail` 结束执行。</span><span class="sxs-lookup"><span data-stu-id="fa18c-129">If the assertion fails, the execution ends by calling `fail` with the given message.</span></span>
<span data-ttu-id="fa18c-130">默认情况下，不实现此操作;可支持它的模拟器应该提供执行运行时检查的实现。</span><span class="sxs-lookup"><span data-stu-id="fa18c-130">By default, this operation is not implemented; simulators that can support it should provide an implementation that performs runtime checking.</span></span>
<span data-ttu-id="fa18c-131">`Assert` 具有 `((Pauli[], Qubit[], Result, String) -> ())`签名。</span><span class="sxs-lookup"><span data-stu-id="fa18c-131">`Assert` has signature `((Pauli[], Qubit[], Result, String) -> ())`.</span></span>
<span data-ttu-id="fa18c-132">由于 `Assert` 是一种将空元组作为其输出类型的函数，因此，不会有调用 `Assert` 的影响在 Q # 程序中是显而易见的。</span><span class="sxs-lookup"><span data-stu-id="fa18c-132">Since `Assert` is a function with an empty tuple as its output type, no effects from having called `Assert` are observable within a Q# program.</span></span>

<span data-ttu-id="fa18c-133">在某种程度上，<xref:microsoft.quantum.intrinsic.assertprob> 操作函数断言，该函数在给定的 Pauli 基础上测量给定的 qubits，以给定的概率表示给定的结果。</span><span class="sxs-lookup"><span data-stu-id="fa18c-133">The <xref:microsoft.quantum.intrinsic.assertprob> operation function asserts that measuring the given qubits in the given Pauli basis will have the given result with the given probability, within some tolerance.</span></span>
<span data-ttu-id="fa18c-134">容差为累加（例如 `abs(expected-actual) < tol`）。</span><span class="sxs-lookup"><span data-stu-id="fa18c-134">Tolerance is additive (e.g. `abs(expected-actual) < tol`).</span></span>
<span data-ttu-id="fa18c-135">如果断言失败，则将通过使用给定的消息调用 `fail` 结束执行。</span><span class="sxs-lookup"><span data-stu-id="fa18c-135">If the assertion fails, the execution ends by calling `fail` with the given message.</span></span>
<span data-ttu-id="fa18c-136">默认情况下，不实现此操作;可支持它的模拟器应该提供执行运行时检查的实现。</span><span class="sxs-lookup"><span data-stu-id="fa18c-136">By default, this operation is not implemented; simulators that can support it should provide an implementation that performs runtime checking.</span></span>
<span data-ttu-id="fa18c-137">`AssertProb` 具有 `((Pauli[], Qubit[], Result, Double, String, Double) -> Unit)`签名。</span><span class="sxs-lookup"><span data-stu-id="fa18c-137">`AssertProb` has signature `((Pauli[], Qubit[], Result, Double, String, Double) -> Unit)`.</span></span> <span data-ttu-id="fa18c-138">`Double` 的第一个参数提供所需的结果概率，第二个参数提供公差。</span><span class="sxs-lookup"><span data-stu-id="fa18c-138">The first of `Double` parameters gives the desired probability of the result, and the second one the tolerance.</span></span>

<span data-ttu-id="fa18c-139">我们不仅可以使用断言单个度量值，还可以使用模拟器用来表示 qubit 的内部状态的传统信息适合复制，这样我们就不需要实际执行度量来测试断言。</span><span class="sxs-lookup"><span data-stu-id="fa18c-139">We can do more than assert a single measurement, using that the classical information used by a simulator to represent the internal state of a qubit is amenable to copying, such that we do not need to actually perform a measurement to test our assertion.</span></span>
<span data-ttu-id="fa18c-140">具体而言，这使我们能够考虑到在实际硬件上无法进行的*不兼容*指标。</span><span class="sxs-lookup"><span data-stu-id="fa18c-140">In particular, this allows us to reason about *incompatible* measurements that would be impossible on actual hardware.</span></span>

<span data-ttu-id="fa18c-141">假定 `P : Qubit => Unit` 是一项操作，用于在其输入处于状态 $ \ket{0}$ 时准备状态 $ \ket{\psi} $。</span><span class="sxs-lookup"><span data-stu-id="fa18c-141">Suppose that `P : Qubit => Unit` is an operation intended to prepare the state $\ket{\psi}$ when its input is in the state $\ket{0}$.</span></span>
<span data-ttu-id="fa18c-142">让 $ \ket{\psi '} $ 是 `P`准备的实际状态。</span><span class="sxs-lookup"><span data-stu-id="fa18c-142">Let $\ket{\psi'}$ be the actual state prepared by `P`.</span></span>
<span data-ttu-id="fa18c-143">然后，当且仅当 $ \ket{\psi} $ 描述的轴中的 $ \ket{\psi '} $ 度量 $ '} $ 时，$ \ket{\psi} = \ket{\psi '} $ 总是返回 `Zero`。</span><span class="sxs-lookup"><span data-stu-id="fa18c-143">Then, $\ket{\psi} = \ket{\psi'}$ if and only if measuring $\ket{\psi'}$ in the axis described by $\ket{\psi}$ always returns `Zero`.</span></span>
<span data-ttu-id="fa18c-144">也就是说，如果且仅当} \braket{\psi | \psi '} = 1 时，\begin{align} \ket{\psi} = \ket{\psi '} \text{。</span><span class="sxs-lookup"><span data-stu-id="fa18c-144">That is, \begin{align} \ket{\psi} = \ket{\psi'} \text{ if and only if } \braket{\psi | \psi'} = 1.</span></span>
<span data-ttu-id="fa18c-145">\end{align} 使用在 prelude 中定义的基元运算，可以直接执行一个度量值，该度量值将在 $ \ket{\psi} $ eigenstate 为 Pauli 运算符之一时返回 `Zero`。</span><span class="sxs-lookup"><span data-stu-id="fa18c-145">\end{align} Using the primitive operations defined in the prelude, we can directly perform a measurement that returns `Zero` if $\ket{\psi}$ is an eigenstate of one of the Pauli operators.</span></span>


<span data-ttu-id="fa18c-146">如果要测试断言 $ \ket{\psi} = \ket{0}$，操作 <xref:microsoft.quantum.diagnostics.assertqubit> 提供了一个特别有用的速记。</span><span class="sxs-lookup"><span data-stu-id="fa18c-146">The operation <xref:microsoft.quantum.diagnostics.assertqubit> provides a particularly useful shorthand to do so in the case that we wish to test the assertion $\ket{\psi} = \ket{0}$.</span></span>
<span data-ttu-id="fa18c-147">这种情况很常见，例如，当我们 uncomputed 将 ancilla qubits 返回到 ${0}\ket 后，再将其释放。</span><span class="sxs-lookup"><span data-stu-id="fa18c-147">This is common, for instance, when we have uncomputed to return ancilla qubits to $\ket{0}$ before releasing them.</span></span>
<span data-ttu-id="fa18c-148">如果希望断言两种状态准备 `P` 和 `Q` 操作都准备相同的状态，并且 `Q` 支持 `Adjoint`，则对 $ \ket{0}$ 进行断言也很有用。</span><span class="sxs-lookup"><span data-stu-id="fa18c-148">Asserting against $\ket{0}$ is also useful when we wish to assert that two state preparation `P` and `Q` operations both prepare the same state, and when `Q` supports `Adjoint`.</span></span>
<span data-ttu-id="fa18c-149">特别是，</span><span class="sxs-lookup"><span data-stu-id="fa18c-149">In particular,</span></span>

```qsharp
using (register = Qubit()) {
    P(register);
    Adjoint Q(register);

    AssertQubit(Zero, register);
}
```

<span data-ttu-id="fa18c-150">但是，更常见的情况是，我们无法访问断言与 Pauli 运算符的 eigenstates 不一致的状态。</span><span class="sxs-lookup"><span data-stu-id="fa18c-150">More generally, however, we may not have access to assertions about states that do not coincide with eigenstates of Pauli operators.</span></span>
<span data-ttu-id="fa18c-151">例如，$ \ket{\psi} = （\ket{0} + e ^ {i \pi/8} \ket{1}）/\sqrt{2}$ 不是任何 Eigenstate 运算符的 Pauli，因此不能使用 <xref:microsoft.quantum.intrinsic.assertprob> 来唯一确定状态 $ \ket{\psi '} $ 等于 $ \ket{\psi} $。</span><span class="sxs-lookup"><span data-stu-id="fa18c-151">For example, $\ket{\psi} = (\ket{0} + e^{i \pi / 8} \ket{1}) / \sqrt{2}$ is not an eigenstate of any Pauli operator, such that we cannot use <xref:microsoft.quantum.intrinsic.assertprob> to uniquely determine that a state $\ket{\psi'}$ is equal to $\ket{\psi}$.</span></span>
<span data-ttu-id="fa18c-152">相反，我们必须将断言 $ \ket{\psi '} = \ket{\psi} $ 分解为可使用模拟器支持的基元直接测试的假设。</span><span class="sxs-lookup"><span data-stu-id="fa18c-152">Instead, we must decompose the assertion $\ket{\psi'} = \ket{\psi}$ into assumptions that can be directly tested using  the primitives supported by our simulator.</span></span>
<span data-ttu-id="fa18c-153">为此，请让 $ \ket{\psi} = \alpha \ket{0} + \beta \ket{1}$ 用于复数 $ \alpha = a\_r + a\_i $ 和 $ \beta $。</span><span class="sxs-lookup"><span data-stu-id="fa18c-153">To do so, let $\ket{\psi} = \alpha \ket{0} + \beta \ket{1}$ for complex numbers $\alpha = a\_r + a\_i i$ and $\beta$.</span></span>
<span data-ttu-id="fa18c-154">请注意，此表达式需要四个实数 $\{一个\_r、一个\_i、b\_r、b\_i\}$ 来指定，因为每个复数都可以表示为实部和虚部的总和。</span><span class="sxs-lookup"><span data-stu-id="fa18c-154">Note that this expression requires four real numbers $\{a\_r, a\_i, b\_r, b\_i\}$ to specify, as each complex number can be expressed as the sum of a real and imaginary part.</span></span>
<span data-ttu-id="fa18c-155">不过，由于全局阶段，我们可以选择 $a\_i = $0，因此，我们只需三个实数即可唯一指定 qubit 状态。</span><span class="sxs-lookup"><span data-stu-id="fa18c-155">Due to the global phase, however, we can choose $a\_i = 0$, such that we only need three real numbers to uniquely specify a single-qubit state.</span></span>

<span data-ttu-id="fa18c-156">因此，需要指定三个断言，它们彼此独立，以便断言所需的状态。</span><span class="sxs-lookup"><span data-stu-id="fa18c-156">Thus, we need to specify three assertions which are independent of each other in order to assert the state that we expect.</span></span>
<span data-ttu-id="fa18c-157">为此，我们需要查找每个 Pauli 度量值（给定 $ \alpha $ 和 $ \beta $）的观察 `Zero` 的概率，并分别对每个度量值进行断言。</span><span class="sxs-lookup"><span data-stu-id="fa18c-157">We do so by finding the probability of observing `Zero` for each Pauli measurement given $\alpha$ and $\beta$, and asserting each independently.</span></span>
<span data-ttu-id="fa18c-158">让 $x $、$y $ 和 $z $ 分别 `Result` 值 $X $、$Y $ 和 $Z $ 度量值。</span><span class="sxs-lookup"><span data-stu-id="fa18c-158">Let $x$, $y$, and $z$ be `Result` values for Pauli $X$, $Y$, and $Z$ measurements respectively.</span></span>
<span data-ttu-id="fa18c-159">然后，对量程度量值使用可能性函数 \begin{align} \Pr （x = \texttt{Zero} | \alpha，\beta） & = \frac12 + a\_r b\_r + a\_i b\_\\\\ \Pr （y = \texttt{Zero} | \alpha，\beta） & = \frac12 + a\_r b\_\Pr i b\_r \\\\ （z = \texttt{Zero} | \alpha，\beta） & = \frac12\left （1 + a\_r ^ 2 + a\_i ^ 2 + b\_r ^ 2 + b\_\_i ^ 2 \right）。</span><span class="sxs-lookup"><span data-stu-id="fa18c-159">Then, using the likelihood function for quantum measurements, \begin{align} \Pr(x = \texttt{Zero} | \alpha, \beta) & = \frac12 + a\_r b\_r + a\_i b\_i \\\\ \Pr(y = \texttt{Zero} | \alpha, \beta) & = \frac12 + a\_r b\_i - a\_i b\_r \\\\ \Pr(z = \texttt{Zero} | \alpha, \beta) & = \frac12\left( 1 + a\_r^2 + a\_i^2 + b\_r^2 + b\_i^2 \right).</span></span>
<span data-ttu-id="fa18c-160">\end{align}</span><span class="sxs-lookup"><span data-stu-id="fa18c-160">\end{align}</span></span>

<span data-ttu-id="fa18c-161"><xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> 操作以 <xref:microsoft.quantum.math.complex>类型的值的形式实现了 $ \alpha $ 和 $ \beta $ 表示形式的这些断言。</span><span class="sxs-lookup"><span data-stu-id="fa18c-161">The <xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> operation implements these assertions given representations of $\alpha$ and $\beta$ as values of type <xref:microsoft.quantum.math.complex>.</span></span>
<span data-ttu-id="fa18c-162">当预期状态可数学计算时，这非常有用。</span><span class="sxs-lookup"><span data-stu-id="fa18c-162">This is helpful when the expected state can be computed mathematically.</span></span>

### <a name="asserting-equality-of-quantum-operations"></a><span data-ttu-id="fa18c-163">断言量程运算的相等性</span><span class="sxs-lookup"><span data-stu-id="fa18c-163">Asserting Equality of Quantum Operations</span></span> ###

<span data-ttu-id="fa18c-164">到目前为止，我们关注的是用于准备特定状态的测试操作。</span><span class="sxs-lookup"><span data-stu-id="fa18c-164">Thus far, we have been concerned with testing operations which are intended to prepare particular states.</span></span>
<span data-ttu-id="fa18c-165">不过，通常情况下，我们对操作如何处理任意输入（而不是单个固定的输入）感兴趣。</span><span class="sxs-lookup"><span data-stu-id="fa18c-165">Often, however, we are interested in how an operation acts for arbitrary inputs rather than for a single fixed input.</span></span>
<span data-ttu-id="fa18c-166">例如，假设我们已实现了一个操作 `U : ((Double, Qubit[]) => () : Adjoint)` 对应于一系列 $U （t） $ 的单一运算符，并且提供了显式 `adjoint` 块，而不是使用 `adjoint auto`。</span><span class="sxs-lookup"><span data-stu-id="fa18c-166">For example, suppose we have implemented an operation `U : ((Double, Qubit[]) => () : Adjoint)` corresponding to a family of unitary operators $U(t)$, and have provided an explicit `adjoint` block instead of using `adjoint auto`.</span></span>
<span data-ttu-id="fa18c-167">如果 $t $ 表示演化时间，我们可能会有兴趣断言 $U ^ \dagger （t） = U （-t） $。</span><span class="sxs-lookup"><span data-stu-id="fa18c-167">We may be interested in asserting that $U^\dagger(t) = U(-t)$, as expected if $t$ represents an evolution time.</span></span>

<span data-ttu-id="fa18c-168">广泛地说，我们可以遵循两种不同的策略，使断言指出两个操作 `U`，`V` 的行为相同。</span><span class="sxs-lookup"><span data-stu-id="fa18c-168">Broadly speaking, there are two different strategies that we can follow in making the assertion that two operations `U` and `V` act identically.</span></span>
<span data-ttu-id="fa18c-169">首先，我们可以检查 `U(target); (Adjoint V)(target);` 在给定的基础上保留每种状态。</span><span class="sxs-lookup"><span data-stu-id="fa18c-169">First, we can check that `U(target); (Adjoint V)(target);` preserves each state in a given basis.</span></span>
<span data-ttu-id="fa18c-170">其次，我们可以检查 `U(target); (Adjoint V)(target);` 在放大状态的一半上是否保留了牵连。</span><span class="sxs-lookup"><span data-stu-id="fa18c-170">Second, we can check that `U(target); (Adjoint V)(target);` acting on half of an entangled state preserves that entanglement.</span></span>
<span data-ttu-id="fa18c-171">这些策略由 canon 操作分别实现 <xref:microsoft.quantum.diagnostics.assertoperationsequalinplace> 和 <xref:microsoft.quantum.diagnostics.assertoperationsequalreferenced>。</span><span class="sxs-lookup"><span data-stu-id="fa18c-171">These strategies are implemented by the canon operations <xref:microsoft.quantum.diagnostics.assertoperationsequalinplace> and <xref:microsoft.quantum.diagnostics.assertoperationsequalreferenced>, respectively.</span></span>

> [!NOTE]
> <span data-ttu-id="fa18c-172">上面所述的引用断言基于[Choi – Jamiłkowski isomorphism](https://en.wikipedia.org/wiki/Channel-state_duality)，这是一个数学框架，该框架将 $n $ qubits 上的操作与 $ 2n $ 放大上的 qubits 状态关联起来。</span><span class="sxs-lookup"><span data-stu-id="fa18c-172">The referenced assertion discussed above works based on the [Choi–Jamiłkowski isomorphism](https://en.wikipedia.org/wiki/Channel-state_duality), a mathematical framework which relates operations on $n$ qubits to entangled states on $2n$ qubits.</span></span>
> <span data-ttu-id="fa18c-173">具体而言，$n $ qubits 上的标识操作由放大状态 $ \ket{\ beta_{00}} \mathrel{： =} （\ket{00} + \ket{11}）/\sqrt{2}$ $n $ 个副本表示。</span><span class="sxs-lookup"><span data-stu-id="fa18c-173">In particular, the identity operation on $n$ qubits is represented by $n$ copies of the entangled state $\ket{\beta_{00}} \mathrel{:=} (\ket{00} + \ket{11}) / \sqrt{2}$.</span></span>
> <span data-ttu-id="fa18c-174">操作 <xref:microsoft.quantum.preparation.preparechoistate> 实现此 isomorphism，准备表示给定操作的状态。</span><span class="sxs-lookup"><span data-stu-id="fa18c-174">The operation <xref:microsoft.quantum.preparation.preparechoistate> implements this isomorphism, preparing a state that represents a given operation.</span></span>

<span data-ttu-id="fa18c-175">大致而言，这些策略可通过时间空间平衡来区分。</span><span class="sxs-lookup"><span data-stu-id="fa18c-175">Roughly, these strategies are distinguished by a time–space tradeoff.</span></span>
<span data-ttu-id="fa18c-176">循环访问每个输入状态需要额外的时间，而使用牵连作为引用需要存储其他 qubits。</span><span class="sxs-lookup"><span data-stu-id="fa18c-176">Iterating through each input state takes additional time, while using entanglement as a reference requires storing additional qubits.</span></span>
<span data-ttu-id="fa18c-177">如果某个操作实现可逆的传统操作，使其只对计算基础状态的行为感兴趣，则 <xref:microsoft.quantum.diagnostics.assertoperationsequalinplacecompbasis> 测试此限制的输入集的相等性。</span><span class="sxs-lookup"><span data-stu-id="fa18c-177">In cases where an operation implements a reversible classical operation, such that we are only interested in its behavior on computational basis states, <xref:microsoft.quantum.diagnostics.assertoperationsequalinplacecompbasis> tests equality on this restricted set of inputs.</span></span>

> [!TIP]
> <span data-ttu-id="fa18c-178">针对输入状态的迭代由 <xref:microsoft.quantum.canon.iteratethroughcartesianproduct> 和 <xref:microsoft.quantum.canon.iteratethroughcartesianpower>的枚举操作处理。</span><span class="sxs-lookup"><span data-stu-id="fa18c-178">The iteration over input states is handled by the enumeration operations <xref:microsoft.quantum.canon.iteratethroughcartesianproduct> and <xref:microsoft.quantum.canon.iteratethroughcartesianpower>.</span></span>
> <span data-ttu-id="fa18c-179">这些操作更适用于将操作应用于两个或多个集之间笛卡尔积的每个元素。</span><span class="sxs-lookup"><span data-stu-id="fa18c-179">These operations are useful more generally for applying an operation to each element of the Cartesian product between two or more sets.</span></span>

<span data-ttu-id="fa18c-180">但更严重的是，这两种方法测试正在检查的操作的不同属性。</span><span class="sxs-lookup"><span data-stu-id="fa18c-180">More critically, however, the two approaches test different properties of the operations under examination.</span></span>
<span data-ttu-id="fa18c-181">由于就地断言多次调用每个操作，因此对每个输入状态一次，任何随机选项和测量结果可能在调用之间发生变化。</span><span class="sxs-lookup"><span data-stu-id="fa18c-181">Since the in-place assertion calls each operation multiple times, once for each input state, any random choices and measurement results might change between calls.</span></span>
<span data-ttu-id="fa18c-182">与此相反，引用的断言只调用一次每个操作一次，以便*在一个拍摄中*检查操作是否相等。</span><span class="sxs-lookup"><span data-stu-id="fa18c-182">By contrast, the referenced assertion calls each operation exactly once, such that it checks that the operations are equal *in a single shot*.</span></span>
<span data-ttu-id="fa18c-183">这两个测试可用于确保量程程序的正确性。</span><span class="sxs-lookup"><span data-stu-id="fa18c-183">Both of these tests are useful in ensuring the correctness of quantum programs.</span></span>


## <a name="further-reading"></a><span data-ttu-id="fa18c-184">延伸阅读</span><span class="sxs-lookup"><span data-stu-id="fa18c-184">Further Reading</span></span> ##

- <xref:microsoft.quantum.techniques.testing-and-debugging>
- <xref:microsoft.quantum.diagnostics>
