---
title: Q# 文件结构
description: 描述文件的结构和语法 Q# 。
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.filestructure
no-loc:
- Q#
- $$v
ms.openlocfilehash: 98b3a2e35186989b8191cc566a5d5310bc26eafc
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833309"
---
# <a name="no-locq-file-structure"></a><span data-ttu-id="a26ce-103">Q# 文件结构</span><span class="sxs-lookup"><span data-stu-id="a26ce-103">Q# File Structure</span></span>

<span data-ttu-id="a26ce-104">Q#文件由*命名空间声明*序列组成。</span><span class="sxs-lookup"><span data-stu-id="a26ce-104">A Q# file consists of a sequence of *namespace declarations*.</span></span>
<span data-ttu-id="a26ce-105">每个命名空间声明都包含用户定义的类型、操作和函数的声明，可以按任意顺序包含每种类型的声明的任意数目。</span><span class="sxs-lookup"><span data-stu-id="a26ce-105">Each namespace declaration contains declarations for user-defined types, operations, and functions, and can contain any number of each type of declaration and in any order.</span></span>
<span data-ttu-id="a26ce-106">有关命名空间中的声明的详细信息，请参阅 [用户定义的类型](xref:microsoft.quantum.guide.types#user-defined-types)、 [操作](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations)和 [函数](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions)。</span><span class="sxs-lookup"><span data-stu-id="a26ce-106">For more information on declarations within a namespace, see [user-defined types](xref:microsoft.quantum.guide.types#user-defined-types), [operations](xref:microsoft.quantum.guide.operationsfunctions#defining-new-operations), and [functions](xref:microsoft.quantum.guide.operationsfunctions#defining-new-functions).</span></span>

<span data-ttu-id="a26ce-107">可在命名空间声明之外显示的唯一文本为注释。</span><span class="sxs-lookup"><span data-stu-id="a26ce-107">The only text that can appear outside of a namespace declaration is comments.</span></span>
<span data-ttu-id="a26ce-108">特别是，命名空间的文档注释位于声明之前。</span><span class="sxs-lookup"><span data-stu-id="a26ce-108">In particular, documentation comments for a namespace precede the declaration.</span></span> <span data-ttu-id="a26ce-109">有关详细信息，请参阅本文中的 [文档注释](#documentation-comments) 。</span><span class="sxs-lookup"><span data-stu-id="a26ce-109">For more information, see [Documentation comments](#documentation-comments) in this article.</span></span> 

## <a name="namespace-declarations"></a><span data-ttu-id="a26ce-110">命名空间声明</span><span class="sxs-lookup"><span data-stu-id="a26ce-110">Namespace Declarations</span></span>

<span data-ttu-id="a26ce-111">Q#文件通常只包含一个命名空间声明，但可能没有 (并且为空，或者只包含注释) 或可能包含多个命名空间。</span><span class="sxs-lookup"><span data-stu-id="a26ce-111">A Q# file typically has just one namespace declaration, but could have none (and be empty or just contain comments) or could contain multiple namespaces.</span></span>
<span data-ttu-id="a26ce-112">命名空间声明不能嵌套。</span><span class="sxs-lookup"><span data-stu-id="a26ce-112">Namespace declarations can not be nested.</span></span>

<span data-ttu-id="a26ce-113">可以在编译的多个文件中声明相同的命名空间 Q# ，只要不存在具有相同名称的类型、操作或函数声明。</span><span class="sxs-lookup"><span data-stu-id="a26ce-113">You can declare the same namespace in multiple Q# files that are compiled together, as long as there are no type, operation, or function declarations with the same name.</span></span>
<span data-ttu-id="a26ce-114">具体而言，在多个文件的同一命名空间中定义同一类型是无效的，即使这些声明相同也是如此。</span><span class="sxs-lookup"><span data-stu-id="a26ce-114">In particular, it is invalid to define the same type in the same namespace in multiple files, even if the declarations are identical.</span></span>

<span data-ttu-id="a26ce-115">命名空间声明包含关键字 `namespace` ，后跟命名空间的名称，以及包含在括在大括号中的命名空间中的声明 `{ }` 。</span><span class="sxs-lookup"><span data-stu-id="a26ce-115">A namespace declaration consists of the keyword `namespace`, followed by the name of the namespace, and the declarations contained in the namespace enclosed in braces `{ }`.</span></span>
<span data-ttu-id="a26ce-116">命名空间名称遵循由句点分隔的一个或多个合法符号序列的 .NET 模式 `.` 。</span><span class="sxs-lookup"><span data-stu-id="a26ce-116">Namespace names follow the .NET pattern of a sequence of one or more legal symbols separated by periods `.`.</span></span>
<span data-ttu-id="a26ce-117">例如， `MyQuantumStuff` 和 `Microsoft.Quantum.Intrinsic` 是有效的命名空间名称。</span><span class="sxs-lookup"><span data-stu-id="a26ce-117">For example, `MyQuantumStuff` and `Microsoft.Quantum.Intrinsic` are valid namespace names.</span></span>
<span data-ttu-id="a26ce-118">按照约定，将命名空间名称中的符号大写，不过，这并不是必需的。</span><span class="sxs-lookup"><span data-stu-id="a26ce-118">By convention, capitalize the symbols in a namespace name, however, this is not required.</span></span>

<span data-ttu-id="a26ce-119">对在文件中进一步声明的类型或 callables 的引用可以正确解析。在引用之前，不需要类型、操作或函数声明。</span><span class="sxs-lookup"><span data-stu-id="a26ce-119">References to types or callables declared further down in a file resolve properly; there is no need for the type, operation, or function declaration to precede a reference to it.</span></span>

## <a name="open-directives"></a><span data-ttu-id="a26ce-120">打开指令</span><span class="sxs-lookup"><span data-stu-id="a26ce-120">Open Directives</span></span>

<span data-ttu-id="a26ce-121">在命名空间块中，使用 `open` 指令导入在某个命名空间中声明的所有类型和 callables，并按它们的非限定名称引用它们。</span><span class="sxs-lookup"><span data-stu-id="a26ce-121">Within a namespace block, use the `open` directive to import all types and callables declared in a certain namespace and refer to them by their unqualified name.</span></span>
<span data-ttu-id="a26ce-122">此类 `open` 指令由关键字组成 `open` ，后跟要打开的命名空间和终止分号。</span><span class="sxs-lookup"><span data-stu-id="a26ce-122">Such an `open` directive consists of the `open` keyword, followed by the namespace to be opened and a terminating semicolon.</span></span>

> [!NOTE] 
> <span data-ttu-id="a26ce-123">所有 `open` 指令必须出现在 `function` `operation` `newtype` 命名空间块中的任何、或声明之前。</span><span class="sxs-lookup"><span data-stu-id="a26ce-123">All `open` directives must appear before any `function`, `operation`, or `newtype` declarations in the namespace block.</span></span>

<span data-ttu-id="a26ce-124">（可选）可以为打开的命名空间定义短名称。</span><span class="sxs-lookup"><span data-stu-id="a26ce-124">Optionally, you can define a short name for the opened namespace.</span></span> <span data-ttu-id="a26ce-125">如果定义了短名称，则必须通过定义的短名称来限定该命名空间中的所有元素。</span><span class="sxs-lookup"><span data-stu-id="a26ce-125">If a short name is defined, you must qualify all elements from that namespace by the defined short name.</span></span> <span data-ttu-id="a26ce-126">例如，给定以下命名空间声明和打开指令，</span><span class="sxs-lookup"><span data-stu-id="a26ce-126">For example, given the following namespace declaration and open directives,</span></span>

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace

    // operation, function, and newtype declarations

}
```

<span data-ttu-id="a26ce-127">如果声明的操作使用中的 `Op` 操作 `Microsoft.Quantum.Intrinsic` ，则只需使用即可调用该操作 `Op` 。</span><span class="sxs-lookup"><span data-stu-id="a26ce-127">if a declared operation uses an operation `Op` from `Microsoft.Quantum.Intrinsic`, you call it by simply using `Op`.</span></span>
<span data-ttu-id="a26ce-128">但是，若要从调用某个 `Fn` 函数 `Microsoft.Quantum.Math` ，必须使用调用它 `Math.Fn` 。</span><span class="sxs-lookup"><span data-stu-id="a26ce-128">However, to call a certain function `Fn` from `Microsoft.Quantum.Math`, you must call it using `Math.Fn`.</span></span>

<span data-ttu-id="a26ce-129">`open`指令适用于文件中的整个命名空间块。</span><span class="sxs-lookup"><span data-stu-id="a26ce-129">The `open` directive applies to the entire namespace block within a file.</span></span>
<span data-ttu-id="a26ce-130">因此，如果在与前面相同的文件中定义了其他命名空间 Q# `NS` ，则在第二个命名空间中定义的任何操作/函数/类型都将无法从或中访问任何内容， `Microsoft.Quantum.Intrinsic` `Microsoft.Quantum.Math` 除非你在其中重复了 open 指令。</span><span class="sxs-lookup"><span data-stu-id="a26ce-130">Hence, if you define an additional namespace in the same Q# file as `NS` earlier, then any operations/functions/types defined in the second namespace would not have access to anything from `Microsoft.Quantum.Intrinsic` or `Microsoft.Quantum.Math` unless you repeated the open directives therein.</span></span> 

<span data-ttu-id="a26ce-131">若要引用 *未* 在当前命名空间中打开的另一个命名空间中定义的类型或可调用，必须按其完全限定名称引用它。</span><span class="sxs-lookup"><span data-stu-id="a26ce-131">To reference a type or callable defined in another namespace that is *not* opened in the current namespace, you must reference it by its fully-qualified name.</span></span>
<span data-ttu-id="a26ce-132">例如，给定 `Op` 命名空间中名为的操作 `X.Y` ：</span><span class="sxs-lookup"><span data-stu-id="a26ce-132">For example, given an operation named `Op` from the `X.Y` namespace:</span></span>

* <span data-ttu-id="a26ce-133">必须按其完全限定名称引用它 `X.Y.Op` ，除非 `X.Y` 之前在当前块中打开了该命名空间。</span><span class="sxs-lookup"><span data-stu-id="a26ce-133">You must reference it by its fully-qualified name `X.Y.Op`, unless the `X.Y` namespace has been opened earlier in the current block.</span></span> 
* <span data-ttu-id="a26ce-134">即使 `X` 命名空间已打开，也不能将该操作作为引用 `Y.Op` 。</span><span class="sxs-lookup"><span data-stu-id="a26ce-134">Even if the `X` namespace is opened, it is not possible to reference the operation as `Y.Op`.</span></span>
* <span data-ttu-id="a26ce-135">如果 `Z` `X.Y` 在该命名空间和文件中定义了的短名称，则必须将引用 `Op` 为 `Z.Op` 。</span><span class="sxs-lookup"><span data-stu-id="a26ce-135">If you defined the short name `Z` for `X.Y` in that namespace and file, you must reference `Op` as `Z.Op`.</span></span> 

<span data-ttu-id="a26ce-136">通常最好通过使用指令来包含命名空间 `open` 。</span><span class="sxs-lookup"><span data-stu-id="a26ce-136">It is usually better to include a namespace by using an `open` directive.</span></span>
<span data-ttu-id="a26ce-137">如果两个命名空间定义具有相同名称的构造，并且当前源使用两者中的构造，则需要使用完全限定的名称。</span><span class="sxs-lookup"><span data-stu-id="a26ce-137">Using a fully-qualified name is required if two namespaces define constructs with the same name, and the current source uses constructs from both.</span></span>

<span data-ttu-id="a26ce-138">Q# 遵循与其他 .NET 语言相同的命名规则。</span><span class="sxs-lookup"><span data-stu-id="a26ce-138">Q# follows the same rules for naming as other .NET languages.</span></span>
<span data-ttu-id="a26ce-139">但是，不 Q# 支持对命名空间的相对引用。</span><span class="sxs-lookup"><span data-stu-id="a26ce-139">However, Q# does not support relative references to namespaces.</span></span>
<span data-ttu-id="a26ce-140">例如，如果命名空间 `a.b` 为打开状态，则对名为的操作的引用不 `c.d` 会解析为具有完整名称的操作*not* `a.b.c.d` 。</span><span class="sxs-lookup"><span data-stu-id="a26ce-140">For example, if the namespace `a.b` is open, a reference to an operation named `c.d` does *not* resolve to an operation with full name `a.b.c.d`.</span></span>

## <a name="formatting"></a><span data-ttu-id="a26ce-141">格式化</span><span class="sxs-lookup"><span data-stu-id="a26ce-141">Formatting</span></span>

<span data-ttu-id="a26ce-142">大多数 Q# 语句和指令以终止分号结束 `;` 。</span><span class="sxs-lookup"><span data-stu-id="a26ce-142">Most Q# statements and directives end with a terminating semicolon, `;`.</span></span>
<span data-ttu-id="a26ce-143">语句和声明（如 `for` ） `operation` 以语句块结尾 (参阅以下部分) 不需要终止分号。</span><span class="sxs-lookup"><span data-stu-id="a26ce-143">Statements and declarations such as `for` and `operation` that end with a statement block (see the following section) do not require a terminating semicolon.</span></span>
<span data-ttu-id="a26ce-144">每个语句说明都说明终止分号是否是必需的。</span><span class="sxs-lookup"><span data-stu-id="a26ce-144">Each statement description notes whether the terminating semicolon is required.</span></span>

<span data-ttu-id="a26ce-145">语句（如表达式、声明和指令）可以跨多行进行划分。</span><span class="sxs-lookup"><span data-stu-id="a26ce-145">Statements, like expressions, declarations, and directives, can be broken out across multiple lines.</span></span>
<span data-ttu-id="a26ce-146">避免在单个行上放置多个语句。</span><span class="sxs-lookup"><span data-stu-id="a26ce-146">Avoid putting multiple statements on a single line.</span></span>

## <a name="statement-blocks"></a><span data-ttu-id="a26ce-147">语句块</span><span class="sxs-lookup"><span data-stu-id="a26ce-147">Statement Blocks</span></span>

<span data-ttu-id="a26ce-148">Q# 语句分为语句块，它们包含在大括号中 `{ }` 。</span><span class="sxs-lookup"><span data-stu-id="a26ce-148">Q# statements are grouped into statement blocks, which are contained with braces `{ }`.</span></span> <span data-ttu-id="a26ce-149">语句块以开头开始，以 `{` 结束 `}` 。</span><span class="sxs-lookup"><span data-stu-id="a26ce-149">A statement block starts with an opening `{` and ends with a closing `}`.</span></span>

<span data-ttu-id="a26ce-150">在词法上包含在另一个块内的语句块被视为包含块的子块;包含和子块也称为外部和内部块。</span><span class="sxs-lookup"><span data-stu-id="a26ce-150">A statement block that is lexically enclosed within another block is considered to be a sub-block of the containing block; containing and sub-blocks are also called outer and inner blocks.</span></span>

## <a name="comments"></a><span data-ttu-id="a26ce-151">注释</span><span class="sxs-lookup"><span data-stu-id="a26ce-151">Comments</span></span>

<span data-ttu-id="a26ce-152">注释以两个正斜杠开头， `//` 并继续到行的末尾。</span><span class="sxs-lookup"><span data-stu-id="a26ce-152">Comments begin with two forward slashes, `//`, and continue until the end of the line.</span></span>
<span data-ttu-id="a26ce-153">注释可以出现在源文件中的任何位置 Q# 。</span><span class="sxs-lookup"><span data-stu-id="a26ce-153">A comment can appear anywhere in a Q# source file.</span></span>

## <a name="documentation-comments"></a><span data-ttu-id="a26ce-154">文档注释</span><span class="sxs-lookup"><span data-stu-id="a26ce-154">Documentation Comments</span></span>

<span data-ttu-id="a26ce-155">`///`当编译器在命名空间、操作、专用化、函数或类型定义紧靠前出现时，编译器会对以三个正斜杠开头的注释进行专门处理。</span><span class="sxs-lookup"><span data-stu-id="a26ce-155">Comments that begin with three forward slashes, `///`, are treated specially by the compiler when they appear immediately before a namespace, operation, specialization, function, or type definition.</span></span>
<span data-ttu-id="a26ce-156">在这种情况下，编译器会将它们视为已定义的可调用或用户定义类型的文档，这与其他 .NET 语言相同。</span><span class="sxs-lookup"><span data-stu-id="a26ce-156">In that case, the compiler treats them as documentation for the defined callable or user-defined type, the same as other .NET languages.</span></span>

<span data-ttu-id="a26ce-157">在 `///` 注释中，作为 API 文档一部分显示的文本将设置为 [Markdown](https://daringfireball.net/projects/markdown/syntax)，并使用特殊命名标头指示的文档的不同部分。</span><span class="sxs-lookup"><span data-stu-id="a26ce-157">Within `///` comments, text to appear as a part of API documentation is formatted as [Markdown](https://daringfireball.net/projects/markdown/syntax), with different parts of the documentation indicated by specially-named headers.</span></span>
<span data-ttu-id="a26ce-158">在 Markdown 中，在 `@"<ref target>"` 中使用扩展来交叉引用操作、函数和用户定义的类型 Q# 。</span><span class="sxs-lookup"><span data-stu-id="a26ce-158">In Markdown, use the `@"<ref target>"` extension to cross-reference operations, functions, and user-defined types in Q#.</span></span> <span data-ttu-id="a26ce-159">替换 `<ref target>` 为所引用代码对象的完全限定名称。</span><span class="sxs-lookup"><span data-stu-id="a26ce-159">Replace `<ref target>` with the fully qualified name of the referenced code object.</span></span>
<span data-ttu-id="a26ce-160">不同的文档引擎还可能支持其他 Markdown 扩展。</span><span class="sxs-lookup"><span data-stu-id="a26ce-160">Different documentation engines may also support additional Markdown extensions.</span></span>

<span data-ttu-id="a26ce-161">例如：</span><span class="sxs-lookup"><span data-stu-id="a26ce-161">For example:</span></span>

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

<span data-ttu-id="a26ce-162">以下名称是有效的文档注释标头。</span><span class="sxs-lookup"><span data-stu-id="a26ce-162">The following names are valid as documentation comment headers.</span></span>

- <span data-ttu-id="a26ce-163">**摘要**：函数或操作行为的简短摘要，或类型的用途。</span><span class="sxs-lookup"><span data-stu-id="a26ce-163">**Summary**: A short summary of the behavior of a function or operation, or the purpose of a type.</span></span> <span data-ttu-id="a26ce-164">摘要的第一个段落用于悬停信息。</span><span class="sxs-lookup"><span data-stu-id="a26ce-164">The first paragraph of the summary is used for hover information.</span></span> <span data-ttu-id="a26ce-165">它应为纯文本。</span><span class="sxs-lookup"><span data-stu-id="a26ce-165">It should be plain text.</span></span>
- <span data-ttu-id="a26ce-166">**说明**：函数或操作的行为或类型用途的说明。</span><span class="sxs-lookup"><span data-stu-id="a26ce-166">**Description**: A description of the behavior of a function or operation, or the purpose of a type.</span></span> <span data-ttu-id="a26ce-167">摘要和说明共同构成了函数、操作或类型所生成的文档文件。</span><span class="sxs-lookup"><span data-stu-id="a26ce-167">Together, the summary and description form the generated documentation file for the function, operation, or type.</span></span>
  <span data-ttu-id="a26ce-168">说明支持行内 LaTeX 格式的符号和公式。</span><span class="sxs-lookup"><span data-stu-id="a26ce-168">The description supports in-line LaTeX-formatted symbols and equations.</span></span>
- <span data-ttu-id="a26ce-169">**输入**：对操作或函数的输入元组的说明。</span><span class="sxs-lookup"><span data-stu-id="a26ce-169">**Input**: A description of the input tuple for an operation or function.</span></span>
  <span data-ttu-id="a26ce-170">可以包含其他 Markdown 子节，指示输入元组的每个元素。</span><span class="sxs-lookup"><span data-stu-id="a26ce-170">Can contain additional Markdown subsections indicating each element of the input tuple.</span></span>
- <span data-ttu-id="a26ce-171">**输出**：操作或函数返回的元组的说明。</span><span class="sxs-lookup"><span data-stu-id="a26ce-171">**Output**: A description of the tuple returned by an operation or function.</span></span>
- <span data-ttu-id="a26ce-172">**类型参数**：一个空节，其中每个泛型类型参数包含一个附加子节。</span><span class="sxs-lookup"><span data-stu-id="a26ce-172">**Type Parameters**: An empty section that contains one additional subsection for each generic type parameter.</span></span>
- <span data-ttu-id="a26ce-173">**示例**：操作、函数或所使用的类型的简短示例。</span><span class="sxs-lookup"><span data-stu-id="a26ce-173">**Example**: A short example of the operation, function, or type in use.</span></span>
- <span data-ttu-id="a26ce-174">**备注**：其他 prose，描述操作、函数或类型的某个方面。</span><span class="sxs-lookup"><span data-stu-id="a26ce-174">**Remarks**: Miscellaneous prose describing some aspect of the operation, function, or type.</span></span>
- <span data-ttu-id="a26ce-175">**另请参阅**：表示相关函数、操作或用户定义类型的完全限定名称的列表。</span><span class="sxs-lookup"><span data-stu-id="a26ce-175">**See Also**: A list of fully qualified names indicating related functions, operations, or user-defined types.</span></span>
- <span data-ttu-id="a26ce-176">**引用**：记录的项的引用和引文列表。</span><span class="sxs-lookup"><span data-stu-id="a26ce-176">**References**: A list of references and citations for the documented item.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a26ce-177">后续步骤</span><span class="sxs-lookup"><span data-stu-id="a26ce-177">Next steps</span></span>

<span data-ttu-id="a26ce-178">了解中的 [操作和函数](xref:microsoft.quantum.guide.operationsfunctions) Q# 。</span><span class="sxs-lookup"><span data-stu-id="a26ce-178">Learn about [Operations and Functions](xref:microsoft.quantum.guide.operationsfunctions) in Q#.</span></span>