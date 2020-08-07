---
title: 中的操作和函数Q#
description: 如何定义和调用操作和函数，以及受控和 adjoint 操作专用化。
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.operationsfunctions
no-loc:
- Q#
- $$v
ms.openlocfilehash: 76437c83df894fa86409e680f961d97e267c6869
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "87867873"
---
# <a name="operations-and-functions-in-no-locq"></a>中的操作和函数Q#

## <a name="defining-new-operations"></a>定义新操作

操作是的核心 Q# 。
声明后，可以从传统的 .NET 应用程序调用它们，例如，使用模拟器或内的其他操作 Q# 。
在中定义的每个操作 Q# 都可以调用任意数量的其他操作，包括由语言定义的内置内部操作。 Q#定义这些内部操作的特定方式取决于目标计算机。
在编译时，每个操作都表示为可提供给目标计算机的 .NET 类类型。

每个 Q# 源文件都可以定义任意数量的操作。
操作名称在命名空间中必须唯一，并且不能与类型或函数名冲突。

操作声明由关键字组成 `operation` ，后跟作为操作名称的符号、定义操作参数的类型化标识符元组、冒号 `:` 、描述操作结果类型的类型批注，还可以是包含操作特征的批注、左大括号和操作声明的正文（括在大括号中） `{ }` 。

每个操作都使用一个输入，生成一个输出，并为一个或多个专用操作指定实现。
本文的不同部分详细说明了可能的专用化，以及如何定义和调用它们。
现在，请考虑以下操作，该操作仅定义默认的主体特殊化并使用单个 qubit 作为其输入，然后对 <xref:microsoft.quantum.intrinsic.x> 该输入调用内置操作：

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

关键字 `operation` 开始操作定义，后跟名称; 此处为 `BitFlip` 。
接下来，定义输入类型 (`Qubit`) ，以及 `target` 用于引用新操作中的输入的名称。
最后， `Unit` 定义操作的输出为空。
`Unit``void`在 c # 和其他命令式语言中使用方式类似，并且等效于 `unit` F # 和其他功能语言。

操作还可以返回比更有趣 `Unit` 的类型。
例如， <xref:microsoft.quantum.intrinsic.m> 操作返回类型的输出，该输出 `Result` 表示已执行了一个度量值。  可以将其从操作传递到另一个操作，或将其与 `let` 关键字一起使用来定义新变量。

此方法允许表示在较低级别与量程操作交互的传统计算，如[superdense 编码](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding)：

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
> 中的每个操作 Q# 都只采用一个输入，并只返回一个输出。
> 多个输入和输出使用元组表示，这些*元组*将多个值一起收集到单个值中。
> 在这种情况下， Q# 是 "元组" 语言。
> 按照此概念，应将一组空括号 `()` 作为 "empty" 元组（类型为）进行读取 `Unit` 。

## <a name="controlled-and-adjoint-operations"></a>受控和 Adjoint 操作

如果操作实现了单一转换，就像在中执行许多操作一样 Q# ，然后可以定义操作在*adjointed*或*控制*时的行为方式。 操作的*adjoint*专用化指定操作的 "反转" 的行为方式，而*受控*专用化指定操作在其应用程序的应用程序在特定量程寄存器状态下运行时的行为方式。

量程操作的 Adjoints 对量程计算的许多方面都至关重要。 有关在一种有用的编程技术中讨论的这种情况的示例 Q# ，请参阅本文中的[语态](#conjugations)。 

操作的受控版本是新操作，仅当所有控件 qubits 都处于指定状态时，才会有效地应用基本操作。
如果控件 qubits 在 superposition 中，则会将基本操作一致应用到 superposition 的相应部分。
因此，受控操作通常用于生成牵连。

当然，还可以使用*受控的 adjoint*特殊化来指定操作 adjoint 的受控应用。

> [!NOTE]
> 如果 $U $ 是操作实现的单一转换 `U` ，则 `Adjoint U` 表示 $U ^ \dagger $ 的单一转换，这是复杂的共轭转置。
> 依次应用某一操作，然后将其 adjoint 的状态保持不变，如 $UU ^ \dagger = U ^ \dagger U = \id $，则为恒等矩阵。
> 受控操作的单一表示形式略微微妙，但可以在量程计算概念中找到更多详细信息[：多个 qubits](xref:microsoft.quantum.concepts.multiple-qubits)。

以下部分介绍如何在代码中调用这些不同的专用化 Q# ，以及如何定义操作来支持它们。

### <a name="calling-operation-specializations"></a>调用专用操作

中*functor*的函子 Q# 是一个工厂，它定义了其他操作的新操作。
中的两个标准函子 Q# 是 `Adjoint` 和 `Controlled` 。

在定义新操作的实现时，函子有权访问基操作的实现。
因此，函子可以比传统的高级函数执行更复杂的功能。 函子在类型系统中没有表示形式 Q# 。 因此，目前不可能将其绑定到变量或将其作为参数传递。 

通过将函子应用到操作来使用该操作，该操作将返回一个新操作。
例如，将函子应用 `Adjoint` 到操作会 `Y` 返回新操作 `Adjoint Y` 。 可以像调用任何其他操作一样调用新操作。
对于支持或函子应用程序的操作 `Adjoint` `Controlled` ，其返回类型必须为 `Unit` 。 

#### <a name="adjoint-functor"></a>`Adjoint`函子

因此， `Adjoint Y(q1)` 会将 `Adjoint` 函子应用到 `Y` 操作以生成新的操作，并将该新操作应用于 `q1` 。
新操作与基本操作具有相同的签名和类型 `Y` 。
具体而言，新操作还支持 `Adjoint` ，且 `Controlled` 仅当基本操作为时才支持。
`Adjoint`函子是其自身的反向; 即， `Adjoint Adjoint Op` 始终与相同 `Op` 。

#### <a name="controlled-functor"></a>`Controlled`函子

同样， `Controlled X(controls, target)` 将 `Controlled` 函子应用到 `X` 操作以生成新的操作，并将该新操作应用于 `controls` 和 `target` 。

> [!NOTE]
> 在中 Q# ，受控制的版本始终采用控件 qubits 数组，并且控制始终基于所有控件 qubits 处于计算 (`PauliZ`) `One` 状态 $ \ket {1} $。
> 基于其他状态的控制是通过在受控操作之前向控件 qubits 应用适当的单一操作来实现的，然后在受控操作之后应用单一操作的逆。
> 例如，将操作应用 `X` 于受控操作前后的控件 qubit 会导致操作控制该 `Zero` qubit 的状态 ($ \ket {0} $) ; `H` 在状态上和控件之前和之后应用操作 `PauliX` `One` ，即 Pauli X，$ \ket {-} \mathrel{： =} ( \ket {0} -\ket {1}) /\sqrt {2} $，而不是 `PauliZ` `One` 状态。

给定一个操作表达式，你可以使用函子来形成新的操作表达式 `Controlled` 。
新操作的签名基于原始操作的签名。
结果类型是相同的，但输入类型是一个具有 qubit 数组的双元组，该数组保存作为第一个元素的控件 qubit () s，作为第二个元素的初始操作的参数。
新操作支持 `Controlled` ，且 `Adjoint` 仅当原始操作执行时才支持。

如果原始操作只使用了一个参数，则会在此处播放[单独的元组等效](xref:microsoft.quantum.guide.types)性。
例如， `Controlled X` 是操作的受控版本 `X` 。 
`X`具有类型 `(Qubit => Unit is Adj + Ctl)` ，因此 `Controlled X` 具有类型 `((Qubit[], (Qubit)) => Unit is Adj + Ctl)` ; 由于单一元组等效，这与相同 `((Qubit[], Qubit) => Unit is Adj + Ctl)` 。

如果基本操作采用多个参数，请记住将操作的受控版本的相应参数括在括号中，以将其转换为元组。
例如， `Controlled Rz` 是操作的受控版本 `Rz` 。 
`Rz`具有类型 `((Double, Qubit) => Unit is Adj + Ctl)` ，因此 `Controlled Rz` 具有类型 `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)` 。
因此，将 `Controlled Rz(controls, (0.1, target))` 是 (的有效调用， `Controlled Rz` 请注意) 附近的括号 `0.1, target` 。

作为另一个示例， `CNOT(control, target)` 可以实现为 `Controlled X([control], target)` 。 如果目标应由两个 control qubits (CCNOT) 控制，请使用 `Controlled X([control1, control2], target)` 语句。

#### `Controlled Adjoint` 

`Controlled`和 `Adjoint` 函子的上下班，因此应用或之间没有区别 `Controlled Adjoint Op` `Adjoint Controlled Op` 。


## <a name="defining-controlled-and-adjoint-implementations"></a>定义受控和 Adjoint 实现

在前面的示例中的第一个操作声明中，操作 `BitFlip` 和 `DecodeSuperdense` 分别定义为签名 `(Qubit => Unit)` 和 `((Qubit, Qubit) => (Result, Result))` 。
`DecodeSuperdense`这并不是一个单一的操作，因此，它不是一种单一操作，因此，不能 adjoint 特殊化， (重新调用此类操作返回) 的相关要求 `Unit` 。
但是， `BitFlip` 只需执行单一 <xref:microsoft.quantum.intrinsic.x> 操作，即可将其定义为专用化。

本节详细介绍了如何在操作声明中包括特殊化的存在性 Q# ，从而使它们能够与 `Adjoint` 或函子一起调用 `Controlled` 。
若要详细了解它是有效的或无效的声明特定专用化的某些情况，请参阅本文中[的有效定义专用](#circumstances-for-validly-defining-specializations)化的情况。

操作特征定义可应用于声明的操作的函子类型，以及它们的影响。 这些专用化的存在可以声明为操作签名的一部分，具体而言，具有操作特征： `is Adj` 、 `is Ctl` 或 `is Adj + Ctl` 。
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
因此，你可以使用此 `DecodeSuperdense` 方法，通过使用 adjoint `PrepareEntangledPair` 将放大状态转换回 qubits 的 unentangled 对，来更简洁地地编写上一个示例中的。

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

声明中具有操作特征的批注非常有用，可确保编译器根据默认实现自动生成其他专用化。 

设计用于函子的操作时，需要考虑几个重要的限制。
大多数情况下，编译器*不能*自动生成使用任何其他操作的输出值的操作的专用化，因为在此类操作中，如何对语句重新排序以获得相同的效果。

因此，显式指定各种实现通常非常有用。

### <a name="explicitly-specifying-implementations"></a>显式指定实现

如果编译器无法生成实现，则可以显式指定它。 此类显式专用化声明可以包含合适的*生成指令*或用户定义的实现。
下面是各种可能性，其中有一些显式特殊化的示例。 


#### <a name="explicit-specialization-declarations"></a>显式专用化声明

Q#操作可以包含以下显式专用化声明：

- `body`专用化指定未应用函子的操作的实现。
- `adjoint`专用化指定应用了函子的操作的实现 `Adjoint` 。
- `controlled`专用化指定应用了函子的操作的实现 `Controlled` 。
- `controlled adjoint`专用化指定操作的实现，同时 `Adjoint` `Controlled` 应用和函子。
  此特殊化还可以命名 `adjoint controlled` ，因为这两个函子。


操作特殊化包含专业化标记 (例如， `body` 或 `adjoint`) 后跟以下其中之一：

- 如下所述的显式声明。
- 告诉编译器*如何*生成专用化的*指令*，可以是：
  - `intrinsic`，它指示目标计算机提供专用化。
  - `distribute`，与和专用化一起使用 `controlled` `controlled adjoint` 。
    当与一起使用时 `controlled` ，它指示编译器应通过将应用 `Controlled` 到中的所有操作来计算特殊化 `body` 。
    当与一起使用时 `controlled adjoint` ，它指示编译器应通过将应用 `Controlled` 到专用化中的所有操作来计算特殊化 `adjoint` 。
  - `invert`，它指示编译器应 `adjoint` 通过反序列化来计算特殊化 `body` ，例如，反转运算顺序并将 adjoint 应用于每个操作。
    当与一起使用时 `adjoint controlled` ，这指示编译器应通过反转专用化来计算特殊化 `controlled` 。
  - `self`，指示 adjoint 专用化与 `body` 专用化相同。
    `self`对于和专用化，使用是合法的 `adjoint` `adjoint controlled` 。
    对于 `adjoint controlled` ， `self` 表示 `adjoint controlled` 专用化与 `controlled` 特殊化相同。
  - `auto`，指示编译器应选择要应用的适当指令。
    不能将 `auto` 用于 `body` 专用化。

指令和 `auto` 都需要右分号 `;` 。
`auto`如果提供了的显式声明，则指令将解析为以下生成的指令 `body` ：

- `adjoint`根据指令生成专用化 `invert` 。
- `controlled`根据指令生成专用化 `distribute` 。
- `adjoint controlled` `invert` 如果为 `controlled` 指定了显式声明，而不是为指定了一个，则根据指令生成专用化 `adjoint` `distribute` 。

> [!TIP]   
> 如果操作是自我 adjoint 的，则通过生成指令显式指定 adjoint 或受控 adjoint 专用化，以便 `self` 编译器可以利用该信息进行优化。

包含用户定义的实现的专用化声明包含一个参数元组，后面跟有用于 Q# 实现专用化的代码的语句块。
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

在前面的 `PrepareEntangledPair` 示例中，代码等效于以下包含显式专用化声明的代码： 

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

如果编译器无法自动生成特定专用化的实现，或者如果可以提供更有效的实现，则可以手动定义实现。

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Ctl + Adj {
    body (...) { // default body specialization
        H(here);
        CNOT(here, there);
    }

    controlled (cs, ...) { // user-defined implementation for the controlled specialization
        Controlled H(cs, here);
        Controlled X(cs + [here], there);
    }

    adjoint invert; 
    controlled adjoint invert; 
}
```
在上面的示例中， `adjoint invert;` 指示 adjoint 专用化是通过反转正文实现生成的，并指示将 `controlled adjoint invert;` 通过反转受控专用化的给定实现生成受控 adjoint 特殊化。

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

指定不具有 adjoint 或受控版本的操作是合法的。 例如，由于度量值不可逆或可控制，因此它们不是可逆的。

如果操作的 `Adjoint` `Controlled` 声明包含各自专用化的隐式或显式声明，则操作支持和函子。

显式声明的 adjoint/受控专用化意味着存在 adjoint/受控专用化。 

对于正文包含重复执行循环、set 语句、度量、return 语句或对不支持函子的其他操作的操作 `Adjoint` ， `invert` 不能通过或指令自动生成 adjoint 专用化 `auto` 。

对于包含对不支持函子的其他操作的调用的操作 `Controlled` ， `distribute` 不能在或指令后自动生成受控专用化 `auto` 。

#### <a name="controlled-adjoint"></a>受控 Adjoint

操作的受控 adjoint 版本指定如何实现该操作的 adjoint 的量程控制版本。
指定不具有受控 adjoint 版本的操作是合法的;例如，度量操作没有受控的 adjoint 版本，因为它们既不能控制也不可逆。

当且仅当存在 adjoint 和受控专用化时，操作的受控 adjoint 专用化才需要存在。 在这种情况下，将推断出是否存在受控 adjoint 专用化。 如果未显式定义实现，编译将生成适当的专用化。

对于其正文包含对没有受控 adjoint 版本的其他操作的调用的操作， `invert` 无法在、 `distribute` 或指令后自动生成 adjoint 特殊化 `auto` 。


### <a name="type-compatibility"></a>类型兼容性

使用具有更少函子但签名相同的操作的其他函子支持的操作。 例如，使用类型为的操作的 `(Qubit => Unit is Adj)` 任何地方的类型运算 `(Qubit => Unit)` 。

Q#对于可调用的返回类型是*协变*的：返回类型的可调用与 `'A` 具有相同输入类型的可调用和与兼容的结果类型兼容 `'A` 。

Q#对于输入类型是*逆变*的：将类型作为输入的可调用与 `'A` 具有相同结果类型的可调用和兼容的输入类型兼容 `'A` 。

即，给定以下定义，

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

您可以

- `ConjugateInvertWith`使用或的参数调用函数 `inner` `Invert` `ApplyUnitary` 。
- `ConjugateUnitaryWith`使用的 `inner` 参数 `ApplyUnitary` （而不是）调用函数 `Invert` 。
- 从返回一个类型的 `(Qubit[] => Unit is Adj + Ctl)` 值 `ConjugateInvertWith` 。

> [!IMPORTANT]
> Q#0.3 引入了用户定义类型的行为的显著差异。

用户定义的类型被视为基础类型的包装版本，而不是作为子类型。
这意味着用户定义类型的值在预期基础类型的值为时不能使用。


### <a name="conjugations"></a>语态

与传统位相比，释放量程内存会稍微增加一点，因为在 qubits 仍放大时，盲目重置 qubits 可能会对剩余计算产生意外影响。 在释放内存之前，可以通过适当的方式 "撤消" 已执行的计算来避免这些效果。 量程计算的常见模式如下： 

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

从0.9 版本开始， Q# 支持实现前面转换的语态语句。 使用该语句，可以通过 `ApplyWith` 以下方式实现操作：

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
如果外部和内部转换不能像操作那样轻松地提供，则这种语态语句就变得更加有用，但通过多个语句组成的块可以更方便地进行描述。 

在内块中定义的语句的反转换是由编译器自动生成的，并在应用块完成后运行。
由于不能在 apply 块中重新绑定用作内部块的一部分的任何可变变量，因此，生成的转换将保证为内块中计算的 adjoint。 


## <a name="defining-new-functions"></a>定义新函数

函数在中是纯粹确定性的传统例程 Q# ，不同于操作，因为它们不允许在计算输出值之前有任何影响。
特别是，函数不能调用操作;操作、分配或借用 qubits;示例随机数;否则，依赖于输入值超出函数的状态。
因此， Q# 函数是*纯*的，因为它们始终将相同的输入值映射到相同的输出值。
此行为允许 Q# 编译器在生成操作专用化时，对调用函数的方式和时间进行安全重新排序。

每个 Q# 源文件都可以定义任意数量的函数。
函数名称在命名空间中必须是唯一的，且不能与操作或类型名称冲突。

定义函数的工作方式与定义操作类似，但不能为函数定义 adjoint 或受控专用化。
例如：

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```

or 

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

只要有可能，就可以根据函数（而不是操作）编写传统逻辑，使操作能够更轻松地使用它。 例如，如果您已编写了前面的 `Square` 声明作为*运算*，则编译器不能保证使用相同的输入调用它会一致地生成相同的输出。

为了下划线函数和操作之间的差异，请考虑经典在操作中采样随机数字的问题 Q# ：

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

每次 `U` 调用时，它将对执行不同的操作 `target` 。
特别是，如果您将一个专用化声明添加到，则该编译器无法保证，它作为 `adjoint auto` `U` 一种 `U(target); Adjoint U(target);` 无操作)  (。
这违反了在[向量和矩阵](xref:microsoft.quantum.concepts.vectors)中定义的 adjoint 的定义，使编译器能够在调用操作的操作中自动生成 adjoint 特殊化，这 <xref:microsoft.quantum.math.randomreal> 会破坏编译器提供的保证; <xref:microsoft.quantum.math.randomreal> 是不存在 adjoint 或受控版本的操作。

另一方面，允许函数调用（如） `Square` 是安全的，并确保编译器仅需保留输入以 `Square` 保持其输出稳定。
因此，将尽可能多的传统逻辑隔离到函数中，可以轻松地在其他函数和操作中重复使用该逻辑。


## <a name="generic-type-parameterized-callables"></a>泛型 (类型参数化) Callables

您可能想要定义的许多函数和操作实际上不依赖于其输入的类型，而只是通过其他函数或操作隐式使用其类型。
例如，请考虑许多功能语言共有的*地图*概念;给定函数 $f (x) $ 和值的集合 $ \{ x_1，x_2，\dots ..，x_n \} $，map 将返回一个新的集合 $ f (x_1)  (x_2)  (\{ \} $。
若要在中实现此 Q# 功能，请利用函数是第一类这一事实。
下面是的一个快速示例 `Map` ，使用 `T` 作为占位符，同时找出所需的类型。

```qsharp
function Map(fn : (T -> T), values : T[]) : T[] {
    mutable mappedValues = new T[Length(values)];
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

原则上，你可以 `Map` 为你遇到的每对类型编写一个版本，但这会带来一些困难。
例如，如果在中发现 bug，则 `Map` 必须确保在的所有版本中统一应用此修补程序 `Map` 。
此外，如果您构造新的元组或 UDT，则您现在必须构造一个新的 `Map` 来与新类型一起工作。
虽然这对于少量此类函数是易的，但当你收集与相同窗体的更多函数时， `Map` 引入新类型的成本将以相当短的顺序变为太。

但是，这种情况很难产生这种情况，因为您没有为编译器提供所需的信息来识别的不同版本 `Map` 是如何相关的。
实际上，你希望编译器将 `Map` 类型中的某种数学函数视为 Q# *types* Q# 函数。

Q#通过允许函数和操作具有*类型参数*，以及其普通元组参数，实现了这一概念的形式。
在前面的示例中，您希望在 `Map` 第一种情况下将类型形参视为 `Int, Pauli` ， `Double, String` 在第二种情况下。
大多数情况下，使用这些类型参数，如同它们是普通类型。 使用类型参数的值来生成数组和元组，调用函数和操作，并将其分配给普通或可变变量。

> [!NOTE]
> 间接依赖关系的最极端情况是 qubits，其中 Q# 程序不能直接依赖类型的结构， `Qubit` 而是**必须**将此类类型传递给其他操作和函数。

返回到前面的示例，然后您将看到 `Map` 需要具有类型参数，一个用于表示输入，另一个用于 `fn` 表示的输出 `fn` 。
在中 Q# ，通过在 `<>` 其声明中的函数或操作的名称后面添加尖括号 (（而不是 brakets $ \braket {} $！ ) ），并列出每个类型参数来编写这种情况。
每个类型形参的名称必须以计时周期开始 `'` ，这表示它是一个类型形参，而不是一个普通类型 (也称为) 的*具体*类型。
因此， `Map` 将编写：

```qsharp
function Map<'Input, 'Output>(fn : ('Input -> 'Output), values : 'Input[]) : 'Output[] {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

请注意，的定义 `Map<'Input, 'Output>` 看起来非常类似于 previoius 版本。
唯一的不同之处在于，你已明确通知编译器 `Map` 不直接依赖哪些内容 `'Input` `'Output` ，但通过间接通过使用这两种类型来实现这一功能 `fn` 。
`Map<'Input, 'Output>`通过这种方式定义后，可以像调用普通函数一样调用它：

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> 编写泛型函数和操作是一个位置，其中 "元组 out" 是一种非常有用的方法，用于考虑 Q# 函数和操作。
> 由于每个函数只采用一个输入并返回一个输出，因此类型的输入 `'T -> 'U` 与*任何* Q# 函数都匹配。
> 同样，可以将任何操作传递到类型为的输入 `'T => 'U` 。

作为第二个示例，请考虑编写一个函数，该函数返回两个其他函数的组合：

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

在此，您必须指定确切的 `A` 、 `B` 和， `C` 从而严格限制新函数的实用工具 `Compose` 。
毕竟， `Compose` 只依赖于 `A` 、和， `B` 并 `C` *通过* `innerFn` 和 `outerFn` 。
作为替代方法，可以将类型参数添加到 `Compose` ，这表示它适用于*任何* `A` 、 `B` 和 `C` ，前提是这些参数与和所需的参数匹配 `innerFn` `outerFn` ：

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

Q#标准库提供了一系列这样的类型参数化操作和函数，使更高顺序控制流更易于表达。
[ Q# 标准库指南](xref:microsoft.quantum.libraries.standard.intro)中进一步讨论了这些情况。


## <a name="callables-as-first-class-values"></a>Callables 作为第一类值

使用函数（而不是操作）对控制流和传统逻辑的推理的一项重要技巧是，使用中的操作和函数是 Q# *第一类*。
也就是说，它们本身就是语言中的每个值。
例如，下面是一个非常有效的 Q# 代码，如果是间接的：

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

`ourH`上一个代码段中的变量的值就是操作 <xref:microsoft.quantum.intrinsic.h> ，因此可以像任何其他操作一样调用该值。
利用此功能，您可以编写将操作作为其输入的一部分执行的操作，形成更高顺序的控制流概念。
例如，你可能想要通过将其应用到同一个目标 qubit 来 "正方形" 的操作。

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

### <a name="returning-operations-from-a-function"></a>从函数返回操作

必须强调的是，您还可以在输出过程中返回操作，以便可以将某些类型的传统条件逻辑隔离为传统函数，这将以操作的形式返回量程程序的说明。
作为一个简单的示例，请考虑 teleportation 示例，在该示例中，接收两位传统消息的参与方需要使用该消息将其 qubit 解码为正确的 teleported 状态。
您可以编写一个函数，该函数采用这两个传统位并返回正确的解码操作。

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

此新函数确实是一个函数，在这种情况下，如果使用和的相同值调用该函数 `hereBit` `thereBit` ，则总是返回相同的操作。
这样，解码器就可以安全地在操作内运行，而无需考虑解码逻辑如何与不同操作专用化的定义进行交互。
也就是说，函数内的传统逻辑是独立的，从而保证编译器函数调用可以与 impunity 重新排序，只要输入已保留。


## <a name="partial-application"></a>部分应用程序

通过使用*部分应用程序*返回操作的函数，你可以更多地执行此操作，在该应用程序中，你可以向函数或操作提供一个或多个输入部分，而无需实际调用它。 在前面的 `ApplyTwice` 示例中，您可以指示您不希望立即指定输入操作应应用到的 qubit：

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

在这种情况下，局部变量 `twiceOp` 包含部分应用的操作 `ApplyTwice(op, _)` ，其中 `_` 指示输入中尚未指定的部分。
`twiceOp`在下一行中调用时，会将输入的所有剩余部分作为初始操作的所有剩余部分传递给部分应用的操作。
因此，前面的代码段与直接调用相同 `ApplyTwice(op, target)` ，因为您引入了一个新的局部变量，因此您可以延迟调用，同时提供输入的某些部分。

由于未实际调用已部分应用的操作，在提供其整个输入之前，可以安全地部分应用操作，即使是在函数内。

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

原则上，中的传统逻辑 `SquareOperation` 可能会更多地涉及到，但它仍与操作的其余部分隔离，因为编译器可以提供函数。 Q#标准库在整个过程中都使用这种方法，以一种可让量子程序随时使用的方式表示传统的控制流。


## <a name="recursion"></a>递归

Q#允许直接或间接递归 callables。
也就是说，操作或函数可以调用自身，也可以调用可直接或间接调用可调用操作的另一个可调用的。

不过，有两个关于递归使用的重要说明：

- 在操作中使用递归可能会干扰某些优化。
  此干扰可能会对算法的执行时间产生重大影响。
- 在实际的量程设备上运行时，堆栈空间可能会受到限制，因此深度递归可能导致运行时错误。
  具体而言， Q# 编译器和运行时不会标识和优化尾递归。

## <a name="next-steps"></a>后续步骤

了解中[Variables](xref:microsoft.quantum.guide.variables)的变量 Q# 。