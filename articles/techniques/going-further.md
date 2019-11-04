---
title: 'Q # 技术-进一步 |Microsoft Docs'
description: 'Q # 技术-进一步'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 4677b0f9c4f64a9c1bc46d34e8a883dc006ba8f0
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183295"
---
# <a name="going-further"></a>进一步 #

现在，你已了解如何在 Q # 中编写有趣的量程程序，本部分将进一步介绍一些更高级的主题，这些主题将有助于今后使用。

<!-- Moved Debugging and Testing Quantum Programs section to a separate article -->

## <a name="generic-operations-and-functions"></a>泛型操作和函数 ##

> [!TIP]
> 本节假定一些基本熟悉[中C#的泛型](https://docs.microsoft.com/dotnet/csharp/programming-guide/generics/introduction-to-generics)、[泛型中F#](https://docs.microsoft.com/dotnet/fsharp/language-reference/generics/)的泛型、 [ C++模板](https://docs.microsoft.com/cpp/cpp/templates-cpp)或类似的方法，以用于其他语言的元编程。

我们可能想要定义的许多函数和操作实际上不依赖于其输入类型，而只是通过其他函数或操作隐式使用其类型。
例如，请考虑许多功能语言共有的*地图*概念;给定一个函数 $f （x） $，值为 $\{的集合 $ x_1，x_2，\dots ..，x_n\}$，map 返回一个新的集合 $\{f （x_1）、f （x_2）、\dots ..、f （x_n）\}$。
若要在 Q # 中实现此功能，我们可以利用该函数作为第一类。
接下来，编写 `Map`的快捷示例，使用★作为占位符，同时找出所需的类型。

```qsharp
function Map(fn : ★ -> ★, values : ★[]) : ★[] {
    mutable mappedValues = new ★[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

请注意，无论替换的实际类型是什么，此函数的外观都是相同的。
例如，从整数到 Paulis 的映射与从浮点数到字符串的映射大致相同：

```qsharp
function MapIntsToPaulis(fn : Int -> Pauli, values : Int[]) : Pauli[] {
    mutable mappedValues = new Pauli[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}

function MapDoublesToStrings(fn : Double -> String, values : Double[]) : String[] {
    mutable mappedValues = new String[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

原则上，我们可以编写一对我们遇到的每对类型的 `Map` 版本，但这会带来很多麻烦。
例如，如果我们在 `Map`中找到 bug，则必须确保在所有版本的 `Map`中统一应用修补程序。
此外，如果我们构造新的元组或 UDT，则现在还必须构造一个新的 `Map` 来与新类型一起工作。
虽然这对于少量此类函数是易的，但由于我们收集与 `Map`相同窗体的更多函数，因此引入新类型的成本将以相当短的顺序变为太。

但这种情况很难得到，因为我们没有为编译器提供所需的信息，以确定不同版本的 `Map` 是如何相关的。
实际上，我们希望编译器将 `Map` 视为从 Q #*类型*到 q # 函数的某种数学函数。
此概念的形式为：允许函数和操作具有*类型参数*，以及其普通元组参数。
在上述示例中，我们希望在第一种情况下将 `Map` 视为具有类型 `Int, Pauli` 参数，并在第二种情况下 `Double, String`。
大多数情况下，可以像使用普通类型一样使用这些类型参数：我们使用类型参数的值来生成数组和元组，调用函数和操作，并将其分配给普通或可变变量。

> [!NOTE]
> 间接依赖关系的最极端情况是 qubits，其中 Q # 程序无法直接依赖于 `Qubit` 类型的结构，但**必须**将此类类型传递给其他操作和函数。

返回到上面的示例，我们可以看到，我们需要 `Map` 具有类型参数，一个用于表示 `fn` 的输入，另一个用于表示 `fn`的输出。
在 Q # 中，这是通过在其声明中的函数或操作名称后面添加尖括号（即 `<>`，而不是 brakets $ \braket{}$！）来编写的，并列出每个类型参数。
每个类型形参的名称必须以刻度 `'`开头，这表示它是一个类型形参，而不是一个普通类型（也称为*具体*类型）。
对于 `Map`，我们编写：

```qsharp
function Map<'Input, 'Output>(fn : 'Input -> 'Output, values : 'Input[]) : 'Output {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

请注意，`Map<'Input, 'Output>` 的定义似乎与之前编写的版本非常类似。
唯一的区别是，我们已明确通知编译器 `Map` 不直接依赖于 `'Input` 和 `'Output`，但可通过 `fn`间接使用这两种类型。
通过这种方式定义 `Map<'Input, 'Output>` 后，可以像调用普通函数一样调用它：

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, we assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> 编写泛型函数和操作是一个位置，其中 "元组即用元组" 是一种非常有用的方法，用于考虑 Q # 函数和操作。
> 由于每个函数只采用一个输入并返回一个输出，因此类型 `'T -> 'U` 的输入与*任何*Q # 函数匹配。
> 同样，可以将任何操作传递到 `'T => 'U`类型的输入。

作为第二个示例，请考虑编写一个函数，该函数返回两个其他函数的组合：

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

在此，我们必须准确指定 `A`、`B`和 `C` 的内容，因此会严重限制新 `Compose` 函数的实用工具。
毕竟，`Compose` 仅依赖于*通过*`innerFn` 和 `outerFn``A`、`B`和 `C`。
作为替代方法，我们可以将类型参数添加到 `Compose`，这表示它适用于*任何*`A`、`B`和 `C`，前提是这些参数与 `innerFn` 和 `outerFn`所需的参数匹配。:

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

Q # 标准库提供了多种类型参数化操作和函数，使更高顺序控制流更易于表达。
" [Q # 标准库指南](xref:microsoft.quantum.libraries.standard.intro)" 中进一步讨论了这些问题。

## <a name="borrowing-qubits"></a>借贷 Qubits ##

使用借款机制，可以在计算过程中将 qubits 分配为暂存空间。 这些 qubits 通常不处于干净状态，也就是说，它们不一定在已知状态（如 $ \ket{0}$）中进行初始化。 还有一个 "脏" qubits，因为其状态为未知，甚至可以与量程计算机内存的其他部分放大。 在脏 qubits 的已知用例中，是多控制 CNOT-CONTAINS 入口的实现，只需很少的 qubits 和实现 incrementers。

在 canon 中，有使用 `borrowing` 关键字的示例，例如函数 `MultiControlledXBorrow` 在下面定义。
如果 `controls` 表示应该添加到 `X` 操作的控件 qubits，则此实现将添加 `Length(controls)-2` 许多脏 ancillas 的总体。

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

请注意，在此示例中，广泛使用 `With` 连结符---的形式，适用于支持 adjoint 的操作，即，`WithA`---在此示例中进行，这是一个很好的编程风格，它是将控件添加到仅涉及 `With`将控制传播到内部操作。 另外请注意，除了操作 `body` 外，还显式提供操作的 `controlled` 体实现，而不是采用 `controlled auto` 语句。 这样做的原因是，我们从线路的结构中知道如何轻松添加更多的控件，这与将控件添加到 `body`中的每个门和每个单独的门相比，更有利。 

将此代码与其他 canon 函数进行比较是有益的 `MultiControlledXClean` 该函数实现了执行乘法控制的 `X` 操作的相同目标，然而，这种方法使用了 `using` 机制。 
