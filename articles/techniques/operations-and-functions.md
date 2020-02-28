---
title: 'Q # 操作和函数'
description: '了解 Q # 操作和函数，以及如何将它们应用于量程计划中。'
uid: microsoft.quantum.techniques.opsandfunctions
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 43f0cf2da192a607e514d0c7de57a9bdd067faf7
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907658"
---
# <a name="q-operations-and-functions"></a>Q # 操作和函数

Q # 程序由一个或多个*操作*组成，这些操作描述量程操作对量程数据的影响，以及允许修改传统数据的一个或多个*函数*。 与操作不同的是，函数用于描述纯粹的传统行为，在计算经典输出值以外，不会产生任何影响。

在 Q # 中定义的每个操作都可以调用任意数量的其他操作，包括由语言定义的内置内部操作。 定义这些内部操作的特定方式取决于目标计算机。 在编译时，每个操作都表示为可提供给目标计算机的 .NET 类类型。

## <a name="defining-new-operations"></a>定义新操作

如上所述，用 Q # 编写的量程程序的最基本构建基块是一项操作，该*操作*可以从传统的 .net 应用程序（例如，使用模拟器）或在 Q # 内的其他操作中调用。
每个操作都使用一个输入，生成一个输出，并为一个或多个专用操作指定实现。
例如，以下操作仅定义默认的主体特殊化，并采用单个 qubit 作为输入，然后对该输入调用内置 `X` 操作：

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

关键字 `operation` 开始操作定义，后跟名称;此处，`BitFlip`。
接下来，输入的类型定义为 `Qubit`，以及用于引用新操作中输入的名称 `target`。
同样，`Unit` 定义操作的输出为空。
这与 `void` C#和其他命令式语言类似，并且与其他功能语言中F# `unit` 等效。

> [!NOTE]
> 我们将在下面更详细地探讨这一点，但 Q # 中的每个操作仅采用一个输入，并只返回一个输出。
> 然后使用*元组*表示多个输入和输出，并将多个值一起收集到单个值中。
> 非正式地说，Q # 是一种 "元组 out" 语言。
> 按照此概念，`()` 应作为 `Unit`类型的 "空" 元组读取。

在新操作中，如果只需显式指定默认正文专用化的实现，则可在声明中直接指定实现。 此外，还可以定义一个或多个 `functor` 操作的实现，如下所述。 在上面的示例中，唯一的语句是调用内置的 Q # 操作 <xref:microsoft.quantum.intrinsic.x>。

与 `Unit`相比，操作还会返回更有趣的类型。
例如，<xref:microsoft.quantum.intrinsic.m> 操作返回 `Result`类型的输出，表示已执行了度量值。 我们可以将操作的输出传递给另一个操作，也可以将其与 `let` 关键字一起使用来定义新变量。
<!-- Link to UID for superdense conceptual and example documentation. -->
这允许表示在较低级别与量程操作交互的传统计算，如 superdense 编码：

```qsharp
operation Superdense(here : Qubit, there : Qubit) : (Result, Result) {

    CNOT(there, here);
    H(there);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```
### <a name="functors-adjoint-and-controlled"></a>函子、adjoint 和受控
如果操作实现了单一转换，则可以定义操作在*adjointed*或*控制*时的行为方式。 操作的 adjoint 专用化指定了它在反向运行时的行为方式，而受控专用化指定了在应用于量程寄存器状态时操作的行为方式。
在以下示例中，可以将这些专用化的存在声明为操作签名的一部分： `is Adj + Ctl`。 然后，编译器将生成每个此类隐式声明的专用化的相应实现。 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```

> [!NOTE]
> Q # 中的许多操作表示单一入口。
> 如果 $U $ 是操作 `U`所表示的单一入口，则 `Adjoint U` 表示单一入口 $U ^ \dagger $。

如果编译器无法生成实现，则可以显式指定实现。 此类显式专用化声明可以包含合适的生成指令或用户定义的实现。 例如，上面 `PrepareEntangledPair` 中的代码等效于以下代码，其中包含显式专用化声明： 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    adjoint auto; // auto-generate adjoint specialization
    controlled auto; // auto-generate controlled specialization
    controlled adjoint auto; // auto-generate controlled adjoint specialization
}
```
关键字 `auto` 指示编译器应该确定如何生成专用化实现。
如果编译器无法自动生成特定专用化的实现，或者如果可以提供更有效的实现，则也可以手动定义该实现。

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```
在上面的示例中，`adjoint invert;` 指示将通过反 `controlled adjoint invert;` 体实现生成 adjoint 专用化，并通过反转受控专用化的给定实现来生成受控 adjoint 专用化。

我们将在[更高顺序控制流](xref:microsoft.quantum.concepts.control-flow)中看到更多的示例。

若要调用操作的专用化，请使用 `Adjoint` 或 `Controlled` 关键字。
例如，可以通过使用 `PrepareEntangledPair` 的 adjoint 将放大状态转换回 unentangled qubits 对，来编写更多的简洁地：

```qsharp
operation Superdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

设计用于函子的操作时，需要考虑一些重要的限制。
大多数情况下，编译器不能自动生成使用任何其他操作的输出值的操作的专用化，因为在此类操作中，如何对语句重新排序以获得相同的效果。


## <a name="defining-new-functions"></a>定义新函数

Q # 还允许定义函数，这些*函数*与操作截然不同，因为不允许在计算输出值之前有任何影响。
特别是，函数不能调用操作、对 qubits 执行操作、采样随机数，或依赖于输入值超出函数的状态。
因此，Q # 函数是*纯*的，因为它们始终将相同的输入值映射到相同的输出值。
这样，在生成操作专用化时，Q # 编译器就可以安全地重新排序调用函数的方式和时间。

定义函数的工作方式与定义操作类似，但不能为函数定义 adjoint 或受控专用化。
例如：

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```
只要有可能，就可以根据函数（而不是操作）编写传统逻辑，以便可以更轻松地在操作中使用。
例如，如果我们将 `Square` 编写为一个操作，则编译器将无法确保使用相同的输入调用它会以一致的方式生成相同的输出。

若要在函数和操作之间使用下划线，请考虑经典的问题：从 Q # 操作中采样随机数字：

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

每次调用 `U` 时，它将对 `target`执行不同的操作。
特别是，如果我们将 `adjoint auto` 特殊化声明添加到 `U`，则编译器无法保证 `U(target); Adjoint U(target);` 作为标识（即，非 op）。
这违反了我们在[向量和矩阵](xref:microsoft.quantum.concepts.vectors)中看到的 adjoint 定义，使在我们调用操作的操作中自动生成 adjoint 特殊化，<xref:microsoft.quantum.math.randomreal> 会破坏编译器提供的保证;<xref:microsoft.quantum.math.randomreal> 是不存在 adjoint 或受控版本的操作。

另一方面，允许 `Square` 等函数调用是安全的，因为编译器可以确保只需将输入保留到 `Square`，以便保持其输出稳定。
因此，将尽可能多的传统逻辑隔离到函数中，可以轻松地在其他函数和操作中重复使用该逻辑。

## <a name="control-flow"></a>控制流

在操作或函数中，每个语句都按顺序执行，类似于最常见的命令性传统语言。
不过，可以通过三种不同的方式来修改这种控制流：

- `if` 语句
- `for` 循环
- `repeat`-`until` 循环

我们将讨论这一话题，直到我们讨论了[重复到成功（ru）](xref:microsoft.quantum.techniques.qubits#measurements)的线路。
不过，`if` 和 `for` 控制流构造，请在大多数传统编程语言中进行熟悉。
具体而言，`if` 语句可以采用一个条件，后面可以跟一个或多个 `elif` 语句，并可能以 `else`结尾：

```qsharp
if (pauli == PauliX) {
    X(qubit);
} elif (pauli == PauliY) {
    Y(qubit);
} elif (pauli == PauliZ) {
    Z(qubit);
} else {
    fail "Cannot use PauliI here.";
}
```

同样，`for` 循环指示对一个整数范围或数组的元素进行迭代：

```qsharp
for (idxQubit in 0..nQubits - 1) {
    // Do something to idxQubit...
}
```

重要的是，`for` 循环和 `if` 语句甚至可用于自动生成专用化的操作。 在这种情况下，`for` 循环的 adjoint 会反转方向，并 adjoint 每次迭代。
这遵循了 "鞋和 socks" 原则：如果你想要撤消对 socks 和鞋的投入，则必须撤消鞋，然后撤消放置在 socks 上。
在您仍戴鞋的同时，小猫的工作效率更小，并使您的 socks 保持不变！

## <a name="operations-and-functions-as-first-class-values"></a>操作和函数作为第一类值

使用函数（而不是操作）对控制流和传统逻辑的推理的一项重要技巧是，使用 Q # 中的操作和函数作为*第一类*。
也就是说，它们本身就是语言中的每个值。
例如，下面是非常有效的 Q # 代码，如果没有间接的：

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

上面的代码段中的变量 `ourH` 的值是 <xref:microsoft.quantum.intrinsic.h>操作，因此我们可以像调用任何其他操作一样调用该值。
这样，我们就可以编写执行操作的操作作为其输入的一部分，形成更高顺序的控制流概念。
例如，我们可以通过将其应用两次到相同的目标 qubit，来想像 "正方形" 的操作。

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

在此示例中，类型 `(Qubit => Unit)` 中出现的 `=>` 箭头表示输入字段 `op` 是一个操作，该操作将 `Qubit` 类型作为其输入，并生成一个空元组作为其输出。
此外，我们还指定该操作类型的特征，其中包含有关受支持的函子的信息。
`(Qubit => Unit)` 类型的操作不支持 `Adjoint` 和 `Controlled` 函子。 如果要指示该类型的操作必须支持，例如 `Adjoint` 函子，则必须将其声明为 adjointable。 这是通过使用批注 `is Adj` 到类型来完成的。 同样，`(Qubit => Unit is Ctl)` 表示该类型的操作支持 `Controlled` 函子。 我们将在更常见的[Q # 中讨论类型](xref:microsoft.quantum.language.type-model)时进一步探讨这一点。

现在，我们强调，我们还可以将操作作为输出的一部分返回，以便可以将某些类型的传统条件逻辑隔离为传统函数，这将以操作的形式返回量程程序的说明。
作为一个简单的示例，请考虑 teleportation 示例，在该示例中，接收两位传统消息的参与方需要使用该消息将其 qubit 解码为正确的 teleported 状态。
我们可以编写一个函数，该函数采用这两个传统位并返回正确的解码操作。

```qsharp
function TeleporationDecoderForMessage(hereBit : Result, thereBit : Result)
: (Qubit => Unit is Adj + Ctl) {

    if (hereBit == Zero && thereBit == Zero) {
        return I;
    } elif (hereBit == One && thereBit == Zero) {
        return X;
    } elif (hereBit == Zero && thereBit == One) {
        return Z;
    } else {
        return Y;
    }
}
```

此新函数确实是一个函数，在这种情况下，如果使用 `hereBit` 和 `thereBit`的相同值调用该函数，则将始终返回相同的操作。
因此，可以安全地在操作内部运行解码器，而无需考虑解码逻辑如何与不同操作专用化的定义交互。
也就是说，我们已在函数内隔离了传统逻辑，从而保证编译器可以使用 impunity 重新排序函数调用，只要保留输入即可。

我们还可以将函数视为第一类值，因为我们会在讨论[操作和函数类型](#operations-and-functions-as-first-class-values)时更详细地介绍这些值。

## <a name="partially-applying-operations-and-functions"></a>部分应用操作和函数

通过使用*部分应用程序*返回操作的函数，我们可以更多地执行此操作，在这种情况下，我们可以向函数或操作提供一个或多个输入部分，而无需实际调用它。 例如，如果调用上面的 `ApplyTwice` 示例，则可以指示我们不想立即指定输入操作应应用到的 qubit：

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

在这种情况下，本地变量 `twiceOp` 包含部分应用的操作 `ApplyTwice(op, _)`，其中尚未指定的部分输入由 `_`指示。
当我们实际调用下一行中的 `twiceOp` 时，我们会将输入的剩余部分的所有剩余部分作为初始操作传递给部分应用的操作。
因此，上面的代码段实际上等同于直接调用 `ApplyTwice(op, target)`，因此，我们引入了一个新的本地变量，使我们能够在提供输入的某些部分时延迟调用。

由于在提供了整个输入之前，不会实际调用已部分应用的操作，因此可以安全地部分应用操作，即使是在函数内也是如此。

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

原则上，`SquareOperation` 中的传统逻辑可能会更多地涉及到，但它仍与操作的其余部分隔离，因为编译器可以提供函数。
此方法将在整个 Q # 标准库中使用，以便以一种可随时在量程程序中使用的方式表示传统控制流。
