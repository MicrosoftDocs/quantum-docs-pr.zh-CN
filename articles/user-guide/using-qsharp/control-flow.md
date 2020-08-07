---
title: 控制流Q#
description: 循环、条件等。
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.controlflow
no-loc:
- Q#
- $$v
ms.openlocfilehash: fc619d64bfebfc27d7feac6dafb2dd4cf22825d6
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "87867941"
---
# <a name="control-flow-in-no-locq"></a>控制流Q#

在操作或函数中，每个语句都按顺序运行，类似于其他常见的命令性传统语言。
但是，可以通过三种不同的方式修改控制流：

* `if`前瞻性
* `for`循环
* `repeat-until-success`循环

`if`和 `for` 控制流构造在熟悉大多数传统编程语言的情况下继续进行。 [`Repeat-until-success`](#repeat-until-success-loop)循环将在本文的后面部分进行讨论。

重要的 `for` 是，循环和 `if` 语句可用于自动生成[专用](xref:microsoft.quantum.guide.operationsfunctions)化的操作。 在这种情况下，循环的 adjoint `for` 会反转方向，并 adjoint 每次迭代。
此操作遵循 "鞋和 socks" 原则：如果想要撤消在 socks 和鞋上进行操作，必须先撤消鞋，然后撤消放置 socks。 

## <a name="if-else-if-else"></a>如果为，则为; 否则为

`if`语句支持条件执行。
它包含关键字 `if` 、括号中的布尔表达式和语句块 (_then_块) 。
根据需要，可以遵循任意数量的 else if 子句，其中每个子句都包含关键字 `elif` 、括号中的布尔表达式和语句块 (_else （if）_ 块) 。
最后，语句可以选择使用 else 子句完成，后者由关键字 `else` 后跟另一个语句块 (_else_块) 。

`if`计算条件，如果该条件为*true*，则运行*then*块。
如果条件为*false*，则计算第一个 else if 条件;如果为 true，则运行*其他-if*块。
否则，第二个 else-if block 计算，然后是第三个，依此类推，直到遇到具有 true 条件的子句，或者没有其他的 else 子句。
如果原始*if*条件和所有 else if 子句的计算结果为*false*，则将运行*else*块（如果已提供）。

请注意，不管哪个块运行，它都在它自己的作用域内运行。
`if`块结束后，在、或块内部所做的绑定 `elif` `else` 将不可见。

例如，应用于对象的

```qsharp
if (result == One) {
    X(target);
    let n = 1;
    // n is bound
} 
// n is not bound
```
or
```qsharp
if (i == 1) {
    X(target);
    let n = 1;
} elif (i == 2) {
    Y(target);
    let m = n + 1; // would cause an error, because n is no longer bound
} else {
    Z(target);
}
```

## <a name="for-loop"></a>For 循环

`for`语句支持对整数范围或数组进行迭代。
语句包含关键字 `for` ，后跟符号或符号元组、关键字 `in` 、类型 `Range` 或数组的表达式、所有 in 括号和语句块。

语句块 (循环的主体) 重复运行，定义的符号 (循环变量) 绑定到该范围或数组中的每个值。
请注意，如果范围表达式的计算结果为空范围或数组，则正文根本不会运行。
在进入循环之前，将完全计算该表达式，并且在执行循环时不会更改。

循环变量绑定到循环体的每个入口，在主体末尾解除绑定。
For 循环完成后，循环变量未绑定。
循环变量的绑定是不可变的，并且与其他变量绑定遵循相同的规则。 

在这些示例中， `qubits` 是 qubits 的寄存器 (即) 类型的 `Qubit[]` ， 

```qsharp
// ...
for (qubit in qubits) {  // iterate over each qubit value in the array qubits
    H(qubit);
}
// 'qubit' is no longer bound

mutable results = new (Int, Results)[Length(qubits)];
for (index in 0 .. Length(qubits) - 1) {  // iterates over the integers in the Range 0 .. (Length(qubits) - 1)
    set results w/= index <- (index, M(qubits[index])); // measure each qubit, updates the tuple value in the results array that at index 
}

mutable accumulated = 0;
for ((index, measured) in results) { // iterates over the tuple values in results
    if (measured == One) {
        set accumulated += 1 <<< index;
    }
}
```

请注意，在结束时，我们使用了算术左移的二进制运算符 `<<<` 。 有关详细信息，请参阅[数值表达式](xref:microsoft.quantum.guide.expressions#numeric-expressions)。

## <a name="repeat-until-success-loop"></a>重复执行-成功循环

此 Q# 语言允许经典控制流依赖于测量 qubits 的结果。
此功能进而实现了实现功能强大的概率小工具，从而降低了实现 unitaries 的计算成本。
这种情况的示例如下所示 *-成功* (ru) 模式 Q# 。
这些 RUS 模式是概率的程序，这些程序在基本入口方面具有*预期*的低成本;产生的费用取决于多个可能 branchings 的实际运行和交叉交叉。

为了便于重复-成功 (ru) 模式， Q# 支持构造

```qsharp
repeat {
    // do stuff
}
until (expression)
fixup {
    // do other stuff
}
```

其中 `expression` ，是任何计算结果为类型的值的有效表达式 `Bool` 。
循环体运行，然后计算条件。
如果条件为 true，则语句已完成;否则，修正将运行，并且语句将再次运行（从循环体开始）。

 (正文、测试和修正) 的所有三个部分都被视为*每个重复*的单个作用域，因此，在正文中绑定的符号可用于测试和修复。
但是，完成修正的执行将结束语句的范围，以便在正文或修正期间所进行的符号绑定在后续的重复中不可用。

而且， `fixup` 语句通常非常有用，但并非总是必需的。
如果不需要，构造

```qsharp
repeat {
    // do stuff
}
until (expression);
```

也是有效的 RUS 模式。

有关更多示例和详细信息，请参阅本文中的[重复-截止到成功示例](#repeat-until-success-examples)。

> [!TIP]   
> 避免在函数内使用重复-until 循环。 使用*while*循环来提供函数内的相应功能。 

## <a name="while-loop"></a>While 循环

重复-直到成功模式有一个非常特定于量程的内涵。 它们广泛用于特定的量程算法类，因此是中的专用语言构造 Q# 。 但是，在编译时，中断的循环会在量程运行时中按特定的小心处理，这种情况下，会在编译时进行中断。 但是，它们在函数中的使用是 unproblematic 的，因为这些循环只包含在常规 (非量程) 硬件上运行的代码。 

Q#因此，仅支持在函数内使用 while 循环。 `while`语句由关键字 `while` 、括号中的布尔表达式和语句块组成。
只要条件的计算结果为，语句块 (循环的主体) 运行 `true` 。

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```

## <a name="return-statement"></a>Return 语句

Return 语句结束操作或函数的运行，并将值返回给调用方。
它包含关键字 `return` ，后跟适当类型的表达式和终止分号。

例如，应用于对象的
```qsharp
return 1;
```
or
```qsharp
return (results, qubits);
```

* 返回空元组的可调用 `()` 不需要 return 语句。
* 若要指定操作或函数的早期退出，请使用 `return ();` 。
返回任何其他类型的 Callables 需要最终的 return 语句。
* 操作中不存在最大返回语句数。
如果语句在块内跟随 return 语句，则编译器可能会发出警告。

   
## <a name="fail-statement"></a>Fail 语句

Fail 语句结束操作的运行，并将错误值返回给调用方。
它包含关键字 `fail` ，后跟一个字符串和一个终止分号。
语句将字符串返回到传统驱动程序作为错误消息。

操作中的 fail 语句数量没有限制。
如果语句在块中跟随 fail 语句，则编译器可能会发出警告。

例如，应用于对象的

```qsharp
fail $"Impossible state reached";
```
或者，使用内[插字符串](xref:microsoft.quantum.guide.expressions#interpolated-strings)
```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="repeat-until-success-examples"></a>重复执行-直到成功示例

### <a name="rus-pattern-for-single-qubit-rotation-about-an-irrational-axis"></a>针对无理数轴的单 qubit 旋转的 RUS 模式 

在典型用例中，以下 Q# 操作实现绕 {5} Bloch 球上的无理数轴（$ (I + 2i Z) /\sqrt $）的旋转。 实现使用已知的 RUS 模式：

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

### <a name="rus-loop-with-a-mutable-variable-in-scope"></a>作用域中具有可变变量的 ru 循环

此示例演示如何使用可变变量，该变量在 `finished` 整个重复截止到延迟的循环范围内，并在循环之前进行初始化并在修正步骤中更新。

```qsharp
mutable iter = 1;
repeat {
    ProbabilisticCircuit(qubits);
    let success = ComputeSuccessIndicator(qubits);
}
until (success || iter > maxIter)
fixup {
    iter += 1;
    ComputeCorrection(qubits);
}
```

### <a name="rus-without-fixup"></a>不带`fixup`

此示例显示了不带修正步骤的 ru 循环。 此代码是一种概率线路，它使用和入口实现重要的旋转门 $V _3 = ( \boldone + 2 i Z) /\sqrt {5} $ `H` `T` 。
该循环平均终止 $ \frac {8} {5} $ 重复。
有关更多详细信息，请参阅 qubit unitaries (Paetznick 和 Svore，2014) 的[*非确定性分解*](https://arxiv.org/abs/1311.1074)。

```qsharp
using (qubit = Qubit()) {
    repeat {
        H(qubit);
        T(qubit);
        CNOT(target, qubit);
        H(qubit);
        Adjoint T(qubit);
        H(qubit);
        T(qubit);
        H(qubit);
        CNOT(target, qubit);
        T(qubit);
        Z(target);
        H(qubit);
        let result = M(qubit);
    } until (result == Zero);
}
```

### <a name="rus-to-prepare-a-quantum-state"></a>用于准备量子状态的 ru

最后，下面是一个用于准备量子状态 $ \frac {1} {\sqrt {3} } \left ( \sqrt {2} \ket {0} + \ket {1} \right) $，从 $ \ket{+} $ 状态开始的 ru 模式的示例。

此操作中所示的明显编程功能包括：

* `fixup`循环中涉及量程操作的更为复杂的部分。 
* 使用 `AssertMeasurementProbability` 语句来确定在程序中的某些指定点测量量程状态的概率。

有关和操作的详细 [`AssertMeasurement`](xref:microsoft.quantum.diagnostics.assertmeasurement) 信息 [`AssertMeasurementProbability`](xref:microsoft.quantum.diagnostics.assertmeasurementprobability) ，请参阅[测试和调试](xref:microsoft.quantum.guide.testingdebugging)。

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+> state.
            AssertMeasurementProbability(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+> state", 1e-10 );
            AssertMeasurementProbability(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+> state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+> state on the auxiliary qubit
            // is 3/4.
            AssertMeasurementProbability(
                [PauliX], [auxiliary], Zero, 3. / 4.,
                "Error: the probability to measure |+> in the first
                auxiliary must be 3/4",
                1e-10);

            // If we get the measurement outcome Zero, we prepare the
            // required state.
            let outcome = Measure([PauliX], [auxiliary]);
        }
        until (outcome == Zero)
        fixup {
            // Bring the auxiliary and target qubits back to |+> state.
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

有关详细信息，请参阅[随标准库提供的单元测试示例](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs)：

## <a name="next-steps"></a>后续步骤

了解中的[测试和调试](xref:microsoft.quantum.guide.testingdebugging) Q# 。
