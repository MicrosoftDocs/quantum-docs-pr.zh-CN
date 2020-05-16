---
title: 使用量子位
description: 填充说明
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.qubits
ms.openlocfilehash: e89b9ccfe2a0796e01eedfc99f7ce71038d85f38
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430928"
---
# <a name="working-with-qubits"></a>使用量子位

现在，您已经看到了几个不同的 Q # 语言部分，接下来让我们来看看它的多样性，并了解如何使用 qubits 本身。

请注意，函数的主体内不允许使用这些语句。
它们仅在操作内有效。

## <a name="allocating-qubits"></a>分配 Qubits

### <a name="clean-qubits"></a>清理 qubits

`using`语句用于*分配*新的 qubits，以便在语句块中使用。

语句包含关键字 `using` ，后跟左括号 `(` 、绑定、右括号 `)` 和 qubits 将在其中可用的语句块。
绑定遵循与语句相同的模式 `let` ：单个符号或符号元组，后跟一个等号 `=` ，一个值或匹配*项*的匹配元组。

初始值设定项可用于单个 qubit （表示为 `Qubit()` ）或 qubits 的数组， `Qubit[n]` 其中 `n` 是一个 `Int` 表达式。
例如，应用于对象的

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```

以这种方式分配的任何 qubits 在 $ \ket {0} $ 状态中开始，在上面的示例中， `register` 将处于状态 $ \ket {00000} = \ket {0} \otimes \ket \otimes \cdots \otimes {0} \ket {0} $。
在块的末尾 `using` ，该块分配的任何 qubits 将立即解除分配，并且无法进一步使用。

> [!WARNING]
> 目标计算机预期 qubits 在解除分配之前立即处于 $ \ket {0} $ 状态，以便可以重用它们并将其提供给其他 `using` 块进行分配。
> 请尽可能使用单一操作将分配的任何 qubits 返回到 $ \ket {0} $。
> 如果需要， @"microsoft.quantum.intrinsic.reset" 可以使用操作来度量 qubit，并使用该度量值来确保将测量的 qubit 返回到 $ \ket {0} $。 此类度量会销毁所有牵连和剩余 qubits，因而会影响计算。


### <a name="borrowed-qubits"></a>借用 Qubits

`borrowing`语句用于使 qubits 可供暂时使用，无需处于特定状态。

使用借款机制，可以在计算过程中将 qubits 分配为暂存空间。
这些 qubits 通常不处于干净状态，也就是说，它们不一定在已知状态（如 $ \ket $）中进行初始化 {0} 。
这通常称为 "脏" qubits，因为它们的状态未知，甚至可以与量程计算机内存的其他部分放大。

绑定与语句中的绑定遵循相同的模式和规则 `using` 。
例如，应用于对象的
```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, register) = (Qubit(), Qubit[5])) {
    // ...
}
```
借 qubits 处于未知状态，在语句块结束时超出范围。
借款人提交 qubits，使其在其被借用时处于相同状态，即，它们在语句块开始和结束时的状态应相同。
此状态特别不一定是经典状态，因此在大多数情况下，借款范围不应包含度量值。 

在借用 qubits 时，系统将首先尝试填写正在使用的 qubits 中的请求，但不会在语句体中进行访问 `borrowing` 。
如果没有足够的 qubits，则它将分配新的 qubits 来完成请求。


在脏 qubits 的已知用例中，是多控制 CNOT-CONTAINS 入口的实现，只需很少的 qubits 和实现 incrementers。
请参阅下面的[借款 Qubits 示例](#borrowing-qubits-example)，以查看在 Q # 中使用的示例，或者[*使用 2n + 2 Qubits 和使用具有 Toffoli 的模块乘法*](https://arxiv.org/abs/1611.07995)（Haner、Roetteler 和 Svore 2017）作为使用借用 Qubits 的算法的纸张。


## <a name="intrinsic-operations"></a>内部操作

分配后，可以将 qubit 传递到函数和操作。
在某种意义上，Q # 程序可以使用 qubit 执行的操作，因为可执行的操作全部定义为操作。
在[内部操作和函数](xref:microsoft.quantum.libraries.standard.prelude)中，我们将更详细地了解这些操作，但现在我们提到了几种可用于与 qubits 交互的有用操作。

首先，qubit Pauli 运算符 $X $、$Y $ 和 $Z $ 通过内部操作 `X` 、 `Y` 和（ `Z` 其中每个都具有类型）表示 `(Qubit => Unit is Adj + Ctl)` 。
如[内部操作和函数](xref:microsoft.quantum.libraries.standard.prelude)中所述，我们可以将 $X $， `X` 以作为位翻转操作，也可以不使用门。
`X`操作允许我们为某些传统位字符串 $s $ s_0 s_1 \dots .. s_n} $ 形式准备状态：

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

我们还可以 {0} {1} {2} {-} {0} {1} {2} 使用 \right 转换 $H $ （在 Q # 中通过内部操作表示）来准备状态，例如 $ \ket{+} = \left （\ket + \ket \sqrt）/\ket $ 和 $ \left = \ket （\ket-\right \sqrt）/Hadamard $ `H : (Qubit => Unit is Adj + Ctl)` 。

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

使用 `Measure` 操作（这是内置的非单一的非单一操作），我们可以从类型的对象中提取传统信息， `Qubit` 并分配一个传统值作为结果，该类型具有保留类型 `Result` ，这表示结果不再是量程状态。
的输入 `Measure` 是 Bloch 球体上的 Pauli 轴，由类型 `Pauli` （例如）的值 `PauliX` 和类型的值表示 `Qubit` 。

一个简单的示例是以下操作，它在 $ \ket $ 状态下分配一个 qubit {0} ，然后对其应用一个 Hadamard 操作， `H` 并根据结果测量结果 `PauliZ` 。

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

## <a name="borrowing-qubits-example"></a>借款 Qubits 示例

在 canon 中，有使用关键字的示例 `borrowing` ，例如定义的函数 `MultiControlledXBorrow` 。
如果 `controls` 表示应添加到操作的控件 qubits `X` ，则 `Length(controls)-2` 此实现将添加多个脏 ancillas 的总体。

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

请注意，广泛使用了 `With` 连结符---其形式适用于支持 adjoint 的操作，即 `WithA` 在此示例中进行了---。
这是一种很好的编程风格，因为将控件添加到结构涉及 `With` 仅将控制传播到内部操作。
此外，请注意，除操作的外 `body` ，还 `controlled` 显式提供操作的主体的实现，而不是使用 `controlled auto` 语句。
这样做的原因是，我们从线路的结构了解到如何轻松添加更多的控件，与向中的每个门和每个单独的门添加控件相比，这一点更有利 `body` 。 

此代码可用于将此代码与另一个 canon 函数进行比较，该函数可实现 `MultiControlledXClean` 按操作控制的操作的相同目标 `X` ，不过，这种方法使用了多个 clean qubits `using` 机制。 

## <a name="whats-next"></a>下一步是什么？
了解 Q # 中的[控制流](xref:microsoft.quantum.guide.controlflow)。