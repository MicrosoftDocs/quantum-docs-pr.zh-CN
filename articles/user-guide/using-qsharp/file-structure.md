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
# <a name="q-file-structure"></a><span data-ttu-id="420b5-103">Q # 文件结构</span><span class="sxs-lookup"><span data-stu-id="420b5-103">Q# File Structure</span></span>

<span data-ttu-id="420b5-104">每个 Q # 操作、函数和用户定义的类型都是在命名空间中定义的。</span><span class="sxs-lookup"><span data-stu-id="420b5-104">Every Q# operation, function, and user-defined type is defined within a namespace.</span></span>

<span data-ttu-id="420b5-105">Q # 文件由一系列*命名空间声明*组成。</span><span class="sxs-lookup"><span data-stu-id="420b5-105">A Q# file consists of a sequence of *namespace declarations*.</span></span>
<span data-ttu-id="420b5-106">每个命名空间声明都包含用户定义的类型、操作和函数的声明。</span><span class="sxs-lookup"><span data-stu-id="420b5-106">Each namespace declaration contains declarations for user-defined types, operations, and functions.</span></span>
<span data-ttu-id="420b5-107">命名空间声明可以包含任何类型的声明，并按任意顺序包含。</span><span class="sxs-lookup"><span data-stu-id="420b5-107">A namespace declaration may contain any number of each type of declaration, and in any order.</span></span>
<span data-ttu-id="420b5-108">若要详细了解如何在命名空间中声明[用户定义的类型](xref:microsoft.quantum.guide.types#user-defined-types)、[操作](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations)和[函数](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions)，请单击以下链接。</span><span class="sxs-lookup"><span data-stu-id="420b5-108">Follow these links for more details on declaring [user-defined types](xref:microsoft.quantum.guide.types#user-defined-types), [operations](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations), and [functions](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions) within a namespace.</span></span>

<span data-ttu-id="420b5-109">可在命名空间声明之外显示的唯一文本为注释。</span><span class="sxs-lookup"><span data-stu-id="420b5-109">The only text that can appear outside of a namespace declaration is comments.</span></span>
<span data-ttu-id="420b5-110">具体而言，命名空间的文档注释（更多详细信息）位于声明之前。</span><span class="sxs-lookup"><span data-stu-id="420b5-110">In particular, documentation comments (more details below) for a namespace precede the declaration.</span></span>

## <a name="namespace-declarations"></a><span data-ttu-id="420b5-111">命名空间声明</span><span class="sxs-lookup"><span data-stu-id="420b5-111">Namespace Declarations</span></span>

<span data-ttu-id="420b5-112">Q # 文件通常只包含一个命名空间声明，但可能不包含（且为空或只包含注释）或可能包含多个命名空间。</span><span class="sxs-lookup"><span data-stu-id="420b5-112">A Q# file will typically have exactly one namespace declaration, but may have none (and be empty or just contain comments) or may contain multiple namespaces.</span></span>
<span data-ttu-id="420b5-113">命名空间声明不能嵌套。</span><span class="sxs-lookup"><span data-stu-id="420b5-113">Namespace declarations may not be nested.</span></span>

<span data-ttu-id="420b5-114">同一个命名空间可以在编译在一起的多个 Q # 文件中声明，只要不存在具有相同名称的类型、操作或函数声明。</span><span class="sxs-lookup"><span data-stu-id="420b5-114">The same namespace may be declared in multiple Q# files that are compiled together, as long as there are no type, operation, or function declarations with the same name.</span></span>
<span data-ttu-id="420b5-115">具体而言，在多个文件的同一命名空间中定义同一类型是无效的，即使这些声明相同也是如此。</span><span class="sxs-lookup"><span data-stu-id="420b5-115">In particular, it is invalid to define the same type in the same namespace in multiple files, even if the declarations are identical.</span></span>

<span data-ttu-id="420b5-116">命名空间声明包含关键字 `namespace` ，后跟命名空间的名称、左大括号 `{` 、命名空间中包含的声明和右大括号 `}` 。</span><span class="sxs-lookup"><span data-stu-id="420b5-116">A namespace declaration consists of the keyword `namespace`, followed by the name of the namespace, an open brace `{`, the declarations contained in the namespace, and a close brace `}`.</span></span>
<span data-ttu-id="420b5-117">命名空间名称遵循由句点分隔的一个或多个合法符号序列的 .NET 模式 `.` 。</span><span class="sxs-lookup"><span data-stu-id="420b5-117">Namespace names follow the .NET pattern of a sequence of one or more legal symbols separated by periods `.`.</span></span>
<span data-ttu-id="420b5-118">例如， `MyQuantumStuff` 和 `Microsoft.Quantum.Intrinsic` 是有效的命名空间名称。</span><span class="sxs-lookup"><span data-stu-id="420b5-118">For instance, `MyQuantumStuff` and `Microsoft.Quantum.Intrinsic` are valid namespace names.</span></span>
<span data-ttu-id="420b5-119">按照约定，命名空间名称中的符号采用大写形式，但这不是必需的。</span><span class="sxs-lookup"><span data-stu-id="420b5-119">By convention, the symbols in a namespace name are capitalized, but this is not required.</span></span>

<span data-ttu-id="420b5-120">已正确解析对文件中的向下声明的类型或 callables 的引用。在引用之前，不需要类型、操作或函数声明。</span><span class="sxs-lookup"><span data-stu-id="420b5-120">References to types or callables declared further down in a file are resolved properly; there is no need for the type, operation, or function declaration to precede a reference to it.</span></span>

## <a name="open-directives"></a><span data-ttu-id="420b5-121">打开指令</span><span class="sxs-lookup"><span data-stu-id="420b5-121">Open Directives</span></span>

<span data-ttu-id="420b5-122">在命名空间块中， `open` 指令可用于导入在某个命名空间中声明的所有类型和 callables，并按其非限定名称引用它们。</span><span class="sxs-lookup"><span data-stu-id="420b5-122">Within a namespace block, the `open` directive may be used to import all types and callables declared in a certain namespace and refer to them by their unqualified name.</span></span>
<span data-ttu-id="420b5-123">此类 `open` 指令由关键字组成 `open` ，后跟要打开的命名空间和终止分号。</span><span class="sxs-lookup"><span data-stu-id="420b5-123">Such an `open` directive consists of the `open` keyword, followed by the namespace to be opened and a terminating semicolon.</span></span>

> [!NOTE] 
> <span data-ttu-id="420b5-124">所有 `open` 指令必须出现在 `function` `operation` `newtype` 命名空间块中的任何、或声明之前。</span><span class="sxs-lookup"><span data-stu-id="420b5-124">All `open` directives must appear before any `function`, `operation`, or `newtype` declarations in the namespace block.</span></span>

<span data-ttu-id="420b5-125">（可选）可定义已打开命名空间的短名称，使来自该命名空间的所有元素都可以（并且需要）由定义的短名称限定。</span><span class="sxs-lookup"><span data-stu-id="420b5-125">Optionally, a short name for the opened namespace may be defined such that all elements from that namespace can (and need) to be qualified by the defined short name.</span></span> <span data-ttu-id="420b5-126">例如，给定以下命名空间声明和打开指令，</span><span class="sxs-lookup"><span data-stu-id="420b5-126">For example, given the following namespace declaration and open directives,</span></span>

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace

    // operation, function, and newtype declarations

}
```

<span data-ttu-id="420b5-127">如果声明的操作使用来自的操作 `Op` `Microsoft.Quantum.Intrinsic` ，只需使用即可调用该操作 `Op` 。</span><span class="sxs-lookup"><span data-stu-id="420b5-127">if an operation we declare uses an operation `Op` from `Microsoft.Quantum.Intrinsic`, we would call it by simply using `Op`.</span></span>
<span data-ttu-id="420b5-128">但是，如果我们想要从调用某个函数 `Fn` `Microsoft.Quantum.Math` ，则需要使用调用它 `Math.Fn` 。</span><span class="sxs-lookup"><span data-stu-id="420b5-128">However, if we wanted a call a certain function `Fn` from `Microsoft.Quantum.Math`, we would need to call it using `Math.Fn`.</span></span>

<span data-ttu-id="420b5-129">`open`指令适用于文件中的整个命名空间块。</span><span class="sxs-lookup"><span data-stu-id="420b5-129">The `open` directive applies to the entire namespace block within a file.</span></span>
<span data-ttu-id="420b5-130">因此，如果我们要在与上述相同的 Q # 文件中定义其他命名空间 `NS` ，则在第二个命名空间中定义的任何操作/函数/类型都不能从或中的任何内容访问， `Microsoft.Quantum.Intrinsic` `Microsoft.Quantum.Math` 除非我们重复了本文中的 open 指令。</span><span class="sxs-lookup"><span data-stu-id="420b5-130">Hence, if we were to define an additional namespace in the same Q# file as `NS` above, then any operations/functions/types defined in the second namespace would not have access to anything from `Microsoft.Quantum.Intrinsic` or `Microsoft.Quantum.Math` unless we repeated the open directives therein.</span></span> 

<span data-ttu-id="420b5-131">在当前命名空间中*未*打开的其他命名空间中定义的类型或可调用必须由其完全限定名称引用。</span><span class="sxs-lookup"><span data-stu-id="420b5-131">A type or callable defined in another namespace that is *not* opened in the current namespace must be referenced by its fully-qualified name.</span></span>
<span data-ttu-id="420b5-132">例如，命名空间中名为的操作 `Op` `X.Y` 必须由其完全限定名称引用 `X.Y.Op` ，除非 `X.Y` 之前在当前块中打开了该命名空间。</span><span class="sxs-lookup"><span data-stu-id="420b5-132">For example, an operation named `Op` from the `X.Y` namespace must be referenced by its fully-qualified name `X.Y.Op`, unless the `X.Y` namespace has been opened earlier in the current block.</span></span> <span data-ttu-id="420b5-133">如上所述，即使 `X` 已打开命名空间，也不能将该操作作为引用 `Y.Op` 。</span><span class="sxs-lookup"><span data-stu-id="420b5-133">As mentioned above, even if the `X` namespace has been opened, it is not possible to reference the operation as `Y.Op`.</span></span>
<span data-ttu-id="420b5-134">如果已 `Z` `X.Y` 在该命名空间和文件中定义了的短名称，则 `Op` 需要将其称为 `Z.Op` 。</span><span class="sxs-lookup"><span data-stu-id="420b5-134">If a short name `Z` for `X.Y` has been defined in that namespace and file, then `Op` needs to be referred to as `Z.Op`.</span></span> 

<span data-ttu-id="420b5-135">通常最好通过使用指令来包含命名空间 `open` 。</span><span class="sxs-lookup"><span data-stu-id="420b5-135">It is usually better to include a namespace by using an `open` directive.</span></span>
<span data-ttu-id="420b5-136">如果两个命名空间定义具有相同名称的构造，并且当前源使用两者中的构造，则需要使用完全限定的名称。</span><span class="sxs-lookup"><span data-stu-id="420b5-136">Using a fully-qualified name is required if two namespaces define constructs with the same name, and the current source uses constructs from both.</span></span>

<span data-ttu-id="420b5-137">Q # 遵循的规则与其他 .NET 语言相同。</span><span class="sxs-lookup"><span data-stu-id="420b5-137">Q# follows the same rules for naming as other .NET languages.</span></span>
<span data-ttu-id="420b5-138">但是，Q # 不支持对命名空间进行相对引用。</span><span class="sxs-lookup"><span data-stu-id="420b5-138">However, Q# does not support relative references to namespaces.</span></span>
<span data-ttu-id="420b5-139">也就是说，如果 `a.b` 已打开命名空间，则不会将对名为的操作的引用 `c.d` 解析为具有完整名称的*not*操作 `a.b.c.d` 。</span><span class="sxs-lookup"><span data-stu-id="420b5-139">That is, if the namespace `a.b` has been opened, a reference to an operation named `c.d` will *not* be resolved to an operation with full name `a.b.c.d`.</span></span>

## <a name="formatting"></a><span data-ttu-id="420b5-140">格式化</span><span class="sxs-lookup"><span data-stu-id="420b5-140">Formatting</span></span>

<span data-ttu-id="420b5-141">大多数 Q # 语句和指令以终止分号结束 `;` 。</span><span class="sxs-lookup"><span data-stu-id="420b5-141">Most Q# statements and directives end with a terminating semicolon, `;`.</span></span>
<span data-ttu-id="420b5-142">语句和声明（例如 `for` 和 `operation` ）以语句块结尾（见下文），不需要终止分号。</span><span class="sxs-lookup"><span data-stu-id="420b5-142">Statements and declarations such as `for` and `operation` that end with a statement block (see below) do not require a terminating semicolon.</span></span>
<span data-ttu-id="420b5-143">每个语句说明都说明终止分号是否是必需的。</span><span class="sxs-lookup"><span data-stu-id="420b5-143">Each statement description notes whether the terminating semicolon is required.</span></span>

<span data-ttu-id="420b5-144">语句（如表达式、声明和指令）可以跨多行进行划分。</span><span class="sxs-lookup"><span data-stu-id="420b5-144">Statements, like expressions, declarations, and directives, may be broken out across multiple lines.</span></span>
<span data-ttu-id="420b5-145">应避免在单个行上包含多个语句。</span><span class="sxs-lookup"><span data-stu-id="420b5-145">Having multiple statements on a single line should be avoided.</span></span>

## <a name="statement-blocks"></a><span data-ttu-id="420b5-146">语句块</span><span class="sxs-lookup"><span data-stu-id="420b5-146">Statement Blocks</span></span>

<span data-ttu-id="420b5-147">Q # 语句分组为语句块。</span><span class="sxs-lookup"><span data-stu-id="420b5-147">Q# statements are grouped into statement blocks.</span></span>
<span data-ttu-id="420b5-148">语句块以开头开始，以 `{` 结束 `}` 。</span><span class="sxs-lookup"><span data-stu-id="420b5-148">A statement block starts with an opening `{` and ends with a closing `}`.</span></span>

<span data-ttu-id="420b5-149">在词法上包含在另一个块内的语句块被视为包含块的子块;包含和子块也称为外部和内部块。</span><span class="sxs-lookup"><span data-stu-id="420b5-149">A statement block that is lexically enclosed within another block is considered to be a sub-block of the containing block; containing and sub-blocks are also called outer and inner blocks.</span></span>

## <a name="comments"></a><span data-ttu-id="420b5-150">注释</span><span class="sxs-lookup"><span data-stu-id="420b5-150">Comments</span></span>

<span data-ttu-id="420b5-151">注释以两个正斜杠开头， `//` 并继续到行尾。</span><span class="sxs-lookup"><span data-stu-id="420b5-151">Comments begin with two forward slashes, `//`, and continue until the end of line.</span></span>
<span data-ttu-id="420b5-152">注释可以出现在 Q # 源文件中的任何位置。</span><span class="sxs-lookup"><span data-stu-id="420b5-152">A comment may appear anywhere in a Q# source file.</span></span>

## <a name="documentation-comments"></a><span data-ttu-id="420b5-153">文档注释</span><span class="sxs-lookup"><span data-stu-id="420b5-153">Documentation Comments</span></span>

<span data-ttu-id="420b5-154">`///`当编译器在命名空间、操作、专用化、函数或类型定义紧靠前出现时，编译器会对以三个正斜杠开头的注释进行专门处理。</span><span class="sxs-lookup"><span data-stu-id="420b5-154">Comments that begin with three forward slashes, `///`, are treated specially by the compiler when they appear immediately before a namespace, operation, specialization, function, or type definition.</span></span>
<span data-ttu-id="420b5-155">在这种情况下，它们的内容将作为定义的可调用或用户定义类型的文档，如其他 .NET 语言所示。</span><span class="sxs-lookup"><span data-stu-id="420b5-155">In that case, their contents are taken as documentation for the defined callable or user-defined type, as for other .NET languages.</span></span>

<span data-ttu-id="420b5-156">在 `///` 注释中，作为 API 文档一部分显示的文本的格式为[Markdown](https://daringfireball.net/projects/markdown/syntax)，特别命名的标头表明文档的不同部分。</span><span class="sxs-lookup"><span data-stu-id="420b5-156">Within `///` comments, text to appear as a part of API documentation is formatted as [Markdown](https://daringfireball.net/projects/markdown/syntax), with different parts of the documentation being indicated by specially-named headers.</span></span>
<span data-ttu-id="420b5-157">作为 Markdown 的扩展，可以使用来包含 Q # 中对操作、函数和用户定义类型的交叉引用， `@"<ref target>"` 其中， `<ref target>` 替换为所引用的代码对象的完全限定名称。</span><span class="sxs-lookup"><span data-stu-id="420b5-157">As an extension to Markdown, cross references to operations, functions and user-defined types in Q# can be included using the `@"<ref target>"`, where `<ref target>` is replaced by the fully qualified name of the code object being referenced.</span></span>
<span data-ttu-id="420b5-158">文档引擎也可以选择支持其他 Markdown 扩展。</span><span class="sxs-lookup"><span data-stu-id="420b5-158">Optionally, a documentation engine may also support additional Markdown extensions.</span></span>

<span data-ttu-id="420b5-159">例如：</span><span class="sxs-lookup"><span data-stu-id="420b5-159">For example:</span></span>

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

<span data-ttu-id="420b5-160">以下名称被识别为文档注释标头。</span><span class="sxs-lookup"><span data-stu-id="420b5-160">The following names are recognized as documentation comment headers.</span></span>

- <span data-ttu-id="420b5-161">**摘要**：函数或操作行为或类型用途的简短摘要。</span><span class="sxs-lookup"><span data-stu-id="420b5-161">**Summary**: A short summary of the behavior of a function or operation, or of the purpose of a type.</span></span> <span data-ttu-id="420b5-162">摘要的第一个段落用于悬停信息。</span><span class="sxs-lookup"><span data-stu-id="420b5-162">The first paragraph of the summary is used for hover information.</span></span> <span data-ttu-id="420b5-163">它应为纯文本。</span><span class="sxs-lookup"><span data-stu-id="420b5-163">It should be plain text.</span></span>
- <span data-ttu-id="420b5-164">**说明**：对函数或操作的行为或类型用途的说明。</span><span class="sxs-lookup"><span data-stu-id="420b5-164">**Description**: A description of the behavior of a function or operation, or of the purpose of a type.</span></span> <span data-ttu-id="420b5-165">摘要和描述连接起来，以形成函数、操作或类型生成的文档文件。</span><span class="sxs-lookup"><span data-stu-id="420b5-165">The summary and description are concatenated to form the generated documentation file for the function, operation, or type.</span></span>
  <span data-ttu-id="420b5-166">描述可以包含行内 LaTeX 格式的符号和公式。</span><span class="sxs-lookup"><span data-stu-id="420b5-166">The description may contain in-line LaTeX-formatted symbols and equations.</span></span>
- <span data-ttu-id="420b5-167">**输入**：对操作或函数的输入元组的说明。</span><span class="sxs-lookup"><span data-stu-id="420b5-167">**Input**: A description of the input tuple for an operation or function.</span></span>
  <span data-ttu-id="420b5-168">可以包含其他 Markdown 子节，指示输入元组的每个单独元素。</span><span class="sxs-lookup"><span data-stu-id="420b5-168">May contain additional Markdown subsections indicating each individual element of the input tuple.</span></span>
- <span data-ttu-id="420b5-169">**输出**：操作或函数返回的元组的说明。</span><span class="sxs-lookup"><span data-stu-id="420b5-169">**Output**: A description of the tuple returned by an operation or function.</span></span>
- <span data-ttu-id="420b5-170">**类型参数**：一个空节，其中每个泛型类型参数包含一个附加子节。</span><span class="sxs-lookup"><span data-stu-id="420b5-170">**Type Parameters**: An empty section which contains one additional subsection for each generic type parameter.</span></span>
- <span data-ttu-id="420b5-171">**示例**：操作、函数或类型正在使用的简短示例。</span><span class="sxs-lookup"><span data-stu-id="420b5-171">**Example**: A short example of the operation, function or type in use.</span></span>
- <span data-ttu-id="420b5-172">**备注**：其他 prose，描述操作、函数或类型的某个方面。</span><span class="sxs-lookup"><span data-stu-id="420b5-172">**Remarks**: Miscellaneous prose describing some aspect of the operation, function, or type.</span></span>
- <span data-ttu-id="420b5-173">**另请参阅**：表示相关函数、操作或用户定义类型的完全限定名称的列表。</span><span class="sxs-lookup"><span data-stu-id="420b5-173">**See Also**: A list of fully qualified names indicating related functions, operations, or user-defined types.</span></span>
- <span data-ttu-id="420b5-174">**引用**：要记录的项的引用和引文的列表。</span><span class="sxs-lookup"><span data-stu-id="420b5-174">**References**: A list of references and citations for the item being documented.</span></span>

## <a name="next-steps"></a><span data-ttu-id="420b5-175">后续步骤</span><span class="sxs-lookup"><span data-stu-id="420b5-175">Next steps</span></span>

<span data-ttu-id="420b5-176">了解 Q # 中的[操作和函数](xref:microsoft.quantum.guide.operationsfunctions)。</span><span class="sxs-lookup"><span data-stu-id="420b5-176">Learn about [Operations and Functions](xref:microsoft.quantum.guide.operationsfunctions) in Q#.</span></span>