---
title: 'Q # 文件结构'
description: '了解如何在 Q # 程序和库中构造命名空间、操作、函数和用户定义类型声明。'
author: QuantumWriter
uid: microsoft.quantum.language.file-structure
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: b4bb7d4d70677dbd5d921a9f68313760499a56a1
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2020
ms.locfileid: "77907386"
---
# <a name="file-structure"></a>文件结构

Q # 文件由一系列命名空间声明组成。
每个命名空间声明都包含用户定义的类型、操作和函数的声明。
命名空间声明可以包含任何类型的声明，并按任意顺序包含。
可在命名空间声明之外显示的唯一文本为注释。
特别是，命名空间的文档注释位于声明之前。

## <a name="namespace-declarations"></a>命名空间声明

Q # 文件通常只包含一个命名空间声明，但可能不包含（且为空或只包含注释）或可能包含多个命名空间。
命名空间声明不能嵌套。

同一个命名空间可以在编译在一起的多个 Q # 文件中声明，只要不存在具有相同名称的类型、操作或函数声明。
具体而言，在多个文件的同一命名空间中定义同一类型是无效的，即使这些声明相同也是如此。

命名空间声明包含关键字 `namespace`，后跟命名空间的名称，左大括号 `{`，命名空间中包含的声明，`}`右大括号。
命名空间名称遵循由一个或多个合法符号序列组成的 .NET 模式，`.`用句点分隔。
例如，`MyQuantumStuff` 和 `Microsoft.Quantum.Canon` 是有效的命名空间名称。
按照约定，命名空间名称中的符号采用大写形式，但这不是必需的。

声明可以在命名空间声明中以任意顺序出现。
已正确解析对文件中的向下声明的类型或 callables 的引用。在引用之前，不需要类型、操作或函数声明。

## <a name="open-directives"></a>打开指令

在命名空间块中，可以使用 `open` 指令导入在某个命名空间中定义的所有类型和 callables，并按其非限定名称引用它们。 

此类 `open` 指令包含 `open` 关键字，后跟要打开的命名空间和终止分号。

例如，

```qsharp
open Microsoft.Quantum.Canon;
```

（可选）可定义已打开命名空间的短名称，使来自该命名空间的所有元素都可以（并且需要）由定义的短名称限定。 这种短名称是通过在 `open` 指令中的分号前添加关键字 `as` 后跟所需的短名称来定义的：

```qsharp
open Microsoft.Quantum.Math as Math;
```

所有 `open` 指令必须出现在命名空间块中的任何 `function`、`operation`或 `newtype` 声明之前。
`open` 指令适用于文件中的整个命名空间块。

## <a name="user-defined-type-declarations"></a>用户定义的类型声明

Q # 为用户提供了一种声明新的用户定义类型的方法，如 " [Q # 类型模型](xref:microsoft.quantum.language.type-model)" 部分所述。
即使基类型是相同的，用户定义的类型还是不同的。
具体而言，两个用户定义类型的值之间不会自动转换，即使基础类型相同也是如此。

用户定义的类型声明包含关键字 `newtype`，后跟用户定义类型的名称、`=`、有效类型规范和终止分号。

例如：

```qsharp
newtype PairOfInts = (Int, Int);
```

每个 Q # 源文件可以声明任意数量的用户定义类型。
类型名称在命名空间中必须是唯一的，且不能与操作和函数名称冲突。

不能定义用户定义类型之间的循环依赖关系。 这样就不能在 Q # 内实现递归类型。

## <a name="operation-declarations"></a>操作声明

操作是 Q # 的核心，大致类似于其他语言中的函数。
每个 Q # 源文件可以定义任意数量的操作。

操作名称在命名空间中必须是唯一的，并且可能不会与类型和函数名称冲突。

操作声明包含关键字 `operation`，后跟作为操作名称的符号、定义操作的参数的类型化标识符元组、冒号 `:`、描述操作结果类型的类型批注、可以选择具有操作特征的批注、左大括号 `{`、操作声明的正文和最终右大括号 `}`。

操作声明的主体既包含默认实现，也包含专用化列表。
如果只需显式指定默认的正文专用化的实现，则可以在声明中直接指定默认实现。
在这种情况下，声明中具有操作特征的批注非常有用，可确保编译器根据默认实现自动生成其他专用化。 

例如 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```

操作特征定义哪些类型的函子可以应用于声明的操作以及它们有什么影响。 如果操作实现了单一转换，则可以定义操作在*adjointed*或*控制*时的行为方式。
这些专用化的存在可以声明为操作签名的一部分。 然后，编译器将生成每个此类隐式声明的专用化的相应实现。 在上面的示例中，编译器将生成一个 adjoint、一个控制的和一个控制的 adjoint 专用化。 

如果编译器无法生成实现，则可以显式指定实现。 此类显式专用化声明可以包含一个合适的生成指令，该指令阐明如何生成特定专用化或用户定义的实现。 例如，上面 `PrepareEntangledPair` 中的代码等效于以下代码，其中包含显式专用化声明： 

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
如果编译器无法为特定专用化生成实现（如更精确的生成指令），或者如果可以提供更有效的实现，则也可以手动定义该实现。

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

对于支持 `Adjoint` 和/或 `Controlled` 函子应用程序的操作，必须 `Unit`其返回类型。 


### <a name="explicit-specialization-declarations"></a>显式专用化声明

Q # 操作可能包含以下显式专用化声明：

- `body` 特殊化指定了在未应用函子的情况中实现操作。
- `adjoint` 特殊化指定应用了 `Adjoint` 函子的操作的实现。
- `controlled` 特殊化指定应用了 `Controlled` 函子的操作的实现。
- `controlled adjoint` 专用化通过应用的 `Adjoint` 和 `Controlled` 指定操作的实现。
  这种特殊化还可以命名为 `adjoint controlled`，因为这两个函子。


操作特殊化包含专业化标记（如 `body`、`adjoint`等），后跟以下其中之一：

- 如下所述的显式声明。
- 告诉编译器如何生成专用化的指令，可以是：
  - `intrinsic`，指示目标计算机提供专用化。
  - `distribute`，可与 `controlled` 和 `controlled adjoint` 专用化一起使用。
    与 `controlled`一起使用时，它指示编译器应通过将 `Controlled` 应用到 `body`中的所有操作来计算特殊化。
    与 `controlled adjoint`一起使用时，它指示编译器应通过将 `Controlled` 应用到 `adjoint` 专用化中的所有操作来计算特殊化。
  - `invert`，它指示编译器应通过反序列化 `body`来计算 `adjoint` 特殊化，即反向运算的顺序并将 adjoint 应用于每个操作。
    与 `adjoint controlled`一起使用时，它指示编译器应通过反转 `controlled` 专用化来计算特殊化。
  - `self`，指示 adjoint 特殊化与 `body` 特殊化相同。
    这对于 `adjoint` 和 `adjoint controlled` 专用化是合法的。
    对于 `adjoint controlled`，`self` 意味着 `adjoint controlled` 专用化与 `controlled` 特殊化相同。
  - `auto`，指示编译器应选择要应用的适当指令。
    `auto` 不能用于 `body` 专用化。

指令和 `auto` 都需要右半冒号 `;`。
如果提供了 `body` 的显式声明，则 `auto` 指令可解析为以下生成指令：

- `adjoint` 专用化是根据指令 `invert`生成的。
- `controlled` 专用化是根据指令 `distribute`生成的。
- `adjoint controlled` 专用化是根据指令生成的 `invert` 如果为 `controlled` 提供了显式声明，但没有为 `adjoint`提供一个，则为，否则为 `distribute`。

> [!TIP]   
> 如果操作是自我 adjoint 的，则通过 `self` 生成指令显式指定 adjoint 或受控 adjoint 特殊化，以允许编译器使用该信息进行优化。

包含用户定义的实现的专用化声明包含一个参数元组，后面跟有用于实现专用化的 Q # 代码的语句块。
在参数列表中，`...` 用于表示作为一个整体为操作声明的参数。
对于 `body` 和 `adjoint`，应始终 `(...)`参数列表;对于 `controlled` 和 `adjoint controlled`，参数列表应为表示控件 qubits 数组的符号，后跟 `...`，并用括号括起来。例如，`(controls,...)`。

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

### <a name="adjoint"></a>Adjoint

操作的 adjoint 指定如何实现该操作的复杂共轭转置，即 "反向运行" 操作的操作方式。
指定一个不带 adjoint 的操作是合法的;例如，测量操作没有 adjoint，因为它们不可逆。
如果操作的声明包含 adjoint 专用化的隐式或显式声明，则该操作支持 `Adjoint` 的函子。
显式声明的受控 adjoint 专用化意味着存在 adjoint 专用化。 

对于其正文包含重复截止时间循环、set 语句、度量、return 语句或对不支持 `Adjoint` 函子的其他操作的操作，如果不可能，请遵循 `invert` 或 `auto` 指令自动生成 adjoint 特殊化。

### <a name="controlled"></a>操控

操作的受控版本指定如何实现该操作的量程控制版本，即，在应用于量程寄存器状态时操作的行为方式。
[受控](xref:microsoft.quantum.language.type-model#controlled)部分提供了更完整的说明。

指定没有受控版本的操作是合法的;例如，由于不能控制度量操作，因此它没有受控版本。
当且仅当其声明包含受控专用化的隐式或显式声明时，操作才支持 `Controlled` 的函子。
显式声明的受控 adjoint 专用化意味着存在受控的专用化。 

对于其正文包含对不支持 `Controlled` 函子的其他操作的调用的操作，无法在 `distribute` 或 `auto` 指令后自动生成受控专用化。

### <a name="controlled-adjoint"></a>受控 Adjoint

操作的受控 adjoint 版本指定如何实现该操作的 adjoint 的量程控制版本。
指定不具有受控 adjoint 版本的操作是合法的;例如，度量操作没有受控的 adjoint 版本，因为它们既不能控制也不可逆。

当且仅当存在 adjoint 和受控专用化时，操作的受控 adjoint 专用化才需要存在。 在这种情况下，如果未显式定义实现，则会推断出受控 adjoint 专用化的存在，并由编译器生成合适的专用化。 

对于其正文包含对没有受控 adjoint 版本的其他操作的调用的操作，无法在 `invert`后自动生成 adjoint 特殊化，`distribute` 或 `auto` 指令。


### <a name="examples"></a>示例

操作声明可能非常简单，如下所示：定义基元 Pauli X 操作：

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```

下面定义了传送操作。

```qsharp
// Entangle two qubits.
// Assumes that both qubits are in the |0> state.
operation EPR (q1 : Qubit, q2 : Qubit) : Unit 
is Adj + Ctl {
    H(q2);
    CNOT(q2, q1);
}

// Teleport the quantum state of the source to the target.
// Assumes that the target is in the |0> state.
operation Teleport (source : Qubit, target : Qubit) : Unit {

    // Get a temporary for the Bell pair
    using (ancilla = Qubit())
    {
        // Create a Bell pair between the temporary and the target
        EPR(target, ancilla);

        // Do the teleportation
        Adjoint EPR (ancilla, source);

        if (MResetZ(source) == One) {
            X(target);
        }
        if (MResetZ(ancilla) == One) {
            Z(target);
        }
    }
}
```

## <a name="function-declarations"></a>函数声明

函数是 Q # 中纯传统例程。
每个 Q # 源文件可以定义任意数量的函数。

函数声明包含关键字 `function`，后跟作为函数名称的符号、类型化标识符元组、描述函数的返回类型的类型批注以及描述函数实现的语句块。

定义函数的语句块必须与任何其他语句块 `{` 和 `}` 括起来。

函数名称在命名空间中必须是唯一的，且不能与操作和类型名称冲突。
函数不能分配或借用 qubits 或调用操作。 操作的部分应用或按操作类型化值的方法很好。

例如，

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
