---
title: 'Q # 文件结构'
description: '介绍 Q # 文件的结构和语法。'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.filestructure
ms.openlocfilehash: b8c24dae6cc8d8f37ad4f1f74017c05cabe3a4b4
ms.sourcegitcommit: a35498492044be4018b4d1b3b611d70a20e77ecc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/03/2020
ms.locfileid: "84327452"
---
# <a name="q-file-structure"></a>Q # 文件结构

每个 Q # 操作、函数和用户定义的类型都是在命名空间中定义的。

Q # 文件由一系列*命名空间声明*组成。
每个命名空间声明都包含用户定义的类型、操作和函数的声明。
命名空间声明可以包含任何类型的声明，并按任意顺序包含。
若要详细了解如何在命名空间中声明[用户定义的类型](xref:microsoft.quantum.guide.types#user-defined-types)、[操作](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations)和[函数](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions)，请单击以下链接。

可在命名空间声明之外显示的唯一文本为注释。
具体而言，命名空间的文档注释（更多详细信息）位于声明之前。

## <a name="namespace-declarations"></a>命名空间声明

Q # 文件通常只包含一个命名空间声明，但可能不包含（且为空或只包含注释）或可能包含多个命名空间。
命名空间声明不能嵌套。

同一个命名空间可以在编译在一起的多个 Q # 文件中声明，只要不存在具有相同名称的类型、操作或函数声明。
具体而言，在多个文件的同一命名空间中定义同一类型是无效的，即使这些声明相同也是如此。

命名空间声明包含关键字 `namespace` ，后跟命名空间的名称、左大括号 `{` 、命名空间中包含的声明和右大括号 `}` 。
命名空间名称遵循由句点分隔的一个或多个合法符号序列的 .NET 模式 `.` 。
例如， `MyQuantumStuff` 和 `Microsoft.Quantum.Intrinsic` 是有效的命名空间名称。
按照约定，命名空间名称中的符号采用大写形式，但这不是必需的。

已正确解析对文件中的向下声明的类型或 callables 的引用。在引用之前，不需要类型、操作或函数声明。

## <a name="open-directives"></a>打开指令

在命名空间块中， `open` 指令可用于导入在某个命名空间中声明的所有类型和 callables，并按其非限定名称引用它们。
此类 `open` 指令由关键字组成 `open` ，后跟要打开的命名空间和终止分号。

> [!NOTE] 
> 所有 `open` 指令必须出现在 `function` `operation` `newtype` 命名空间块中的任何、或声明之前。

（可选）可定义已打开命名空间的短名称，使来自该命名空间的所有元素都可以（并且需要）由定义的短名称限定。 例如，给定以下命名空间声明和打开指令，

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace

    // operation, function, and newtype declarations

}
```

如果声明的操作使用来自的操作 `Op` `Microsoft.Quantum.Intrinsic` ，只需使用即可调用该操作 `Op` 。
但是，如果我们想要从调用某个函数 `Fn` `Microsoft.Quantum.Math` ，则需要使用调用它 `Math.Fn` 。

`open`指令适用于文件中的整个命名空间块。
因此，如果我们要在与上述相同的 Q # 文件中定义其他命名空间 `NS` ，则在第二个命名空间中定义的任何操作/函数/类型都不能从或中的任何内容访问， `Microsoft.Quantum.Intrinsic` `Microsoft.Quantum.Math` 除非我们重复了本文中的 open 指令。 

在当前命名空间中*未*打开的其他命名空间中定义的类型或可调用必须由其完全限定名称引用。
例如，命名空间中名为的操作 `Op` `X.Y` 必须由其完全限定名称引用 `X.Y.Op` ，除非 `X.Y` 之前在当前块中打开了该命名空间。 如上所述，即使 `X` 已打开命名空间，也不能将该操作作为引用 `Y.Op` 。
如果已 `Z` `X.Y` 在该命名空间和文件中定义了的短名称，则 `Op` 需要将其称为 `Z.Op` 。 

通常最好通过使用指令来包含命名空间 `open` 。
如果两个命名空间定义具有相同名称的构造，并且当前源使用两者中的构造，则需要使用完全限定的名称。

Q # 遵循的规则与其他 .NET 语言相同。
但是，Q # 不支持对命名空间进行相对引用。
也就是说，如果 `a.b` 已打开命名空间，则不会将对名为的操作的引用 `c.d` 解析为具有完整名称的*not*操作 `a.b.c.d` 。

## <a name="formatting"></a>格式化

大多数 Q # 语句和指令以终止分号结束 `;` 。
语句和声明（例如 `for` 和 `operation` ）以语句块结尾（见下文），不需要终止分号。
每个语句说明都说明终止分号是否是必需的。

语句（如表达式、声明和指令）可以跨多行进行划分。
应避免在单个行上包含多个语句。

## <a name="statement-blocks"></a>语句块

Q # 语句分组为语句块。
语句块以开头开始，以 `{` 结束 `}` 。

在词法上包含在另一个块内的语句块被视为包含块的子块;包含和子块也称为外部和内部块。

## <a name="comments"></a>注释

注释以两个正斜杠开头， `//` 并继续到行尾。
注释可以出现在 Q # 源文件中的任何位置。

## <a name="documentation-comments"></a>文档注释

`///`当编译器在命名空间、操作、专用化、函数或类型定义紧靠前出现时，编译器会对以三个正斜杠开头的注释进行专门处理。
在这种情况下，它们的内容将作为定义的可调用或用户定义类型的文档，如其他 .NET 语言所示。

在 `///` 注释中，作为 API 文档一部分显示的文本的格式为[Markdown](https://daringfireball.net/projects/markdown/syntax)，特别命名的标头表明文档的不同部分。
作为 Markdown 的扩展，可以使用来包含 Q # 中对操作、函数和用户定义类型的交叉引用， `@"<ref target>"` 其中， `<ref target>` 替换为所引用的代码对象的完全限定名称。
文档引擎也可以选择支持其他 Markdown 扩展。

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

以下名称被识别为文档注释标头。

- **摘要**：函数或操作行为或类型用途的简短摘要。 摘要的第一个段落用于悬停信息。 它应为纯文本。
- **说明**：对函数或操作的行为或类型用途的说明。 摘要和描述连接起来，以形成函数、操作或类型生成的文档文件。
  描述可以包含行内 LaTeX 格式的符号和公式。
- **输入**：对操作或函数的输入元组的说明。
  可以包含其他 Markdown 子节，指示输入元组的每个单独元素。
- **输出**：操作或函数返回的元组的说明。
- **类型参数**：一个空节，其中每个泛型类型参数包含一个附加子节。
- **示例**：操作、函数或类型正在使用的简短示例。
- **备注**：其他 prose，描述操作、函数或类型的某个方面。
- **另请参阅**：表示相关函数、操作或用户定义类型的完全限定名称的列表。
- **引用**：要记录的项的引用和引文的列表。

## <a name="next-steps"></a>后续步骤

了解 Q # 中的[操作和函数](xref:microsoft.quantum.guide.operationsfunctions)。