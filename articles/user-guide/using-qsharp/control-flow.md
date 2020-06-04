---
title: Q 中的控制流#
description: 循环、条件等。
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.controlflow
ms.openlocfilehash: 1f1b641563fe35879abeee32b4f0aeeb7001b1a0
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/03/2020
ms.locfileid: "84326534"
---
# <a name="control-flow-in-q"></a>Q 中的控制流#

在操作或函数中，每个语句都按顺序执行，类似于最常见的命令性传统语言。
不过，可以通过三种不同的方式来修改这种控制流：

- `if`前瞻性
- `for`循环
- `repeat`-`until`循环

接[下来，我们](#repeat-until-success-loop)将讨论后者。
`if` `for` 不过，和控制流构造在熟悉大多数传统编程语言的情况下继续进行。

重要的 `for` 是，循环和 `if` 语句甚至可用于自动生成专用化的操作。 在这种情况下，循环的 adjoint `for` 会反转方向，并 adjoint 每次迭代。
这遵循了 "鞋和 socks" 原则：如果你想要撤消对 socks 和鞋的投入，则必须撤消鞋，然后撤消放置在 socks 上。
在您仍戴鞋的同时，小猫的工作效率更小，并使您的 socks 保持不变！

## <a name="if-else-if-else"></a>如果为，则为; 否则为

`if`语句支持条件执行。
它包含关键字 `if` 、左括号 `(` 、布尔表达式、右括号 `)` 和语句块（ _then_块）。
这可能后跟任意数量的 else if 子句，每个子句包含关键字 `elif` 、左括号 `(` 、布尔表达式、右括号 `)` 和语句块（ _else-if_块）。
最后，语句可以选择使用 else 子句完成，后者由关键字 `else` 后跟另一个语句块（ _else_块）组成。

`if`计算条件，如果该条件为 true，则执行 then 块。
如果条件为 false，则计算第一个 else if 条件;如果为 true，则执行此 else-if block。
否则，将测试第二个 else-if 块，然后是第三个块，依此类推，直到遇到具有 true 条件的子句或没有其他的 else 子句。
如果原始 if 条件和所有 else-if 子句的计算结果为 false，则在提供时将执行 else 块。

请注意，执行的任何块在其自己的作用域中执行。
在、或块内部所做的绑定在 `if` `elif` `else` 其结束后将不可见。

例如，

```qsharp
if (result == One) {
    X(target);
    let n = 1;
    // n is bound
} 
// n is not bound
```
或
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
语句包含关键字 `for` 、左括号 `(` 、符号或符号元组、关键字 `in` 、类型 `Range` 或数组的表达式、右括号 `)` 和语句块。

语句块（循环的主体）将重复执行，其中定义的符号（即循环变量）绑定到范围或数组中的每个值。
请注意，如果范围表达式的计算结果为空范围或数组，则不会执行主体。
在进入循环之前，将完全计算该表达式，并且在执行循环时不会更改。

循环变量绑定到循环体的每个入口，并在主体末尾解除绑定。
具体而言，for 循环完成后不会绑定循环变量。
声明的符号的绑定是不可变的，并且与其他变量绑定遵循相同的规则。 

对于某些示例，supposing `qubits` 是 qubits （即类型）的寄存器 `Qubit[]` ， 

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
请注意，在结束时，我们使用了算术左移的二进制运算符， `<<<` 详细信息可在[数值表达式](xref:microsoft.quantum.guide.expressions#numeric-expressions)中找到


## <a name="repeat-until-success-loop"></a>重复执行-成功循环

Q # 语言允许经典控制流依赖于测量 qubits 的结果。
此功能反过来允许实现功能强大的概率小工具，从而降低实现 unitaries 的计算成本。
例如，可以轻松地在 Q # 中实现所谓的 "*重复到-成功*" （ru）模式。
这些 ru 模式是概率的程序，这些程序在基本入口方面具有*预期*的低成本，但真正的成本取决于实际运行以及各种可能的 branchings 的实际交错。

为了便于重复到成功（ru）模式，Q # 支持构造

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
执行循环体，然后计算条件。
如果条件为 true，则语句已完成;否则，将执行修正，并从循环体开始重新执行该语句。

重复/等待循环的所有三个部分（正文、测试和修正）被视为*每个重复*的单个作用域，因此，在正文中绑定的符号可用于测试和修复中。
但是，完成修正的执行将结束语句的范围，以便在正文或修正期间进行的符号绑定在后续的重复中不可用。

而且， `fixup` 语句通常非常有用，但并非总是必需的。
如果不需要，构造
```qsharp
repeat {
    // do stuff
}
until (expression);
```
也是有效的 RUS 模式。

在此页的底部，我们提供[了一个 ru 循环的示例](#repeat-until-success-examples)。

> [!TIP]   
> 避免在函数内使用重复-until 循环。 当函数中的循环时，将提供相应的功能。 

## <a name="while-loop"></a>While 循环

重复-直到成功模式有一个非常特定于量程的内涵。 它们广泛用于特定的量程算法类，因此，它是 Q # 中的专用语言构造。 但是，在编译时，需要在量程运行时中特别小心地处理基于某个条件、其执行长度未知的循环。 另一方面，它们在函数中的使用是 unproblematic 的，因为它们仅包含将在常规（非量程）硬件上执行的代码。 

因此，Q # 支持仅在函数内使用 while 循环。 `while`语句由关键字 `while` 、左括号 `(` 、条件（即布尔表达式）、右括号 `)` 和语句块组成。
只要条件的计算结果为，就会执行语句块（循环的主体） `true` 。

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```


## <a name="return-statement"></a>Return 语句

Return 语句结束操作或函数的执行，并将值返回给调用方。
它包含关键字 `return` ，后跟适当类型的表达式和终止分号。

返回空元组的可调用 `()` 不需要 return 语句。
如果需要提前退出，则可 `return ()` 在此情况下使用。
返回任何其他类型的 Callables 需要最终的 return 语句。

操作中不存在最大返回语句数。
如果语句在块内跟随 return 语句，则编译器可能会发出警告。

例如，
```qsharp
return 1;
```
或
```qsharp
return ();
```
或
```qsharp
return (results, qubits);
```

## <a name="fail-statement"></a>Fail 语句

Fail 语句结束操作的执行，并将错误值返回给调用方。
它包含关键字 `fail` ，后跟一个字符串和一个终止分号。
该字符串返回到传统驱动程序作为错误消息。

操作中的 fail 语句数量没有限制。
如果语句在块中跟随 fail 语句，则编译器可能会发出警告。

例如，
```qsharp
fail $"Impossible state reached";
```
或者，使用内[插字符串](xref:microsoft.quantum.guide.expressions#interpolated-strings)
```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="repeat-until-success-examples"></a>重复执行-直到成功示例

### <a name="rus-pattern-for-single-qubit-rotation-about-an-irrational-axis"></a>针对无理数轴的单个 qubit 旋转的 ru 模式 

在典型用例中，以下 Q # 操作实现绕 Bloch 球上的无理数轴（I + 2i Z）/\sqrt $ 围绕 {5} 的旋转。 这是通过使用已知的 RUS 模式来实现的：

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

### <a name="rus-loop-with-mutable-variable-in-scope"></a>作用域中具有可变变量的 ru 循环

此示例演示如何使用可变变量，该变量 `finished` 位于整个重复截止到修正循环范围内，并在循环之前进行了初始化并在修正步骤中更新。

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

例如，下面的代码是一种概率线路，它使用和入口实现重要的旋转门 $V _3 = （\boldone + 2 i Z）/\sqrt {5} $ `H` `T` 。
该循环平均终止 $ \frac {8} {5} $ 重复。
有关更多详细信息，请参阅[*qubit unitaries 的非确定性分解*](https://arxiv.org/abs/1311.1074)（Paetznick 和 Svore，2014）。

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

最后，我们将演示一个用于 {1} {3} {2} {0} {1} 从 $ \ket +} $ 状态中开始准备量子状态 $ \frac {\sqrt} \left （\sqrt \ket + \right \ket{） $ 的 ru 模式的示例。
另请参阅[标准库提供的单元测试示例](https://github.com/microsoft/Quantum/blob/master/samples/diagnostics/unit-testing/RepeatUntilSuccessCircuits.qs)：

```qsharp
operation PrepareStateUsingRUS(target : Qubit) : Unit {
    using (auxiliary = Qubit()) {
        H(auxiliary);
        repeat {
            // We expect the target and auxiliary qubits to each be in
            // the |+> state.
            AssertProb(
                [PauliX], [target], Zero, 1.0,
                "target qubit should be in the |+> state", 1e-10 );
            AssertProb(
                [PauliX], [auxiliary], Zero, 1.0,
                "auxiliary qubit should be in the |+> state", 1e-10 );

            Adjoint T(auxiliary);
            CNOT(target, auxiliary);
            T(auxiliary);

            // The probability of measuring |+> state on the auxiliary qubit
            // is 3/4.
            AssertProb(
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

此操作中所示的明显编程功能是循环中更复杂 `fixup` 的部分，它涉及量程操作，并使用 `AssertProb` 语句来确定在程序中的某些指定点测量量程状态的概率。
有关和操作的详细信息，另请参阅[测试和调试](xref:microsoft.quantum.guide.testingdebugging) [`Assert`](xref:microsoft.quantum.intrinsic.assert) [`AssertProb`](xref:microsoft.quantum.intrinsic.assertprob) 。


## <a name="next-steps"></a>后续步骤

了解问题解答 # 中的[测试和调试](xref:microsoft.quantum.guide.testingdebugging)。