---
title: 使用量子位
description: 填充说明
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.qubits
ms.openlocfilehash: 1655d18ab9d8638ad356e6fb90994b5c1fd76a25
ms.sourcegitcommit: a3775921db1dc5c653c97b8fa8fe2c0ddd5261ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2020
ms.locfileid: "85885298"
---
# <a name="working-with-qubits"></a>使用量子位

Qubits 是量程计算中信息的基础对象。 有关 qubits 的常规介绍，请参阅[了解量程计算](xref:microsoft.quantum.overview.understanding)，若要深入了解其数学表示形式，请参阅[Qubit](xref:microsoft.quantum.concepts.qubit)。 

本文探讨了如何在 Q # 程序中使用和处理 qubits。 

> [!IMPORTANT]
>本文中所述的所有语句在函数体中均无效。 它们仅在操作内有效。

## <a name="allocating-qubits"></a>分配 Qubits

由于物理 qubits 是量程计算机中宝贵的资源，因此，编译器的一项工作是确保它们尽可能有效地使用。
因此，您需要告诉 Q # 为在特定语句块内使用而*分配*qubits。
可以将 qubits 分配为单一 qubit，也可以将其分配为 qubits 数组（称为*寄存器*）。 

### <a name="clean-qubits"></a>清理 qubits

使用 `using` 语句可分配新的 qubits，以便在语句块期间使用。

语句包含关键字 `using` ，后跟括在括号中的绑定 `( )` 和 qubits 可用的语句块。
绑定遵循与语句相同的模式 `let` ：单个符号或符号元组，后跟一个等号 `=` ，一个值或匹配*项*的匹配元组。

初始值设定项可用于单个 qubit （表示为 `Qubit()` ）或 qubits 的数组， `Qubit[n]` 其中 `n` 是一个 `Int` 表达式。
例如，

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```

以这种方式分配的任何 qubits 在 $ \ket {0} $ 状态下开始。 因此，在前面的示例中， `auxiliary` 是处于状态 $ \ket $ 的单个 qubit {0} ，位于 `register` qubit 状态 $ \ket {00000} = \ket \otimes {0} {0} {0} \ket \otimes \cdots \otimes $ 中。
在块的末尾 `using` ，该块分配的任何 qubits 将立即解除分配，并且无法进一步使用。

> [!WARNING]
> 目标计算机可以重复使用已释放的 qubits，并将其提供给其他 `using` 块进行分配。 因此，在释放之前，目标计算机期望 qubits 处于 $ \ket {0} $ 状态。
> 请尽可能使用单一操作将分配的任何 qubits 返回到 $ \ket {0} $。
> 如果需要，可以使用 @"microsoft.quantum.intrinsic.reset" 操作，该操作通过测量将 qubit 返回 $ \ket {0} $，并根据结果有条件地执行操作。 此类度量会销毁剩余 qubits 的所有牵连，从而影响计算。


### <a name="borrowed-qubits"></a>借用 Qubits

使用 `borrowing` 语句可将 qubits 分配为临时使用，无需处于特定状态。

在计算过程中，可以使用借用 qubits 作为暂存空间。
这些 qubits 通常不处于干净状态，也就是说，它们不一定在已知状态（如 $ \ket $）中进行初始化 {0} 。
这通常称为 "脏" qubits，因为它们的状态未知，甚至可以与量程计算机内存的其他部分放大。

绑定遵循与语句相同的模式和规则 `using` 。
例如，
```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```
借 qubits 处于未知状态，在语句块结束时超出范围。
借款人提交 qubits，使其在其借出时处于相同状态;也就是说，它们在语句块的开头和结尾处的状态应相同。
由于此状态不一定是经典状态，因此在大多数情况下，借款范围不应包含度量值。 

在借用 qubits 时，系统首先会尝试从正在使用的 qubits 中填充请求，但在语句体中不会访问该请求 `borrowing` 。
如果没有足够的 qubits，则会分配新的 qubits 来完成请求。

在脏 qubits 的已知用例中，是多控制 CNOT-CONTAINS 入口的实现，只需很少的 qubits 和实现 incrementers。
有关在 Q # 中使用的示例，请参阅本文中的[借款 Qubits 示例](#borrowing-qubits-example)，或使用 2n + 2 Qubits （对于利用借用 Roetteler 的算法，[*使用 2n + 2*](https://arxiv.org/abs/1611.07995) 2017 和 Toffoli）进行的纸张分解。

## <a name="intrinsic-operations"></a>内部操作

分配后，可以将 qubit 传递到函数和操作。
在某种意义上，Q # 程序可以使用 qubit 执行的操作，因为可执行的操作全部定义为操作。

本文讨论了几个有用的 Q # 操作，可用于与 qubits 交互。
有关这些和其他的详细信息，请参阅[内部操作和函数](xref:microsoft.quantum.libraries.standard.prelude)。 

首先，qubit Pauli 运算符 $X $、$Y $ 和 $Z $ 通过内部操作 [`X`](xref:microsoft.quantum.intrinsic.x) 、 [`Y`](xref:microsoft.quantum.intrinsic.y) 和（ [`Z`](xref:microsoft.quantum.intrinsic.z) 其中每个都具有类型）表示 `(Qubit => Unit is Adj + Ctl)` 。

如[内部操作和函数](xref:microsoft.quantum.libraries.standard.prelude)中所述，请将 $X $， `X` 以作为位翻转操作，而不是入口。
您可以使用该 `X` 操作来为某些传统位字符串 $s $ s_0 \ket{s_1 \dots .. s_n} $ 的形式准备状态：

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
> 稍后，您将看到更简洁的方式来编写不需要手动控制流的操作。

你还可以使用 \Right 转换 $H $ 来准备状态，例如 $ \ket{+} = \left （\ket {0} + \ket {1} \sqrt）/\ket {2} $ 和 $ \left {-} = \ket （\ket {0} -\right {1} \sqrt）/Hadamard {2} $，该转换在 Q # 中通过内部运算 [`H`](xref:microsoft.quantum.intrinsic.h) （类型为（Qubit => Unit is 调整 + Ctl））来表示：

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

## <a name="measurements"></a>度量

可以在不同的基础上执行单个 qubits 的度量值，每个度量值由[Bloch 球体](xref:microsoft.quantum.glossary#bloch-sphere)上的 Pauli 轴表示。
*计算基础*是指 `PauliZ` 基础，是用于度量的最常见的基础。

### <a name="measure-a-single-qubit-in-the-pauliz-basis"></a>基于单个 qubit 度量 `PauliZ`

使用 " [`M`](xref:microsoft.quantum.intrinsic.m) 操作"，它是一个内置的非单一的非单一操作，用于度量单个 qubit 并为 `PauliZ` 结果分配一个传统值。
`M`具有保留的返回类型， `Result` 它只能接受值 `Zero` 或 `One` 对应于已测量状态 $ \ket {0} $ 或 $ \ket {1} $-指示结果不再是量程状态。

一个简单的示例是以下操作，它在 $ \ket $ 状态下分配一个 qubit {0} ，然后对其应用一个 Hadamard 操作， `H` 并根据结果测量结果 `PauliZ` 。

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

### <a name="measure-one-or-more-qubits-in-specific-bases"></a>度量特定基准中的一个或多个 qubits

若要测量特定基数的一个或多个 qubits 数组，可以使用 [`Measure`](xref:microsoft.quantum.intrinsic.measure) 操作。

的输入 `Measure` 是一组 `Pauli` 类型（例如， `[PauliX, PauliZ, PauliZ]` ）和 qubits 的数组。

下面的操作将提供一个稍微复杂的示例， `true` 如果 `Qubit[]` 在指定的 Pauli 基础上测量时，类型寄存器中的所有 qubits 都处于状态零，则返回布尔值; `false` 否则返回。

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

请注意，此示例 `Measure` 每次仅在单个 qubits 上执行一次，但可以将该操作扩展到多个 qubits 上的联合度量。

## <a name="borrowing-qubits-example"></a>借款 Qubits 示例

使用关键字的 canon 中有一些示例 `borrowing` ，如以下函数 `MultiControlledXBorrow` 。 如果 `controls` 表示要添加到操作的控件 qubits `X` ，则该实现添加的脏[ancillas](xref:microsoft.quantum.glossary#ancilla)的数量为 `Length(controls)-2` 。

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

请注意，此示例使用了连结符的广泛使用 `With` 方式，其形式适用于支持 adjoint 的操作，例如 `WithA` 。
这是一种很好的编程风格，因为将控件添加到结构涉及 `With` 仅将控制传播到内部操作。
另请注意，除 `body` 操作的外， `controlled` 显式提供操作的主体的实现，而不是使用 `controlled auto` 语句。
出现这种情况的原因是，由于线路的结构，可以很容易地添加进一步的控件，这与向中的每个入口添加控件相比，这一点更有利 `body` 。 

此代码可用于将此代码与另一个 canon 函数进行比较，该函数可实现 `MultiControlledXClean` 按操作控制的操作的相同目标 `X` ，不过，这种方法使用了多个 clean qubits `using` 机制。 

## <a name="next-steps"></a>后续步骤

了解 Q # 中的[控制流](xref:microsoft.quantum.guide.controlflow)。