---
title: Q#文件结构
description: 描述文件的结构和语法 Q# 。
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.filestructure
no-loc:
- Q#
- $$v
ms.openlocfilehash: ac73962b1a718cd04aa87ee3476c66781fe3ac2b
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "87867924"
---
# <a name="no-locq-file-structure"></a>Q#文件结构

Q#文件由*命名空间声明*序列组成。
每个命名空间声明都包含用户定义的类型、操作和函数的声明，可以按任意顺序包含每种类型的声明的任意数目。
有关命名空间中的声明的详细信息，请参阅[用户定义的类型](xref:microsoft.quantum.guide.types#user-defined-types)、[操作](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations)和[函数](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions)。

可在命名空间声明之外显示的唯一文本为注释。
特别是，命名空间的文档注释位于声明之前。 有关详细信息，请参阅本文中的[文档注释](#documentation-comments)。 

## <a name="namespace-declarations"></a>命名空间声明

Q#文件通常只包含一个命名空间声明，但可能没有 (并且为空，或者只包含注释) 或可能包含多个命名空间。
命名空间声明不能嵌套。

可以在编译的多个文件中声明相同的命名空间 Q# ，只要不存在具有相同名称的类型、操作或函数声明。
具体而言，在多个文件的同一命名空间中定义同一类型是无效的，即使这些声明相同也是如此。

命名空间声明包含关键字 `namespace` ，后跟命名空间的名称，以及包含在括在大括号中的命名空间中的声明 `{ }` 。
命名空间名称遵循由句点分隔的一个或多个合法符号序列的 .NET 模式 `.` 。
例如， `MyQuantumStuff` 和 `Microsoft.Quantum.Intrinsic` 是有效的命名空间名称。
按照约定，将命名空间名称中的符号大写，不过，这并不是必需的。

对在文件中进一步声明的类型或 callables 的引用可以正确解析。在引用之前，不需要类型、操作或函数声明。

## <a name="open-directives"></a>打开指令

在命名空间块中，使用 `open` 指令导入在某个命名空间中声明的所有类型和 callables，并按它们的非限定名称引用它们。
此类 `open` 指令由关键字组成 `open` ，后跟要打开的命名空间和终止分号。

> [!NOTE] 
> 所有 `open` 指令必须出现在 `function` `operation` `newtype` 命名空间块中的任何、或声明之前。

（可选）可以为打开的命名空间定义短名称。 如果定义了短名称，则必须通过定义的短名称来限定该命名空间中的所有元素。 例如，给定以下命名空间声明和打开指令，

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace

    // operation, function, and newtype declarations

}
```

如果声明的操作使用中的 `Op` 操作 `Microsoft.Quantum.Intrinsic` ，则只需使用即可调用该操作 `Op` 。
但是，若要从调用某个 `Fn` 函数 `Microsoft.Quantum.Math` ，必须使用调用它 `Math.Fn` 。

`open`指令适用于文件中的整个命名空间块。
因此，如果在与前面相同的文件中定义了其他命名空间 Q# `NS` ，则在第二个命名空间中定义的任何操作/函数/类型都将无法从或中访问任何内容， `Microsoft.Quantum.Intrinsic` `Microsoft.Quantum.Math` 除非你在其中重复了 open 指令。 

若要引用*未*在当前命名空间中打开的另一个命名空间中定义的类型或可调用，必须按其完全限定名称引用它。
例如，给定 `Op` 命名空间中名为的操作 `X.Y` ：

* 必须按其完全限定名称引用它 `X.Y.Op` ，除非 `X.Y` 之前在当前块中打开了该命名空间。 
* 即使 `X` 命名空间已打开，也不能将该操作作为引用 `Y.Op` 。
* 如果 `Z` `X.Y` 在该命名空间和文件中定义了的短名称，则必须将引用 `Op` 为 `Z.Op` 。 

通常最好通过使用指令来包含命名空间 `open` 。
如果两个命名空间定义具有相同名称的构造，并且当前源使用两者中的构造，则需要使用完全限定的名称。

Q#遵循与其他 .NET 语言相同的命名规则。
但是，不 Q# 支持对命名空间的相对引用。
例如，如果命名空间 `a.b` 为打开状态，则对名为的操作的引用不 `c.d` 会解析为具有完整名称的操作*not* `a.b.c.d` 。

## <a name="formatting"></a>格式化

大多数 Q# 语句和指令以终止分号结束 `;` 。
语句和声明（如 `for` ） `operation` 以语句块结尾 (参阅以下部分) 不需要终止分号。
每个语句说明都说明终止分号是否是必需的。

语句（如表达式、声明和指令）可以跨多行进行划分。
避免在单个行上放置多个语句。

## <a name="statement-blocks"></a>语句块

Q#语句分为语句块，它们包含在大括号中 `{ }` 。 语句块以开头开始，以 `{` 结束 `}` 。

在词法上包含在另一个块内的语句块被视为包含块的子块;包含和子块也称为外部和内部块。

## <a name="comments"></a>注释

注释以两个正斜杠开头， `//` 并继续到行的末尾。
注释可以出现在源文件中的任何位置 Q# 。

## <a name="documentation-comments"></a>文档注释

`///`当编译器在命名空间、操作、专用化、函数或类型定义紧靠前出现时，编译器会对以三个正斜杠开头的注释进行专门处理。
在这种情况下，编译器会将它们视为已定义的可调用或用户定义类型的文档，这与其他 .NET 语言相同。

在 `///` 注释中，作为 API 文档一部分显示的文本将设置为[Markdown](https://daringfireball.net/projects/markdown/syntax)，并使用特殊命名标头指示的文档的不同部分。
在 Markdown 中，在 `@"<ref target>"` 中使用扩展来交叉引用操作、函数和用户定义的类型 Q# 。 替换 `<ref target>` 为所引用代码对象的完全限定名称。
不同的文档引擎还可能支持其他 Markdown 扩展。

例如：

```qsharp
/// # Summary
/// Given an operation and a target for that operation,
/// applies the given operation twice.
///
/// # Input
/// ## op
/// The operation to be applied.
/// ## target
/// The target to which the operation is to be applied.
///
/// # Type Parameters
/// ## 'T
/// The type expected by the given operation as its input.
///
/// # Example
/// ```Q#
/// // Should be equivalent to the identity.
/// ApplyTwice(H, qubit);
/// ```
///
/// # See Also
/// - Microsoft.Quantum.Intrinsic.H
operation ApplyTwice<'T>(op : ('T => Unit), target : 'T) : Unit {
    op(target);
    op(target);
}
```

以下名称是有效的文档注释标头。

- **摘要**：函数或操作行为的简短摘要，或类型的用途。 摘要的第一个段落用于悬停信息。 它应为纯文本。
- **说明**：函数或操作的行为或类型用途的说明。 摘要和说明共同构成了函数、操作或类型所生成的文档文件。
  说明支持行内 LaTeX 格式的符号和公式。
- **输入**：对操作或函数的输入元组的说明。
  可以包含其他 Markdown 子节，指示输入元组的每个元素。
- **输出**：操作或函数返回的元组的说明。
- **类型参数**：一个空节，其中每个泛型类型参数包含一个附加子节。
- **示例**：操作、函数或所使用的类型的简短示例。
- **备注**：其他 prose，描述操作、函数或类型的某个方面。
- **另请参阅**：表示相关函数、操作或用户定义类型的完全限定名称的列表。
- **引用**：记录的项的引用和引文列表。

## <a name="next-steps"></a>后续步骤

了解中的[操作和函数](xref:microsoft.quantum.guide.operationsfunctions) Q# 。