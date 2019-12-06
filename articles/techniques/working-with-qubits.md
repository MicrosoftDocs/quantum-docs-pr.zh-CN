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
# <a name="working-with-qubits"></a>使用 Qubits #

现在，您已经看到了几个不同的 Q # 语言部分，接下来让我们来看看它的多样性，并了解如何使用 qubits 本身。

## <a name="allocating-qubits"></a>分配量子位 ##

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

## <a name="intrinsic-operations"></a>内部操作 ##

分配后，可以将 qubit 传递到函数和操作。
在某种意义上，Q # 程序可以使用 qubit 执行的操作，因为可执行的操作全部定义为操作。
在[内部操作和函数](xref:microsoft.quantum.libraries.standard.prelude)中，我们将更详细地了解这些操作，但现在我们提到了几种可用于与 qubits 交互的有用操作。

首先，qubit Pauli 运算符 $X $、$Y $ 和 $Z $ 通过内部运算 `X`、`Y`和 `Z`表示，其中每个操作都具有类型 `(Qubit => Unit is Adj + Ctl)`。
如[内部操作和函数](xref:microsoft.quantum.libraries.standard.prelude)中所述，我们可以将 $X $ 并因此 `X` 为位翻转操作或不进行操作。
这样 $s，我们就可以将 "$ \ket{s_0 s_1 \dots . s_n} $"

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

## <a name="measurements"></a>度量 ##

使用 `Measure` 操作（这是一种内置的内部非单一操作），我们可以从类型为 `Qubit` 的对象中提取传统信息，并分配一个传统值作为结果，该类型具有一个保留类型 `Result`，这表示结果不再是量程状态。 `Measure` 的输入是 Bloch 球体上的一个 Pauli 轴，由 `Pauli` 类型的对象（例如 `PauliX`）和类型 `Qubit`的对象表示。 

一个简单的示例是以下操作，它在 $ \ket{0}$ 状态下创建一个 qubit，然后向其应用 Hadamard 入口 ``H``，然后在 `PauliZ` 基础测量结果。 

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

如果 `Qubit[]` 类型的寄存器中的所有 qubits 的状态均为零，则在按指定的 `false` Pauli 进行度量时，将返回布尔值，这会稍微复杂一些的示例，否则，将返回布尔值 `true`。 

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

Q # 语言允许 qubits 的测量结果的传统控制流的依赖关系。 这进而使实现功能强大的概率小工具，从而降低了实现 unitaries 的计算成本。 例如，可以很容易地在 Q # 中实现所谓的 "*重复-成功*"，这是概率的线路，这些电路在基本入口方面具有*预期*的低成本，但真正的成本取决于实际运行情况以及各种可能 branchings 的实际交错。 

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
其中 `statementBlock1` 和 `statementBlock2` 是零个或多个 Q # 语句，`expression` 任何计算结果为类型 `Bool`值的有效表达式。 在典型用例中，以下线路实现绕 Bloch 球上的无理数轴（I + 2i Z）/\sqrt{5}$ 的旋转。 这是通过使用已知的 RUS 模式来实现的： 

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

此示例演示如何使用可变变量 `finished` 它在整个重复截止时间延迟循环范围内，并在循环之前进行了初始化并在修正步骤中更新。

最后，我们将演示一个用于准备量子状态 $ \frac{1}{\sqrt{3}} \left （\sqrt{2}\ket{0}+ \ket{1}\right） $ （从 $ \ket{+} $ 状态开始）的 ru 模式的示例。 另请参阅[标准库提供的单元测试示例](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs)： 

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
 
此操作中所示的明显编程功能是更复杂 `fixup` 的循环部分，它涉及量程操作，并且使用 `AssertProb` 语句来确定在程序中的某些指定点测量量程状态的概率。 有关 `Assert` 和 `AssertProb` 语句的详细信息，另请参阅[测试和调试](xref:microsoft.quantum.techniques.testing-and-debugging)。 
