---
title: 使用 Qubits
description: 了解如何分配 qubits，如何在操作和函数中使用它们并测量结果。
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.qubits
ms.openlocfilehash: 1aa2432996dda61d099e3b5bb4db78379ce43d97
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907641"
---
# <a name="working-with-qubits"></a>使用 Qubits

现在，您已经看到了几个不同的 Q # 语言部分，接下来让我们来看看它的多样性，并了解如何使用 qubits 本身。

## <a name="allocating-qubits"></a>分配 Qubits

首先，若要获取可在 Q # 中使用的 qubit，我们将在 `using` 块中*分配*qubits：

```qsharp
using (register = Qubit[5]) {
    // Do stuff...
}
```

以这种方式分配的任何 qubits 在 $ \ket{0}$ 状态下开始：在上面的示例中，`register` 在状态 $ \ket{00000} = \ket{0} \otimes \ket{0} \otimes \cdots \otimes \ket{0}$。
在 `using` 块结束时，将立即释放该块分配的所有 qubits，并且无法进一步使用。

> [!WARNING]
> 目标计算机预期 qubits 在释放前立即处于 $ \ket{0}$ 状态，以便可以重用它们并将其提供给其他 `using` 块进行分配。
> 请尽可能使用单一操作将分配的任何 qubits 返回到 $ \ket{0}$。
> 如果需要，可以使用 @"microsoft.quantum.intrinsic.reset" 操作来度量 qubit，并使用该度量值来确保度量的 qubit 返回到 $ \ket{0}$。 此类度量会销毁所有牵连和剩余 qubits，因而会影响计算。

## <a name="intrinsic-operations"></a>内部操作

分配后，可以将 qubit 传递到函数和操作。
在某种意义上，Q # 程序可以使用 qubit 执行的操作，因为可执行的操作全部定义为操作。
在[内部操作和函数](xref:microsoft.quantum.libraries.standard.prelude)中，我们将更详细地了解这些操作，但现在我们提到了几种可用于与 qubits 交互的有用操作。

首先，qubit Pauli 运算符 $X $、$Y $ 和 $Z $ 通过内部运算 `X`、`Y`和 `Z`表示，其中每个操作都具有类型 `(Qubit => Unit is Adj + Ctl)`。
如[内部操作和函数](xref:microsoft.quantum.libraries.standard.prelude)中所述，我们可以将 $X $ 并因此 `X` 为位翻转操作或不进行操作。
`X` 操作允许我们为某些传统位字符串 $s $ \ket{s_0 s_1 \dots . s_n} $ 准备状态：

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
        // Resetting the qubits will allow us to deallocate them properly.
        ResetAll(register);
    }
}
```

> [!TIP]
> 稍后，我们将看到更简洁的方式来编写不需要手动流控制的此操作。

我们还可以使用 \Right 转换{0} $ 来准备状态，例如 $ \ket{+} = \left （\ket{0} + \ket{1}\sqrt）/\ket{2}$ 和 $ \left{-} = \ket （\ket{1}-\right{2}\sqrt）/Hadamard $H $，该转换在 Q # 中由内部操作 `H : (Qubit => Unit is Adj + Ctl)`：

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

## <a name="measurements"></a>度量

使用 `Measure` 操作（这是一种内置的固有非单一操作），我们可以从类型为 `Qubit` 的对象中提取传统信息，并分配一个传统值作为结果，该类型具有保留类型 `Result`，这表示结果不再是量程状态。
`Measure` 的输入是 Bloch 球体上的一个 Pauli 轴，由类型 `Pauli` （例如 `PauliX`）的值和 `Qubit`类型的值表示。

一个简单的示例是以下操作，它在 $ \ket{0}$ 状态下分配一个 qubit，然后将 Hadamard 操作 `H` 应用到该操作并按 `PauliZ` 度量结果。

```qsharp
operation MeasureOneQubit() : Result {
    // The following using block creates a fresh qubit and initializes it
    // in the |0〉 state.
    using (qubit = Qubit()) {
        // We apply a Hadamard operation H to the state, thereby preparing the
        // state 1 / sqrt(2) (|0〉 + |1〉).
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

以下操作指定了一个稍微复杂的示例，如果 `Qubit[]` 类型的寄存器中的所有 qubits 的值在指定的 Pauli 时为零，则返回布尔值 `true`; 否则返回 `false`。

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

Q # 语言允许经典控制流依赖于测量 qubits 的结果。
此功能反过来允许实现功能强大的概率小工具，从而降低实现 unitaries 的计算成本。
例如，可以轻松地在 Q # 中实现所谓的 "*重复到-成功*" （ru）模式。
这些 ru 模式是概率的程序，这些程序在基本入口方面具有*预期*的低成本，但真正的成本取决于实际运行以及各种可能的 branchings 的实际交错。

为了便于重复到成功（ru）模式，Q # 支持构造

```qsharp
repeat {
    statementBlock1
}
until (expression)
fixup {
    statementBlock2
}
```

其中 `statementBlock1` 和 `statementBlock2` 是零个或多个 Q # 语句，`expression` 任何计算结果为类型 `Bool`值的有效表达式。
在典型用例中，以下 Q # 操作实现绕 Bloch 球上的无理数轴（I + 2i Z）/\sqrt{5}$ 的旋转。 这是通过使用已知的 RUS 模式来实现的：

```qsharp
operation ApplyVRotationUsingRUS(qubit : Qubit) : Unit {
    using (controls = Qubit[2]) {
        ApplyToEachA(H, controls);
        mutable finished = false;
        repeat {
            Controlled X(controls, qubit);
            S(qubit);
            Controlled X(controls, qubit);
            Z(qubit);
        }
        until (finished)
        fixup {
            if (MeasureIfAllQubitsAreZero(controls, PauliX)) {
                set finished = true;
            }
        }
    }
}
```

此示例演示如何使用可变变量 `finished` 它在整个重复截止时间延迟循环范围内，并在循环之前进行了初始化并在修正步骤中更新。

最后，我们将演示一个用于准备量子状态 $ \frac{1}{\sqrt{3}} \left （\sqrt{2}\ket{0}+ \ket{1}\right） $ （从 $ \ket{+} $ 状态开始）的 ru 模式的示例。
另请参阅[标准库提供的单元测试示例](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs)：

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+⟩ state.
            AssertProb(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+⟩ state", 1e-10 );
            AssertProb(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+⟩ state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+⟩ state on the auxiliary qubit
            // is 3/4.
            AssertProb(
                [PauliX], [auxiliary], Zero, 3. / 4.,
                "Error: the probability to measure |+⟩ in the first
                auxiliary must be 3/4",
                1e-10);

            // If we get the measurement outcome Zero, we prepare the
            // required state.
            let outcome = Measure([PauliX], [auxiliary]);
        }
        until (outcome == Zero)
        fixup {
            // Bring the auxiliary and target qubits back to |+⟩ state.
            if (outcome == One) {
                Z(auxiliary);
                X(target);
                H(target);
            }
        }
        // Return the auxiliary qubit back to the Zero state.
        H(auxiliary);
    }
}
```

此操作中所示的明显编程功能是更复杂 `fixup` 的循环部分，它涉及量程操作，并且使用 `AssertProb` 语句来确定在程序中的特定点测量量程状态的概率。
有关[`Assert`](xref:microsoft.quantum.intrinsic.assert)和[`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob)操作的详细信息，另请参阅[测试和调试](xref:microsoft.quantum.techniques.testing-and-debugging)。
