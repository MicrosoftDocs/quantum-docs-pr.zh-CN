---
title: 使用 Qubits |Microsoft Docs
description: 使用 Qubits
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.qubits
ms.openlocfilehash: 477b358c3eba58b62926b4e9094770c9741cac92
ms.sourcegitcommit: 27c9bf1aae923527aa5adeaee073cb27d35c0ca1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/05/2019
ms.locfileid: "74864247"
---
# <a name="working-with-qubits"></a><span data-ttu-id="1b711-103">使用 Qubits</span><span class="sxs-lookup"><span data-stu-id="1b711-103">Working with Qubits</span></span> #

<span data-ttu-id="1b711-104">现在，您已经看到了几个不同的 Q # 语言部分，接下来让我们来看看它的多样性，并了解如何使用 qubits 本身。</span><span class="sxs-lookup"><span data-stu-id="1b711-104">Having now seen a variety of different parts of the Q# language, let us get into the thick of it and see how to use qubits themselves.</span></span>

## <a name="allocating-qubits"></a><span data-ttu-id="1b711-105">分配量子位</span><span class="sxs-lookup"><span data-stu-id="1b711-105">Allocating Qubits</span></span> ##

<span data-ttu-id="1b711-106">首先，若要获取可在 Q # 中使用的 qubit，我们将在 `using` 块中*分配*qubits：</span><span class="sxs-lookup"><span data-stu-id="1b711-106">First, to obtain a qubit that we can use in Q#, we *allocate* qubits within a `using` block:</span></span>

```qsharp
using (register = Qubit[5]) {
    // Do stuff...
}
```

<span data-ttu-id="1b711-107">以这种方式分配的任何 qubits 在 $ \ket{0}$ 状态下开始：在上面的示例中，`register` 在状态 $ \ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$。</span><span class="sxs-lookup"><span data-stu-id="1b711-107">Any qubits allocated in this way start off in the $\ket{0}$ state; in the example above, `register` is thus in the state $\ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$.</span></span>
<span data-ttu-id="1b711-108">在 `using` 块结束时，将立即释放该块分配的所有 qubits，并且无法进一步使用。</span><span class="sxs-lookup"><span data-stu-id="1b711-108">At the end of the `using` block, any qubits allocated by that block are immediately deallocated and cannot be used further.</span></span>

> [!WARNING]
> <span data-ttu-id="1b711-109">目标计算机预期 qubits 在释放前立即处于 $ \ket{0}$ 状态，以便可以重用它们并将其提供给其他 `using` 块进行分配。</span><span class="sxs-lookup"><span data-stu-id="1b711-109">Target machines expect that qubits are in the $\ket{0}$ state immediately before deallocation, so that they can be reused and offered to other `using` blocks for allocation.</span></span>
> <span data-ttu-id="1b711-110">请尽可能使用单一操作将分配的任何 qubits 返回到 $ \ket{0}$。</span><span class="sxs-lookup"><span data-stu-id="1b711-110">Whenever possible, use unitary operations to return any allocated qubits to $\ket{0}$.</span></span>
> <span data-ttu-id="1b711-111">如果需要，可以使用 @"microsoft.quantum.intrinsic.reset" 操作来度量 qubit，并使用该度量值来确保度量的 qubit 返回到 $ \ket{0}$。</span><span class="sxs-lookup"><span data-stu-id="1b711-111">If need be, the @"microsoft.quantum.intrinsic.reset" operation can be used to measure a qubit instead, and to use that measurement result to ensure that the measured qubit is returned to $\ket{0}$.</span></span> <span data-ttu-id="1b711-112">此类度量会销毁所有牵连和剩余 qubits，因而会影响计算。</span><span class="sxs-lookup"><span data-stu-id="1b711-112">Such a measurement will destroy any entanglement with the remaining qubits and can thus impact the computation.</span></span> 

## <a name="intrinsic-operations"></a><span data-ttu-id="1b711-113">内部操作</span><span class="sxs-lookup"><span data-stu-id="1b711-113">Intrinsic Operations</span></span> ##

<span data-ttu-id="1b711-114">分配后，可以将 qubit 传递到函数和操作。</span><span class="sxs-lookup"><span data-stu-id="1b711-114">Once allocated, a qubit can then be passed to functions and operations.</span></span>
<span data-ttu-id="1b711-115">在某种意义上，Q # 程序可以使用 qubit 执行的操作，因为可执行的操作全部定义为操作。</span><span class="sxs-lookup"><span data-stu-id="1b711-115">In some sense, this is all that a Q# program can do with a qubit, as the actions that can be taken are all defined as operations.</span></span>
<span data-ttu-id="1b711-116">在[内部操作和函数](xref:microsoft.quantum.libraries.standard.prelude)中，我们将更详细地了解这些操作，但现在我们提到了几种可用于与 qubits 交互的有用操作。</span><span class="sxs-lookup"><span data-stu-id="1b711-116">We will see these operations in more detail in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), but for now, we mention a few useful operations that can be used to interact with qubits.</span></span>

<span data-ttu-id="1b711-117">首先，qubit Pauli 运算符 $X $、$Y $ 和 $Z $ 通过内部运算 `X`、`Y`和 `Z`表示，其中每个操作都具有类型 `(Qubit => Unit is Adj + Ctl)`。</span><span class="sxs-lookup"><span data-stu-id="1b711-117">First, the single-qubit Pauli operators $X$, $Y$, and $Z$ are represented in Q# by the intrinsic operations `X`, `Y`, and `Z`, each of which has type `(Qubit => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="1b711-118">如[内部操作和函数](xref:microsoft.quantum.libraries.standard.prelude)中所述，我们可以将 $X $ 并因此 `X` 为位翻转操作或不进行操作。</span><span class="sxs-lookup"><span data-stu-id="1b711-118">As described in [Intrinsic Operations and Functions](xref:microsoft.quantum.libraries.standard.prelude), we can think of $X$ and hence of `X` as a bit-flip operation or NOT gate.</span></span>
<span data-ttu-id="1b711-119">这样 $s，我们就可以将 "$ \ket{s_0 s_1 \dots . s_n} $"</span><span class="sxs-lookup"><span data-stu-id="1b711-119">This lets us prepare states of the form $\ket{s_0 s_1 \dots s_n}$ for some classical bit string $s$:</span></span>

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

operation Example() : Unit {

    using (register = Qubit[8]) {
        PrepareBitString(
            [true, true, false, false, true, false, false, true],
            register
        );
        // At this point, register now has the state |11001001〉.
    }
}
```

> [!TIP]
> <span data-ttu-id="1b711-120">稍后，我们将看到更简洁的方式来编写不需要手动流控制的此操作。</span><span class="sxs-lookup"><span data-stu-id="1b711-120">Later, we will see more compact ways of writing this operation that do not require manual flow control.</span></span>

<span data-ttu-id="1b711-121">我们还可以使用 \Right 转换{0} $ 来准备状态，例如 $ \ket{+} = \left （\ket{0} + \ket{1}\sqrt）/\ket{2}$ 和 $ \left{-} = \ket （\ket{1}-\right{2}\sqrt）/Hadamard $H $，该转换在 Q # 中由内部操作 `H : (Qubit => Unit is Adj + Ctl)`：</span><span class="sxs-lookup"><span data-stu-id="1b711-121">We can also prepare states such as $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ and $\ket{-} = \left(\ket{0} - \ket{1}\right) / \sqrt{2}$ by using the Hadamard transform $H$, which is represented in Q# by the intrinsic operation `H : (Qubit => Unit is Adj + Ctl)`:</span></span>

```qsharp
operation PreparePlusMinusState(bitstring : Bool[], register : Qubit[]) : Unit {

    // First, get a computational basis state of the form
    // |s_0 s_1 ... s_n〉 by using PrepareBitString, above.
    PrepareBitString(bitstring, register);
    // Next, we use that |+〉 = H|0〉 and |-〉 = H|1〉 to
    // prepare the state we want.
    for (idxQubit in IndexRange(register)) {
        H(register[idxQubit]);
    }
}
```

## <a name="measurements"></a><span data-ttu-id="1b711-122">度量</span><span class="sxs-lookup"><span data-stu-id="1b711-122">Measurements</span></span> ##

<span data-ttu-id="1b711-123">使用 `Measure` 操作（这是一种内置的内部非单一操作），我们可以从类型为 `Qubit` 的对象中提取传统信息，并分配一个传统值作为结果，该类型具有一个保留类型 `Result`，这表示结果不再是量程状态。</span><span class="sxs-lookup"><span data-stu-id="1b711-123">Using the `Measure` operation, which is a built in intrinsic non-unitary operation, we can extract classical information from an object of type `Qubit` and assign a classical value as a result, which has a reserved type `Result`, indicating that the result is no longer a quantum state.</span></span> <span data-ttu-id="1b711-124">`Measure` 的输入是 Bloch 球体上的一个 Pauli 轴，由 `Pauli` 类型的对象（例如 `PauliX`）和类型 `Qubit`的对象表示。</span><span class="sxs-lookup"><span data-stu-id="1b711-124">The input to `Measure` is a Pauli axis on the Bloch sphere, represented by an object of type `Pauli` (i.e., for instance `PauliX`) and an object of type `Qubit`.</span></span> 

<span data-ttu-id="1b711-125">一个简单的示例是以下操作，它在 $ \ket{0}$ 状态下创建一个 qubit，然后向其应用 Hadamard 入口 ``H``，然后在 `PauliZ` 基础测量结果。</span><span class="sxs-lookup"><span data-stu-id="1b711-125">A simple example is the following operation which creates one qubit in the $\ket{0}$ state, then applies a Hadamard gate ``H`` to it and then measures the result in the `PauliZ` basis.</span></span> 

```qsharp
operation MeasurementOneQubit () : Result {

    // The following using block creates a fresh qubit and initializes it 
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // We apply a Hadamard operation H to the state, thereby creating the 
        // state 1/sqrt(2)(|0〉+|1〉). 
        H(qubit); 
        // Now we measure the qubit in Z-basis.
        let result = M(qubit);
        // As the qubit is now in an eigenstate of the measurement operator, 
        // we reset the qubit before releasing it. 
        if (result == One) { X(qubit); }   
        // Finally, we return the result of the measurement. 
        return result;
    }
}
```

<span data-ttu-id="1b711-126">如果 `Qubit[]` 类型的寄存器中的所有 qubits 的状态均为零，则在按指定的 `false` Pauli 进行度量时，将返回布尔值，这会稍微复杂一些的示例，否则，将返回布尔值 `true`。</span><span class="sxs-lookup"><span data-stu-id="1b711-126">A slightly more complicated example is given by the following operation which returns the Boolean value `true` if all qubits in a register of type `Qubit[]` are in the state zero, when measured in a specified Pauli basis and `false` otherwise.</span></span> 

```qsharp
operation AllMeasurementsZero (qs : Qubit[], pauli : Pauli) : Bool {

    mutable value = true;
    for (q in qs) {
        if ( Measure([pauli], [q]) == One ) {
            set value = false;
        }
    }
    return value;
}
```

<span data-ttu-id="1b711-127">Q # 语言允许 qubits 的测量结果的传统控制流的依赖关系。</span><span class="sxs-lookup"><span data-stu-id="1b711-127">The Q# language allows dependencies of classical control flow on measurement results of qubits.</span></span> <span data-ttu-id="1b711-128">这进而使实现功能强大的概率小工具，从而降低了实现 unitaries 的计算成本。</span><span class="sxs-lookup"><span data-stu-id="1b711-128">This in turn enables to implement powerful probabilistic gadgets that can reduce the computational cost for implementing unitaries.</span></span> <span data-ttu-id="1b711-129">例如，可以很容易地在 Q # 中实现所谓的 "*重复-成功*"，这是概率的线路，这些电路在基本入口方面具有*预期*的低成本，但真正的成本取决于实际运行情况以及各种可能 branchings 的实际交错。</span><span class="sxs-lookup"><span data-stu-id="1b711-129">As an example, it is easy to implement so-called *Repeat-Until-Success* in Q# which are probabilistic circuits that have an *expected* low cost in terms of elementary gates, but for which the true cost depends on an actual run and an actual interleaving of various possible branchings.</span></span> 

<span data-ttu-id="1b711-130">为了便于重复到成功（ru）模式，Q # 支持构造</span><span class="sxs-lookup"><span data-stu-id="1b711-130">To facilitate Repeat-Until-Success (RUS) patterns, Q# supports the construct</span></span>
```qsharp
repeat {
    statementBlock1 
}
until (expression)
fixup {
    statementBlock2
}
```
<span data-ttu-id="1b711-131">其中 `statementBlock1` 和 `statementBlock2` 是零个或多个 Q # 语句，`expression` 任何计算结果为类型 `Bool`值的有效表达式。</span><span class="sxs-lookup"><span data-stu-id="1b711-131">where `statementBlock1` and `statementBlock2` are zero or more Q# statements, and `expression` any valid expression that evaluates to a value of type `Bool`.</span></span> <span data-ttu-id="1b711-132">在典型用例中，以下线路实现绕 Bloch 球上的无理数轴（I + 2i Z）/\sqrt{5}$ 的旋转。</span><span class="sxs-lookup"><span data-stu-id="1b711-132">In a typical use case, the following circuit implements a rotation around an irrational axis of $(I + 2i Z)/\sqrt{5}$ on the Bloch sphere.</span></span> <span data-ttu-id="1b711-133">这是通过使用已知的 RUS 模式来实现的：</span><span class="sxs-lookup"><span data-stu-id="1b711-133">This is accomplished by using a known RUS pattern:</span></span> 

```qsharp
operation RUScircuit (qubit : Qubit) : Unit {

    using(ancillas = Qubit[2]) {
        ApplyToEachA(H, ancillas);
        mutable finished = false;
        repeat {
            Controlled X(ancillas, qubit);
            S(qubit);
            Controlled X(ancillas, qubit);
            Z(qubit);
        }
        until(finished)
        fixup {
            if AllMeasurementsZero(ancillas, Xpauli) {
                set finished = true;
            }
        }
    }
}
```

<span data-ttu-id="1b711-134">此示例演示如何使用可变变量 `finished` 它在整个重复截止时间延迟循环范围内，并在循环之前进行了初始化并在修正步骤中更新。</span><span class="sxs-lookup"><span data-stu-id="1b711-134">This example shows the use of a mutable variable `finished` which is in scope of the entire repeat-until-fixup loop and which gets initialized before the loop and updated in the fixup step.</span></span>

<span data-ttu-id="1b711-135">最后，我们将演示一个用于准备量子状态 $ \frac{1}{\sqrt{3}} \left （\sqrt{2}\ket{0}+ \ket{1}\right） $ （从 $ \ket{+} $ 状态开始）的 ru 模式的示例。</span><span class="sxs-lookup"><span data-stu-id="1b711-135">Finally, we show an example of a RUS pattern to prepare a quantum state $\frac{1}{\sqrt{3}}\left(\sqrt{2}\ket{0}+\ket{1}\right)$, starting from the $\ket{+}$ state.</span></span> <span data-ttu-id="1b711-136">另请参阅[标准库提供的单元测试示例](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs)：</span><span class="sxs-lookup"><span data-stu-id="1b711-136">See also the [unit testing sample provided with the standard library](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs):</span></span> 

```qsharp
operation RepeatUntilSuccessStatePreparation( target : Qubit ) : Unit {

    using( ancilla = Qubit() ) {
        H(ancilla);
        repeat {
            // We expect target and ancilla qubit to be in |+⟩ state.
            AssertProb( 
                [PauliX], [target], Zero, 1.0, 
                "target qubit should be in the |+⟩ state", 1e-10 );
            AssertProb( 
                [PauliX], [ancilla], Zero, 1.0,
                "ancilla qubit should be in the |+⟩ state", 1e-10 );
                
            Adjoint T(ancilla);
            CNOT(target, ancilla);
            T(ancilla);

            // The probability of measuring |+⟩ state on ancilla is 3/4.
            AssertProb( 
                [PauliX], [ancilla], Zero, 3. / 4., 
                "Error: the probability to measure |+⟩ in the first 
                ancilla must be 3/4",
                1e-10);

            // If we get measurement outcome Zero, we prepare the required state 
            let outcome = Measure([PauliX], [ancilla]);
        }
        until( outcome == Zero )
        fixup {
            // Bring ancilla and target back to |+⟩ state
            if( outcome == One ) {
                Z(ancilla);
                X(target);
                H(target);
            }
        }
        // Return ancilla back to Zero state
        H(ancilla);
    }
}
```
 
<span data-ttu-id="1b711-137">此操作中所示的明显编程功能是更复杂 `fixup` 的循环部分，它涉及量程操作，并且使用 `AssertProb` 语句来确定在程序中的某些指定点测量量程状态的概率。</span><span class="sxs-lookup"><span data-stu-id="1b711-137">Notable programmatic features shown in this operation are a more complex `fixup` part of the loop which involves quantum operations, and the use of `AssertProb` statements to ascertain the probability of measuring the quantum state at certain specified points in the program.</span></span> <span data-ttu-id="1b711-138">有关 `Assert` 和 `AssertProb` 语句的详细信息，另请参阅[测试和调试](xref:microsoft.quantum.techniques.testing-and-debugging)。</span><span class="sxs-lookup"><span data-stu-id="1b711-138">See also [Testing and debugging](xref:microsoft.quantum.techniques.testing-and-debugging) for more information about `Assert` and `AssertProb` statements.</span></span> 
