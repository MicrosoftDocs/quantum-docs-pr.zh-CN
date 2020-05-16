---
title: 问答中的操作和函数#
description: 如何定义和调用操作和函数，以及受控和 adjoint 操作专用化。
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.operationsfunctions
ms.openlocfilehash: bc9695b85b68807801225ccbc903a4622b450768
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431064"
---
# <a name="operations-and-functions-in-q"></a>问答中的操作和函数#

## <a name="defining-new-operations"></a>定义新操作

操作是 Q # 的核心。
声明后，可以从传统 .NET 应用程序（例如，使用模拟器）调用，也可以由 Q # 内的其他操作调用。
在 Q # 中定义的每个操作都可以调用任意数量的其他操作，包括由语言定义的内置内部操作。 定义这些内部操作的特定方式取决于目标计算机。
在编译时，每个操作都表示为可提供给目标计算机的 .NET 类类型。

每个 Q # 源文件可以定义任意数量的操作。
操作名称在命名空间中必须唯一，并且不能与类型或函数名冲突。

操作声明由关键字组成 `operation` ，后跟作为操作名称的符号、定义操作的参数的类型化标识符元组、冒号 `:` 、描述操作结果类型的类型批注、有操作特征的批注、左大括号 `{` 、操作声明的正文和最终右大括号 `}` 。

每个操作都使用一个输入，生成一个输出，并为一个或多个专用操作指定实现。
下面详细说明了可能的专用化，以及如何定义/调用它们。
现在，请考虑以下操作，该操作仅定义默认的主体特殊化并使用单个 qubit 作为其输入，然后对 <xref:microsoft.quantum.intrinsic.x> 该输入调用内置操作：

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

关键字将 `operation` 开始操作定义，后跟名称; 此处为 `BitFlip` 。
接下来，输入的类型定义为，并 `Qubit` 将定义为 `target` 在新操作中引用输入。
同样， `Unit` 定义操作的输出为空。
这类似于 `void` c # 和其他命令式语言，与 `unit` F # 和其他功能语言等效。

操作还可以返回比更有趣 `Unit` 的类型。
例如， <xref:microsoft.quantum.intrinsic.m> 操作返回类型的输出，该输出 `Result` 表示已执行了一个度量值。 我们可以将操作的输出传递给另一个操作，也可以将其与关键字一起使用 `let` 来定义新变量。

这允许表示在较低级别与量程操作交互的传统计算，如[superdense 编码](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding)：

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {

    CNOT(there, here);
    H(there);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

> [!NOTE]
> Q # 中的每个操作都只采用一个输入，并只返回一个输出。
> 然后使用*元组*表示多个输入和输出，并将多个值一起收集到单个值中。
> 非正式地说，Q # 是一种 "元组 out" 语言。
> 遵循此概念后， `()` 应将其作为 "empty" 元组（类型为）进行读取 `Unit` 。


## <a name="controlled-and-adjoint-operations"></a>受控和 Adjoint 操作

如果某个操作实现了单一转换（如 Q # 中的多个操作），则可以定义操作在*adjointed*或*控制*时的行为方式。 操作的*adjoint*专用化指定操作的 "反转" 的行为方式，而*受控*专用化指定操作在其应用程序的应用程序在特定量程寄存器状态下运行时的行为方式。

量程操作的 Adjoints 对量程计算的许多方面都至关重要。 接下来，在 "[语态](#conjugations)" 部分中，你将发现一种此类情况与有用的 Q # 编程方法一起讨论。

操作的受控版本是新操作，仅当所有控件 qubits 都处于指定状态时，才会有效地应用基本操作。
如果控件 qubits 在 superposition 中，则会将基本操作一致应用到 superposition 的相应部分。
因此，受控操作通常用于生成牵连。

当然，还可以使用*受控的 adjoint*特殊化来指定操作 adjoint 的受控应用。

> [!NOTE]
> 如果 $U $ 是操作实现的单一转换 `U` ，则 `Adjoint U` 表示 $U ^ \dagger $ 的单一转换，这是复杂的共轭转置。
> 依次应用某一操作，然后将其 adjoint 的状态保持不变，如 $UU ^ \dagger = U ^ \dagger U = \id $，则为恒等矩阵。
> 受控操作的单一表示形式略微微妙，但可以在量程计算概念中找到更多详细信息[：多个 qubits](xref:microsoft.quantum.concepts.multiple-qubits)。

以下部分介绍如何在 Q # 代码中调用这些不同的专用化。
下面详细介绍了如何定义操作来支持它们。

### <a name="calling-operation-specializations"></a>调用专用操作

Q # 中的*函子*是一个工厂，它定义了其他操作的新操作。
Q # 中的两个标准函子是 `Adjoint` 和 `Controlled` 。

在定义新操作的实现时，函子有权访问基操作的实现。
因此，函子可以比传统的高级函数执行更复杂的功能。 函子在 Q # 类型系统中没有表示形式。 因此，目前不可能将其绑定到变量或将其作为参数传递。 

函子可通过将其应用于操作来使用，返回新操作。
例如，将 `Adjoint` 函子应用到操作后生成的操作 `Y` 将编写为 `Adjoint Y` 。
然后，可以像任何其他操作一样调用新操作。
对于支持 `Adjoint` 和/或函子的应用程序的操作 `Controlled` ，其返回类型必须为 `Unit` 。 

#### <a name="adjoint-functor"></a>`Adjoint`函子

因此，将 `Adjoint Y(q1)` Adjoint 函子应用于 `Y` 操作以生成新的操作，并将该新操作应用于 `q1` 。
新操作与基本操作具有相同的签名和类型 `Y` 。
具体而言，新操作也允许 `Adjoint` ，并且 `Controlled` 仅当基本操作执行时才允许。
Adjoint 函子是其自身的反向;也就是说， `Adjoint Adjoint Op` 始终与相同 `Op` 。

#### <a name="controlled-functor"></a>`Controlled`函子

同样， `Controlled X(controls, target)` 将受控函子应用于 `X` 操作以生成新的操作，并将该新操作应用于 `controls` 和 `target` 。

> [!NOTE]
> 在 Q # 中，受控版本始终采用控件 qubits 的数组，并且指定的状态始终是所有控件 qubits 都处于计算（ `PauliZ` ） `One` 状态 $ \ket {1} $。
> 可以通过将适当的单一操作应用于受控操作之前的控件 qubits 来实现基于其他状态的控制，然后在受控操作后应用单一操作的逆。
> 例如， `X` 将操作应用于受控操作前后的控件 qubit 会导致操作控制 `Zero` 该 qubit 的状态（$ \ket {0} $）; 应用 `H` 操作之前和之后，将控制该 `PauliX` `One` 状态，即-1 eigenvalue of Pauli X，$ \ket {-} \mathrel{： =} （\ket {0} -\ket {1} ）/\sqrt {2} $，而不是 `PauliZ` `One` 状态。

给定操作表达式，可以使用函子生成新的操作表达式 `Controlled` 。
新操作的签名基于原始操作的签名。
结果类型是相同的，但输入类型是具有 qubit 数组的两元组，它将控件 qubit 保存为第一个元素，并将原始操作的参数作为第二个元素。
新操作支持 `Controlled` ，且 `Adjoint` 仅当原始操作执行时才支持。

如果原始操作只使用了一个参数，则会在此处播放单独的元组等效性。
例如， `Controlled X` 是操作的受控版本 `X` 。 
`X`具有类型 `(Qubit => Unit is Adj + Ctl)` ，因此 `Controlled X` 具有类型 `((Qubit[], (Qubit)) => Unit is Adj + Ctl)` ; 由于单一元组等效，这与相同 `((Qubit[], Qubit) => Unit is Adj + Ctl)` 。

如果基本操作采用多个参数，请记住将操作的受控版本的相应参数括在括号中，以将其转换为元组。
例如， `Controlled Rz` 是操作的受控版本 `Rz` 。 
`Rz`具有类型 `((Double, Qubit) => Unit is Adj + Ctl)` ，因此 `Controlled Rz` 具有类型 `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)` 。
因此，将 `Controlled Rz(controls, (0.1, target))` 是的有效调用 `Controlled Rz` （请注意两边的括号 `0.1, target` ）。

作为另一个示例， `CNOT(control, target)` 可以实现为 `Controlled X([control], target)` 。 如果目标应由2个 control qubits （CCNOT）控制，则可以使用 `Controlled X([control1, control2], target)` 语句。

#### `Controlled Adjoint` 

`Controlled`和 `Adjoint` 函子的上下班，因此应用或之间没有区别 `Controlled Adjoint Op` `Adjoint Controlled Op` 。


## <a name="defining-controlled-and-adjoint-implementations"></a>定义受控和 Adjoint 实现

在上面的第一个操作声明示例中，操作 `BitFlip` 和 `DecodeSuperdense` 分别定义为签名 `(Qubit => Unit)` 和 `((Qubit, Qubit) => (Result, Result))` 。
`DecodeSuperdense`这并不是一个单一的操作，因此，它不是单一操作，因此，不能有控制的 adjoint 专用化不能存在（重新调用此类操作返回的相关要求 `Unit` ）。
但是， `BitFlip` 只需执行单一 <xref:microsoft.quantum.intrinsic.x> 操作，就可以将其定义为专用化。

在这里，我们详细介绍了如何在 Q # 操作声明中包含特殊化的存在性，从而使它们能够与 `Adjoint` and/or 函子一起调用 `Controlled` 。
在[下面](#circumstances-for-validly-defining-specializations)的部分中，我们介绍了在声明特定专用化的有效或无效情况下的某些情况。

操作特征定义哪些类型的函子可以应用于声明的操作以及它们有什么影响。 这些专用化的存在可以声明为操作签名的一部分，具体而言，具有操作特征： `is Adj` 、 `is Ctl` 或 `is Adj + Ctl` 。
可以*隐式*或*显式*定义每个特殊化的实际实现。

### <a name="implicitly-specifying-implementations"></a>隐式指定实现

在这种情况下，操作声明的主体只包含默认实现。 例如：

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```
此处，编译器会自动生成每个此类隐式声明的专用化的对应实现，以在 `Adjoint` 使用或 `Controlled` 函子时执行。

因此，对的调用 `Adjoint PrepareEntangledPair` 将导致编译器实现的 adjoint `CNOT` ，然后实现的 adjoint `H` 。
这些单独的操作都是 adjoint 的，因此，生成的 `Adjoint PrepareEntangledPair` 操作只包含应用 `CNOT(here, there)` 和 `H(here)` 。
因此，我们可以 `DecodeSuperdense` 通过使用 adjoint `PrepareEntangledPair` 将放大状态转换回 qubits 的 unentangled 对，使用它来编写更简洁地的示例：

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

声明中具有操作特征的批注非常有用，可确保编译器根据默认实现自动生成其他专用化。 

设计用于函子的操作时，需要考虑一些重要的限制。
大多数情况下，编译器*不能*自动生成使用任何其他操作的输出值的操作的专用化，因为在此类操作中，如何对语句重新排序以获得相同的效果。

因此，显式指定各种实现通常非常有用。

### <a name="explicitly-specifying-implementations"></a>显式指定实现

如果编译器无法生成实现，则可以显式指定实现。 此类显式专用化声明可以包含合适的*生成指令*或用户定义的实现。
在这里，我们提供了各种可能性，其中包含以下示例。


#### <a name="explicit-specialization-declarations"></a>显式专用化声明

Q # 操作可能包含以下显式专用化声明：

- `body`专用化指定未应用函子的操作的实现。
- `adjoint`专用化指定应用了函子的操作的实现 `Adjoint` 。
- `controlled`专用化指定应用了函子的操作的实现 `Controlled` 。
- `controlled adjoint`专用化指定操作的实现，同时 `Adjoint` `Controlled` 应用和函子。
  此特殊化还可以命名 `adjoint controlled` ，因为这两个函子。


操作特殊化包含专业化标记（如或等）， `body` `adjoint` 后跟以下其中之一：

- 如下所述的显式声明。
- 告诉编译器*如何*生成专用化的*指令*，可以是：
  - `intrinsic`，它指示目标计算机提供专用化。
  - `distribute`，可与和专用化一起 `controlled` 使用 `controlled adjoint` 。
    当与一起使用时 `controlled` ，它指示编译器应通过将应用 `Controlled` 到中的所有操作来计算特殊化 `body` 。
    当与一起使用时 `controlled adjoint` ，它指示编译器应通过将应用 `Controlled` 到专用化中的所有操作来计算特殊化 `adjoint` 。
  - `invert`，它指示编译器应 `adjoint` 通过反序列化来计算特殊化 `body` ，即反转运算顺序并将 adjoint 应用于每个操作。
    当与一起使用时 `adjoint controlled` ，这指示编译器应通过反转专用化来计算特殊化 `controlled` 。
  - `self`，指示 adjoint 专用化与 `body` 专用化相同。
    这对和专用化是合法的 `adjoint` `adjoint controlled` 。
    对于 `adjoint controlled` ， `self` 表示 `adjoint controlled` 专用化与 `controlled` 特殊化相同。
  - `auto`，指示编译器应选择要应用的适当指令。
    `auto`不能用于 `body` 专用化。

指令和 `auto` 都需要右分号 `;` 。
`auto`如果提供了的显式声明，则指令将解析为以下生成指令 `body` ：

- `adjoint`根据指令生成专用化 `invert` 。
- `controlled`根据指令生成专用化 `distribute` 。
- `adjoint controlled` `invert` 如果为 `controlled` 指定了显式声明，而不是为指定了一个，则根据指令生成专用化 `adjoint` `distribute` 。

> [!TIP]   
> 如果操作是自我 adjoint 的，则通过生成指令显式指定 adjoint 或受控 adjoint 专用化，以便 `self` 编译器可以利用该信息进行优化。

包含用户定义的实现的专用化声明包含一个参数元组，后面跟有用于实现专用化的 Q # 代码的语句块。
在参数列表中， `...` 用于表示作为一个整体为操作声明的参数。
对于 `body` 和 `adjoint` ，参数列表应始终为 `(...)` ; 对于 `controlled` 和 `adjoint controlled` ，参数列表应为表示控件 qubits 数组的符号，后面跟有 `...` 括号括在括号中; 例如， `(controls,...)` 。

### <a name="examples"></a>示例

操作声明可能非常简单，如下所示：定义基元 Pauli X 操作：

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```
请注意，Pauli X 操作的 adjoint 是使用指令定义的， `self` 因为按定义 `X` 是其自身的反向运算。

上例中的代码 `PrepareEntangledPair` 等效于下面的代码，其中包含显式专用化声明： 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Ctl + Adj {
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

#### <a name="user-defined-specialization-implementation"></a>用户定义的特殊化实现

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
在上面的示例中， `adjoint invert;` 指示 adjoint 专用化是通过反转正文实现生成的，并指示将 `controlled adjoint invert;` 通过反转受控专用化的给定实现生成受控 adjoint 专用化。

如果需要显式声明默认正文之外的一个或多个特殊化，则默认体的实现也需要包装到适当的专用化声明中：

```qsharp
operation CountOnes(qubits: Qubit[]) : Int {

    body (...) // default body specialization
    {
        mutable n = 0;
        for (qubit in qubits) {
            set n += M(q) == One ? 1 | 0;
        }
        return n;
    }

    ...
```

### <a name="circumstances-for-validly-defining-specializations"></a>有效定义专用化的情况

#### <a name="operation-declarations-with-adjointcontrolled"></a>带有 adjoint/控制的操作声明

指定不具有 adjoint 或受控版本的操作是合法的。 例如，度量操作不具有，因为它们不可逆或可控制。

如果操作的 `Adjoint` `Controlled` 声明包含各自专用化的隐式或显式声明，则操作支持和/或函子。

显式声明的 adjoint/受控专用化意味着存在 adjoint/受控专用化。 

对于正文包含重复执行循环、set 语句、度量、return 语句或对不支持函子的其他操作的操作 `Adjoint` ， `invert` 不能通过或指令自动生成 adjoint 专用化 `auto` 。

对于其主体包含对不支持函子的其他操作的调用的操作 `Controlled` ，无法在或指令后自动生成受控专用 `distribute` 化 `auto` 。

#### <a name="controlled-adjoint"></a>受控 Adjoint

操作的受控 adjoint 版本指定如何实现该操作的 adjoint 的量程控制版本。
指定不具有受控 adjoint 版本的操作是合法的;例如，度量操作没有受控的 adjoint 版本，因为它们既不能控制也不可逆。

当且仅当存在 adjoint 和受控专用化时，操作的受控 adjoint 专用化才需要存在。 在这种情况下，如果未显式定义实现，则会推断出受控 adjoint 专用化的存在，并由编译器生成合适的专用化。 

对于其正文包含对没有受控 adjoint 版本的其他操作的调用的操作，不能在之后自动生成 adjoint 特殊化 `invert` `distribute` `auto` 。


### <a name="type-compatibility"></a>类型兼容性

具有更多函子支持的操作可能会在具有较少函子但需要相同签名的操作的任何位置使用。
例如，类型的操作可以在 `(Qubit => Unit is Adj)` 预期类型为的操作的任何位置使用 `(Qubit => Unit)` 。

Q # 对于可调用的返回类型是*协变*的：返回类型的可调用与 `'A` 具有相同输入类型的可调用和与兼容的结果类型兼容 `'A` 。

Q # 对于输入类型是*逆变*的：将类型作为输入的可调用与 `'A` 具有相同结果类型和与兼容的输入类型的可调用兼容 `'A` 。

也就是说，提供以下定义：

```qsharp
operation Invert(qubits : Qubit[]) : Unit 
is Adj {...} 

operation ApplyUnitary(qubits : Qubit[]) : Unit 
is Adj + Ctl {...} 

function ConjugateInvertWith(
    inner : (Qubit[] => Unit is Adj),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj) {...}

function ConjugateUnitaryWith(
    inner : (Qubit[] => Unit is Adj + Ctl),
    outer : (Qubit[] => Unit is Adj))
: (Qubit[] => Unit is Adj + Ctl) {...}
```

以下为 true：

- `ConjugateInvertWith`可以使用或的参数调用函数 `inner` `Invert` `ApplyUnitary` 。
- `ConjugateUnitaryWith`可以使用 `inner` 参数 `ApplyUnitary` （而不是）调用函数 `Invert` 。
- 类型的值 `(Qubit[] => Unit is Adj + Ctl)` 可以从返回 `ConjugateInvertWith` 。

> [!IMPORTANT]
> Q # 0.3 引入了用户定义类型的行为方面的显著差异。

用户定义的类型被视为基础类型的包装版本，而不是作为子类型。
这意味着，如果需要基础类型的值，用户定义类型的值将无法使用。


### <a name="conjugations"></a>语态

与传统位相比，释放量程内存会稍微增加一点，因为在 qubits 仍放大时，盲目重置 qubits 可能会对剩余计算产生意外影响。 在释放内存之前，可以通过正确的方式 "撤消" 已执行的计算来避免这种情况。 量程计算的常见模式如下： 

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    outerOperation(target);
    innerOperation(target);
    Adjoint outerOperation(target);
}
```

从0.9 版本开始，我们支持语态语句来实现上述转换。 使用该语句，可以通过 `ApplyWith` 以下方式实现操作：

```qsharp
operation ApplyWith<'T>(
    outerOperation : ('T => Unit is Adj), 
    innerOperation : ('T => Unit), 
    target : 'T) 
: Unit {

    within{ 
        outerOperation(target);
    }
    apply {
        innerOperation(target);
    }
}
```
如果外部和内部转换不能像操作那样轻松地提供，则这种语态语句就变得非常有用，但通过多个语句组成的块可以更方便地进行描述。 

在内块中定义的语句的反转换是由编译器自动生成的，并在 apply 块完成后执行。
由于不能在 apply 块中重新绑定用作内部块的一部分的任何可变变量，因此，生成的转换将保证为内块中计算的 adjoint。 


## <a name="defining-new-functions"></a>定义新函数

函数是在 Q # 中纯粹确定的传统例程，不同于操作，因为它们不允许在计算输出值之前有任何影响。
特别是，函数不能调用操作;操作、分配或借用 qubits;示例随机数;否则，依赖于输入值超出函数的状态。
因此，Q # 函数是*纯*的，因为它们始终将相同的输入值映射到相同的输出值。
这样，在生成操作专用化时，Q # 编译器就可以安全地重新排序调用函数的方式和时间。

每个 Q # 源文件可以定义任意数量的函数。
函数名称在命名空间中必须是唯一的，并且可能不会与操作或类型名称冲突。

定义函数的工作方式与定义操作类似，但不能为函数定义 adjoint 或受控专用化。
例如：

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```

或 

```qsharp
function DotProduct(a : Double[], b : Double[]) : Double {
    if (Length(a) != Length(b)) {
        fail "Arrays are not compatible";
    }

    mutable accum = 0.0;
    for (i in 0..Length(a)-1) {
        set accum += a[i] * b[i];
    }
    return accum;
}
```

### <a name="classical-logic-in-functions--good"></a>函数 = = 良好中的传统逻辑

只要有可能，就可以根据函数（而不是操作）编写传统逻辑，以便可以更轻松地在操作中使用。
例如，如果我们 `Square` 已编写上述声明作为*运算*，则编译器将无法确保使用相同的输入调用它会一致地生成相同的输出。

若要在函数和操作之间使用下划线，请考虑经典的问题：从 Q # 操作中采样随机数字：

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

每次 `U` 调用时，它将对执行不同的操作 `target` 。
特别是，如果我们将 `adjoint auto` 专用化声明添加到，则编译器无法保证将作为 `U` `U(target); Adjoint U(target);` 标识（即，非 op）。
这违反了我们在[矢量和矩阵](xref:microsoft.quantum.concepts.vectors)中看到的 adjoint 定义，使你能够在我们调用了该操作的操作中自动生成 adjoint 特殊化，这 <xref:microsoft.quantum.math.randomreal> 会破坏编译器提供的保证; <xref:microsoft.quantum.math.randomreal> 是不存在 adjoint 或受控版本的操作。

另一方面，允许函数调用（如） `Square` 是安全的，因为编译器可以确保只需将输入保留为，以便 `Square` 保持其输出稳定。
因此，将尽可能多的传统逻辑隔离到函数中，可以轻松地在其他函数和操作中重复使用该逻辑。


## <a name="generic-type-parameterized-callables"></a>泛型（类型参数化） Callables

我们可能想要定义的许多函数和操作实际上不依赖于其输入类型，而只是通过其他函数或操作隐式使用其类型。
例如，请考虑许多功能语言共有的*地图*概念;给定一个函数 $f （x） $，值为 $ x_1 的集合 \{ ，x_2，\dots ..，x_n \} $，map 返回一个新的集合 $ \{ f （x_1）、f （x_2）、\dots ..、f （x_n） \} $。
若要在 Q # 中实现此功能，我们可以利用该函数作为第一类。
让我们简单地编写一个示例 `Map` ，使用★作为占位符，同时找出所需的类型。

```qsharp
function Map(fn : (★ -> ★), values : ★[]) : ★[] {
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
function MapIntsToPaulis(fn : (Int -> Pauli), values : Int[]) : Pauli[] {
    mutable mappedValues = new Pauli[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}

function MapDoublesToStrings(fn : (Double -> String), values : Double[]) : String[] {
    mutable mappedValues = new String[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

原则上，我们可以 `Map` 为我们遇到的每对类型编写一个版本的，但这会带来很多麻烦。
例如，如果我们发现中的 bug `Map` ，则必须确保在的所有版本中统一应用此修补程序 `Map` 。
此外，如果我们构造新的元组或 UDT，则现在还必须构建一个新的 `Map` 来与新类型一起工作。
虽然这对于少量此类函数是易的，但由于我们收集与相同窗体的更多功能， `Map` 引入新类型的成本在很大程度上将变为太。

但这种情况很难得到，因为我们没有为编译器提供所需的信息，以确定不同版本的 `Map` 关联方式。
实际上，我们希望编译器将 `Map` q #*类型*中的某种数学函数视为 q # 函数。

此概念的形式为：允许函数和操作具有*类型参数*，以及其普通元组参数。
在上面的示例中，我们希望在 `Map` 第一种情况下将类型形参视为， `Int, Pauli` `Double, String` 在第二种情况下。
大多数情况下，可以像使用普通类型一样使用这些类型参数：我们使用类型参数的值来生成数组和元组，调用函数和操作，并将其分配给普通或可变变量。

> [!NOTE]
> 间接依赖关系的最极端情况是 qubits，其中 Q # 程序无法直接依赖类型的结构 `Qubit` ，但**必须**将此类类型传递给其他操作和函数。

返回到上面的示例，我们可以看到，我们需要 `Map` 具有类型参数，一个用于表示输入，另 `fn` 一个用于表示的输出 `fn` 。
在 Q # 中，这是通过 `<>` 在其声明中的函数或操作名称后面添加尖括号（即，不 brakets $ \braket $！）来编写的， {} 并列出每个类型参数。
每个类型形参的名称必须以计时周期开始 `'` ，指示它是一个类型形参，而不是一个普通类型（也称为*具体*类型）。
对于 `Map` ，我们编写：

```qsharp
function Map<'Input, 'Output>(fn : ('Input -> 'Output), values : 'Input[]) : 'Output[] {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

请注意，的定义与 `Map<'Input, 'Output>` 我们之前编写的版本非常类似。
唯一的区别是，我们已明确通知编译器 `Map` 不直接依赖于哪些内容 `'Input` `'Output` ，但也适用于任何两种类型，方法是通过从间接使用它们 `fn` 。
`Map<'Input, 'Output>`通过这种方式定义后，可以像调用普通函数一样调用它：

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, we assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> 编写泛型函数和操作是一个位置，其中 "元组即用元组" 是一种非常有用的方法，用于考虑 Q # 函数和操作。
> 由于每个函数只使用一个输入并返回一个输出，因此类型为的输入 `'T -> 'U` 与*任何*Q # 函数匹配。
> 同样，可以将任何操作传递到类型的输入 `'T => 'U` 。

作为第二个示例，请考虑编写一个函数，该函数返回两个其他函数的组合：

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

在此，我们必须明确指定 `A` 、 `B` 和， `C` 从而严格限制新函数的实用工具 `Compose` 。
毕竟， `Compose` 只依赖于 `A` 、和， `B` 并 `C` *通过* `innerFn` 和 `outerFn` 。
作为替代方法，我们可以将类型参数添加到 `Compose` ，这表示它适用于*任何* `A` 、 `B` 和 `C` ，前提是这些参数与和所需的参数匹配 `innerFn` `outerFn` ：

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


## <a name="callables-as-first-class-values"></a>Callables 作为第一类值

使用函数（而不是操作）对控制流和传统逻辑的推理的一项重要技巧是，使用 Q # 中的操作和函数作为*第一类*。
也就是说，它们本身就是语言中的每个值。
例如，下面是非常有效的 Q # 代码，如果没有间接的：

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

上面的代码段中的变量的值 `ourH` 为运算，以便 <xref:microsoft.quantum.intrinsic.h> 我们可以像其他任何操作一样调用该值。
这样，我们就可以编写执行操作的操作作为其输入的一部分，形成更高顺序的控制流概念。
例如，我们可以通过将其应用两次到相同的目标 qubit，来想像 "正方形" 的操作。

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

### <a name="returning-operations-from-a-function"></a>从函数返回操作

我们强调的是，我们还可以在输出过程中返回操作，以便将某些类型的传统条件逻辑隔离为传统函数，该函数将以操作的形式返回量程程序的说明。
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

此新函数确实是一个函数，在这种情况下，如果使用和的相同值调用该函数 `hereBit` `thereBit` ，则将始终返回相同的操作。
因此，可以安全地在操作内部运行解码器，而无需考虑解码逻辑如何与不同操作专用化的定义交互。
也就是说，我们已在函数内隔离了传统逻辑，从而保证编译器可以使用 impunity 重新排序函数调用，只要保留输入即可。


## <a name="partial-application"></a>部分应用程序

通过使用*部分应用程序*返回操作的函数，我们可以更多地执行此操作，在这种情况下，我们可以向函数或操作提供一个或多个输入部分，而无需实际调用它。 例如，若要调用 `ApplyTwice` 上面的示例，我们可以指示我们不想立即指定输入操作应应用到的 qubit：

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

在这种情况下，局部变量 `twiceOp` 包含部分应用的操作，在该操作中 `ApplyTwice(op, _)` ，尚未指定的部分输入由指示 `_` 。
当我们 `twiceOp` 在下一行中实际调用时，我们会将输入的剩余部分的所有剩余部分作为初始操作的输入传递给部分应用的操作。
因此，上面的代码段与直接调用相同，因此， `ApplyTwice(op, target)` 我们引入了新的局部变量，使我们能够在提供输入的某些部分时延迟调用。

由于在提供了整个输入之前，不会实际调用已部分应用的操作，因此可以安全地部分应用操作，即使是在函数内也是如此。

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

原则上，中的传统逻辑 `SquareOperation` 可能会更多地涉及到，但它仍与操作的其余部分隔离，因为编译器可以提供函数。
此方法将在整个 Q # 标准库中使用，以便以一种可随时在量程程序中使用的方式表示传统控制流。


## <a name="recursion"></a>递归

Q # callables 允许直接或间接递归。
也就是说，操作或函数可能调用自身，或者它可能调用直接或间接调用可调用操作的另一个可调用的。

不过，有两个关于递归使用的重要说明：

- 在操作中使用递归可能会干扰某些优化。
  这可能会对算法的执行时间产生重大影响。
- 在实际的量程设备上执行时，堆栈空间可能会受到限制，因此深度递归可能导致运行时错误。
  特别是，Q # 编译器和运行时不标识和优化尾递归。

## <a name="whats-next"></a>下一步是什么？
了解 Q # 中的[变量](xref:microsoft.quantum.guide.variables)。