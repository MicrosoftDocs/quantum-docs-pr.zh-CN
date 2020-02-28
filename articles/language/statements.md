---
title: 'Q # 语句'
description: '了解如何正确使用 Q # 中的语句，包括函数和操作声明、变量声明和赋值以及操作调用。'
author: QuantumWriter
uid: microsoft.quantum.language.statements
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: e801a5fdd24b973f47d23d2aca6f11bbebf333d4
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904666"
---
# <a name="statements-and-other-constructs"></a><span data-ttu-id="0bccb-103">语句和其他构造</span><span class="sxs-lookup"><span data-stu-id="0bccb-103">Statements and Other Constructs</span></span>

## <a name="comments"></a><span data-ttu-id="0bccb-104">Comments</span><span class="sxs-lookup"><span data-stu-id="0bccb-104">Comments</span></span>

<span data-ttu-id="0bccb-105">注释以两个正斜杠（`//`）开头，并继续到行尾。</span><span class="sxs-lookup"><span data-stu-id="0bccb-105">Comments begin with two forward slashes, `//`, and continue until the end of line.</span></span>
<span data-ttu-id="0bccb-106">注释可以出现在 Q # 源文件中的任何位置。</span><span class="sxs-lookup"><span data-stu-id="0bccb-106">A comment may appear anywhere in a Q# source file.</span></span>

### <a name="documentation-comments"></a><span data-ttu-id="0bccb-107">文档注释</span><span class="sxs-lookup"><span data-stu-id="0bccb-107">Documentation Comments</span></span>

<span data-ttu-id="0bccb-108">当编译器在命名空间、操作、专用化、函数或类型定义紧靠前出现时，编译器会对以第三个正斜杠（`///`）开头的注释进行专门处理。</span><span class="sxs-lookup"><span data-stu-id="0bccb-108">Comments that begin with three forward slashes, `///`, are treated specially by the compiler when they appear immediately before a namespace, operation, specialization, function, or type definition.</span></span>
<span data-ttu-id="0bccb-109">在这种情况下，它们的内容将作为定义的可调用或用户定义类型的文档，如其他 .NET 语言所示。</span><span class="sxs-lookup"><span data-stu-id="0bccb-109">In that case, their contents are taken as documentation for the defined callable or user-defined type, as for other .NET languages.</span></span>

<span data-ttu-id="0bccb-110">在 `///` 注释中，作为 API 文档一部分显示的文本格式设置为[Markdown](https://daringfireball.net/projects/markdown/syntax)，并且特殊命名的标头所指示的文档的不同部分。</span><span class="sxs-lookup"><span data-stu-id="0bccb-110">Within `///` comments, text to appear as a part of API documentation is formatted as [Markdown](https://daringfireball.net/projects/markdown/syntax), with different parts of the documentation being indicated by specially-named headers.</span></span>
<span data-ttu-id="0bccb-111">作为 Markdown 的扩展，可以使用 `@"<ref target>"`包含 Q # 中对操作、函数和用户定义类型的交叉引用，其中 `<ref target>` 替换为所引用的代码对象的完全限定名称。</span><span class="sxs-lookup"><span data-stu-id="0bccb-111">As an extension to Markdown, cross references to operations, functions and user-defined types in Q# can be included using the `@"<ref target>"`, where `<ref target>` is replaced by the fully qualified name of the code object being referenced.</span></span>
<span data-ttu-id="0bccb-112">文档引擎也可以选择支持其他 Markdown 扩展。</span><span class="sxs-lookup"><span data-stu-id="0bccb-112">Optionally, a documentation engine may also support additional Markdown extensions.</span></span>

<span data-ttu-id="0bccb-113">例如：</span><span class="sxs-lookup"><span data-stu-id="0bccb-113">For example:</span></span>

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

<span data-ttu-id="0bccb-114">以下名称被识别为文档注释标头。</span><span class="sxs-lookup"><span data-stu-id="0bccb-114">The following names are recognized as documentation comment headers.</span></span>

- <span data-ttu-id="0bccb-115">**摘要**：函数或操作行为或类型用途的简短摘要。</span><span class="sxs-lookup"><span data-stu-id="0bccb-115">**Summary**: A short summary of the behavior of a function or operation, or of the purpose of a type.</span></span> <span data-ttu-id="0bccb-116">摘要的第一个段落用于悬停信息。</span><span class="sxs-lookup"><span data-stu-id="0bccb-116">The first paragraph of the summary is used for hover information.</span></span> <span data-ttu-id="0bccb-117">它应为纯文本。</span><span class="sxs-lookup"><span data-stu-id="0bccb-117">It should be plain text.</span></span>
- <span data-ttu-id="0bccb-118">**说明**：对函数或操作的行为或类型用途的说明。</span><span class="sxs-lookup"><span data-stu-id="0bccb-118">**Description**: A description of the behavior of a function or operation, or of the purpose of a type.</span></span> <span data-ttu-id="0bccb-119">摘要和描述连接起来，以形成函数、操作或类型生成的文档文件。</span><span class="sxs-lookup"><span data-stu-id="0bccb-119">The summary and description are concatenated to form the generated documentation file for the function, operation, or type.</span></span>
  <span data-ttu-id="0bccb-120">描述可以包含行内 LaTeX 格式的符号和公式。</span><span class="sxs-lookup"><span data-stu-id="0bccb-120">The description may contain in-line LaTeX-formatted symbols and equations.</span></span>
- <span data-ttu-id="0bccb-121">**输入**：对操作或函数的输入元组的说明。</span><span class="sxs-lookup"><span data-stu-id="0bccb-121">**Input**: A description of the input tuple for an operation or function.</span></span>
  <span data-ttu-id="0bccb-122">可以包含其他 Markdown 子节，指示输入元组的每个单独元素。</span><span class="sxs-lookup"><span data-stu-id="0bccb-122">May contain additional Markdown subsections indicating each individual element of the input tuple.</span></span>
- <span data-ttu-id="0bccb-123">**输出**：操作或函数返回的元组的说明。</span><span class="sxs-lookup"><span data-stu-id="0bccb-123">**Output**: A description of the tuple returned by an operation or function.</span></span>
- <span data-ttu-id="0bccb-124">**类型参数**：一个空节，其中每个泛型类型参数包含一个附加子节。</span><span class="sxs-lookup"><span data-stu-id="0bccb-124">**Type Parameters**: An empty section which contains one additional subsection for each generic type parameter.</span></span>
- <span data-ttu-id="0bccb-125">**示例**：操作、函数或类型正在使用的简短示例。</span><span class="sxs-lookup"><span data-stu-id="0bccb-125">**Example**: A short example of the operation, function or type in use.</span></span>
- <span data-ttu-id="0bccb-126">**备注**：其他 prose，描述操作、函数或类型的某个方面。</span><span class="sxs-lookup"><span data-stu-id="0bccb-126">**Remarks**: Miscellaneous prose describing some aspect of the operation, function, or type.</span></span>
- <span data-ttu-id="0bccb-127">**另请参阅**：表示相关函数、操作或用户定义类型的完全限定名称的列表。</span><span class="sxs-lookup"><span data-stu-id="0bccb-127">**See Also**: A list of fully qualified names indicating related functions, operations, or user-defined types.</span></span>
- <span data-ttu-id="0bccb-128">**引用**：要记录的项的引用和引文的列表。</span><span class="sxs-lookup"><span data-stu-id="0bccb-128">**References**: A list of references and citations for the item being documented.</span></span>

## <a name="namespaces"></a><span data-ttu-id="0bccb-129">命名空间</span><span class="sxs-lookup"><span data-stu-id="0bccb-129">Namespaces</span></span>

<span data-ttu-id="0bccb-130">每个 Q # 操作、函数和用户定义的类型都是在命名空间中定义的。</span><span class="sxs-lookup"><span data-stu-id="0bccb-130">Every Q# operation, function, and user-defined type is defined within a namespace.</span></span>
<span data-ttu-id="0bccb-131">Q # 遵循的规则与其他 .NET 语言相同。</span><span class="sxs-lookup"><span data-stu-id="0bccb-131">Q# follows the same rules for naming as other .NET languages.</span></span>
<span data-ttu-id="0bccb-132">但是，Q # 不支持对命名空间进行相对引用。</span><span class="sxs-lookup"><span data-stu-id="0bccb-132">However, Q# does not support relative references to namespaces.</span></span>
<span data-ttu-id="0bccb-133">也就是说，如果已打开命名空间 `a.b`，则不会将对操作名称 `c.d` 的引用解析为具有完整名称 `a.b.c.d`的操作。</span><span class="sxs-lookup"><span data-stu-id="0bccb-133">That is, if the namespace `a.b` has been opened, a reference to an operation names `c.d` will not be resolved to an operation with full name `a.b.c.d`.</span></span>

<span data-ttu-id="0bccb-134">在命名空间块中，可以使用 `open` 指令导入在某个命名空间中声明的所有类型和 callables，并按其非限定名称引用它们。</span><span class="sxs-lookup"><span data-stu-id="0bccb-134">Within a namespace block, the `open` directive may be used to import all types and callables declared in a certain namespace and refer to them by their unqualified name.</span></span> <span data-ttu-id="0bccb-135">（可选）可定义已打开命名空间的短名称，使来自该命名空间的所有元素都可以（并且需要）由定义的短名称限定。</span><span class="sxs-lookup"><span data-stu-id="0bccb-135">Optionally, a short name for the opened namespace may be defined such that all elements from that namespace can (and need) to be qualified by the defined short name.</span></span> <span data-ttu-id="0bccb-136">`open` 指令适用于文件中的整个命名空间块。</span><span class="sxs-lookup"><span data-stu-id="0bccb-136">The `open` directive applies to the entire namespace block within a file.</span></span>

<span data-ttu-id="0bccb-137">在当前命名空间中未打开的其他命名空间中定义的类型或可调用必须由其完全限定名称引用。</span><span class="sxs-lookup"><span data-stu-id="0bccb-137">A type or callable defined in another namespace that is not opened in the current namespace must be referenced by its fully-qualified name.</span></span>
<span data-ttu-id="0bccb-138">例如，除非之前在当前块中打开了 `X.Y` 命名空间，否则 `X.Y` 命名空间中名为 `Op` 的操作必须由其完全限定名称 `X.Y.Op`引用。</span><span class="sxs-lookup"><span data-stu-id="0bccb-138">For example, an operation named `Op` in the `X.Y` namespace must be referenced by its fully-qualified name `X.Y.Op`, unless the `X.Y` namespace has been opened earlier in the current block.</span></span> <span data-ttu-id="0bccb-139">如上所述，即使已打开 `X` 命名空间，也无法 `Y.Op`中引用操作。</span><span class="sxs-lookup"><span data-stu-id="0bccb-139">As mentioned above, even if the `X` namespace has been opened, it is not possible to reference the operation as `Y.Op`.</span></span>
<span data-ttu-id="0bccb-140">如果在该命名空间和文件中定义了 `X.Y` 的短名称 `Z`，则 `Op` 需要称为 `Z.Op`。</span><span class="sxs-lookup"><span data-stu-id="0bccb-140">If a short name `Z` for `X.Y` has been defined in that namespace and file, then `Op` needs to be referred to as `Z.Op`.</span></span> 

```qsharp
namespace NS {
    open Microsoft.Quantum.Intrinsic; // opens the namespace
    open Microsoft.Quantum.Math as Math; // defines a short name for the namespace
}
```

<span data-ttu-id="0bccb-141">通常，最好通过使用 `open` 指令来包含命名空间。</span><span class="sxs-lookup"><span data-stu-id="0bccb-141">It is usually better to include a namespace by using an `open` directive.</span></span>
<span data-ttu-id="0bccb-142">如果两个命名空间定义具有相同名称的构造，并且当前源使用两者中的构造，则需要使用完全限定的名称。</span><span class="sxs-lookup"><span data-stu-id="0bccb-142">Using a fully-qualified name is required if two namespaces define constructs with the same name, and the current source uses constructs from both.</span></span>

## <a name="formatting"></a><span data-ttu-id="0bccb-143">格式设置</span><span class="sxs-lookup"><span data-stu-id="0bccb-143">Formatting</span></span>

<span data-ttu-id="0bccb-144">大多数 Q # 语句和指令以终止分号 `;`结束。</span><span class="sxs-lookup"><span data-stu-id="0bccb-144">Most Q# statements and directives end with a terminating semicolon, `;`.</span></span>
<span data-ttu-id="0bccb-145">语句和声明（如 `for` 和以语句块结尾的 `operation`）不需要终止分号。</span><span class="sxs-lookup"><span data-stu-id="0bccb-145">Statements and declarations such as `for` and `operation` that end with a statement block do not require a terminating semicolon.</span></span>
<span data-ttu-id="0bccb-146">每个语句说明都说明终止分号是否是必需的。</span><span class="sxs-lookup"><span data-stu-id="0bccb-146">Each statement description notes whether the terminating semicolon is required.</span></span>

<span data-ttu-id="0bccb-147">语句（如表达式、声明和指令）可以跨多行进行划分。</span><span class="sxs-lookup"><span data-stu-id="0bccb-147">Statements, like expressions, declarations, and directives, may be broken out across multiple lines.</span></span>
<span data-ttu-id="0bccb-148">应避免在单个行上包含多个语句。</span><span class="sxs-lookup"><span data-stu-id="0bccb-148">Having multiple statements on a single line should be avoided.</span></span>

## <a name="statement-blocks"></a><span data-ttu-id="0bccb-149">语句块</span><span class="sxs-lookup"><span data-stu-id="0bccb-149">Statement Blocks</span></span>

<span data-ttu-id="0bccb-150">Q # 语句分组为语句块。</span><span class="sxs-lookup"><span data-stu-id="0bccb-150">Q# statements are grouped into statement blocks.</span></span>
<span data-ttu-id="0bccb-151">语句块以开始 `{` 开始，以结束 `}`结束。</span><span class="sxs-lookup"><span data-stu-id="0bccb-151">A statement block starts with an opening `{` and ends with a closing `}`.</span></span>

<span data-ttu-id="0bccb-152">在词法上包含在另一个块内的语句块被视为包含块的子块;包含和子块也称为外部和内部块。</span><span class="sxs-lookup"><span data-stu-id="0bccb-152">A statement block that is lexically enclosed within another block is considered to be a sub-block of the containing block; containing and sub-blocks are also called outer and inner blocks.</span></span>

## <a name="symbol-binding-and-assignment"></a><span data-ttu-id="0bccb-153">符号绑定和赋值</span><span class="sxs-lookup"><span data-stu-id="0bccb-153">Symbol Binding and Assignment</span></span>

<span data-ttu-id="0bccb-154">Q # 区分可变和不可变符号。</span><span class="sxs-lookup"><span data-stu-id="0bccb-154">Q# distinguishes between mutable and immutable symbols.</span></span>
<span data-ttu-id="0bccb-155">通常，建议使用不可变符号，因为它允许编译器执行更多优化。</span><span class="sxs-lookup"><span data-stu-id="0bccb-155">In general, the use of immutable symbols is encouraged because it allows the compiler to perform more optimizations.</span></span>

<span data-ttu-id="0bccb-156">绑定的左侧包含一个符号元组和一个表达式的右端。</span><span class="sxs-lookup"><span data-stu-id="0bccb-156">The left-hand-side of the binding consists of a symbol tuple, and the right hand side of an expression.</span></span>

<span data-ttu-id="0bccb-157">由于所有 Q # 类型都是值类型-如果 qubits 采用特殊的角色，则在将值绑定到符号或重新绑定符号时，会创建 "copy"。</span><span class="sxs-lookup"><span data-stu-id="0bccb-157">Since all Q# types are value types - with the qubits taking a somewhat special role - formally a "copy" is created when a value is bound to a symbol, or when a symbol is rebound.</span></span> <span data-ttu-id="0bccb-158">也就是说，Q # 的行为与在分配时创建副本的行为相同。</span><span class="sxs-lookup"><span data-stu-id="0bccb-158">That is to say, the behavior of Q# is the same as if a copy were created on assignment.</span></span> <span data-ttu-id="0bccb-159">这特别包括数组。</span><span class="sxs-lookup"><span data-stu-id="0bccb-159">This in particular also includes arrays.</span></span> <span data-ttu-id="0bccb-160">当然，实际上只需根据需要重新创建相关的部分。</span><span class="sxs-lookup"><span data-stu-id="0bccb-160">Of course in practice only the relevant pieces are actually recreated as needed.</span></span> 

### <a name="tuple-deconstruction"></a><span data-ttu-id="0bccb-161">元组析构</span><span class="sxs-lookup"><span data-stu-id="0bccb-161">Tuple Deconstruction</span></span>

<span data-ttu-id="0bccb-162">如果绑定的右侧是一个元组，则该元组可能在赋值时是析构的。</span><span class="sxs-lookup"><span data-stu-id="0bccb-162">If the right-hand side of the binding is a tuple, then that tuple may be deconstructed upon assignment.</span></span>
<span data-ttu-id="0bccb-163">此类 deconstructions 可能涉及嵌套元组，只要右侧的元组形状与符号元组的形状兼容，所有完整或部分析构都有效。</span><span class="sxs-lookup"><span data-stu-id="0bccb-163">Such deconstructions may involve nested tuples, and any full or partial deconstruction is valid as long as the shape of the tuple on the right hand side is compatible with the shape of the symbol tuple.</span></span>
<span data-ttu-id="0bccb-164">当 `=` 的右侧是元组值表达式时，也可以使用元组析构。</span><span class="sxs-lookup"><span data-stu-id="0bccb-164">Tuple deconstruction can in particular also be used when the right-hand side of the `=` is a tuple-valued expression.</span></span>

```qsharp
let (i, f) = (5, 0.1); // i is bound to 5 and f to 0.1
mutable (a, (_, b)) = (1, (2, 3)); // a is bound to 1, b is bound to 3
mutable (x, y) = ((1, 2), [3, 4]); // x is bound to (1,2), y is bound to [3,4]
set (x, _, y) = ((5, 6), 7, [8]);  // x is rebound to (5,6), y is rebound to [8]
let (r1, r2) = MeasureTwice(q1, PauliX, q2, PauliY);
```

### <a name="immutable-symbols"></a><span data-ttu-id="0bccb-165">不可变符号</span><span class="sxs-lookup"><span data-stu-id="0bccb-165">Immutable Symbols</span></span>

<span data-ttu-id="0bccb-166">使用 `let` 语句绑定不可变符号。</span><span class="sxs-lookup"><span data-stu-id="0bccb-166">Immutable symbols are bound using the `let` statement.</span></span>
<span data-ttu-id="0bccb-167">这大致相当于语言（例如C#）中的变量声明和初始化，但 Q # 符号一旦绑定后可能不会更改;`let` 绑定是不可变的。</span><span class="sxs-lookup"><span data-stu-id="0bccb-167">This is roughly equivalent to variable declaration and initialization in languages such as C#, except that Q# symbols, once bound, may not be changed; `let` bindings are immutable.</span></span>

<span data-ttu-id="0bccb-168">不可变绑定包含关键字 `let`，后跟符号或符号元组、等号 `=`、将符号绑定到的表达式和终止分号。</span><span class="sxs-lookup"><span data-stu-id="0bccb-168">An immutable binding consists of the keyword `let`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to bind the symbol(s) to, and a terminating semicolon.</span></span>
<span data-ttu-id="0bccb-169">绑定符号的类型是根据右侧的表达式推断出来的。</span><span class="sxs-lookup"><span data-stu-id="0bccb-169">The type of the bound symbol(s) is inferred based on the expression on the right hand side.</span></span>

### <a name="mutable-symbols"></a><span data-ttu-id="0bccb-170">可变符号</span><span class="sxs-lookup"><span data-stu-id="0bccb-170">Mutable Symbols</span></span>

<span data-ttu-id="0bccb-171">可变符号使用 `mutable` 语句进行定义和初始化。</span><span class="sxs-lookup"><span data-stu-id="0bccb-171">Mutable symbols are defined and initialized using the `mutable` statement.</span></span>
<span data-ttu-id="0bccb-172">作为 `mutable` 语句的一部分声明和绑定的符号可能会在后面的代码中重新绑定到不同的值。</span><span class="sxs-lookup"><span data-stu-id="0bccb-172">Symbols declared and bound as part of a `mutable` statement may be rebound to a different value later in the code.</span></span> 

<span data-ttu-id="0bccb-173">可变绑定语句包含关键字 `mutable`，后跟符号或符号元组、等号 `=`、将符号绑定到的表达式和终止分号。</span><span class="sxs-lookup"><span data-stu-id="0bccb-173">A mutable binding statement consists of the keyword `mutable`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to bind the symbol(s) to, and a terminating semicolon.</span></span>
<span data-ttu-id="0bccb-174">绑定符号的类型是根据右侧的表达式推断出来的。</span><span class="sxs-lookup"><span data-stu-id="0bccb-174">The type of the bound symbol(s) is inferred based on the expression on the right hand side.</span></span> <span data-ttu-id="0bccb-175">如果稍后在代码中重新绑定符号，则其类型不会更改，并且绑定值需要与该类型兼容。</span><span class="sxs-lookup"><span data-stu-id="0bccb-175">If a symbol is rebound later in the code, its type does not change, and the bound value needs to be compatible with that type.</span></span>

### <a name="rebinding-of-mutable-symbols"></a><span data-ttu-id="0bccb-176">重新绑定可变符号</span><span class="sxs-lookup"><span data-stu-id="0bccb-176">Rebinding of Mutable Symbols</span></span>

<span data-ttu-id="0bccb-177">可以使用 `set` 语句重新绑定可变变量。</span><span class="sxs-lookup"><span data-stu-id="0bccb-177">A mutable variable may be rebound using a `set` statement.</span></span>
<span data-ttu-id="0bccb-178">这种重新绑定包含关键字 `set`，后跟符号或符号元组、等号 `=`、将符号重新绑定到的表达式和终止分号。</span><span class="sxs-lookup"><span data-stu-id="0bccb-178">Such a rebinding consists of the keyword `set`, followed by a symbol or symbol tuple, an equals sign `=`, an expression to rebind the symbol(s) to, and a terminating semicolon.</span></span>
<span data-ttu-id="0bccb-179">该值必须与它所绑定到的符号的类型兼容。</span><span class="sxs-lookup"><span data-stu-id="0bccb-179">The value must be compatible with the type(s) of the symbol(s) it is bound to.</span></span>

#### <a name="apply-and-reassign-statement"></a><span data-ttu-id="0bccb-180">应用和重新分配语句</span><span class="sxs-lookup"><span data-stu-id="0bccb-180">Apply-and-Reassign Statement</span></span>

<span data-ttu-id="0bccb-181">如果右侧包含二元运算符的应用程序，并将结果重新绑定到运算符的左侧参数，则称为 "应用" 和 "重新分配" 语句的一种特殊的 set 语句。</span><span class="sxs-lookup"><span data-stu-id="0bccb-181">A particular kind of set-statement we refer to as an apply-and-reassign statement provides a convenient way of concatenation if the right hand side consists of the application of a binary operator and the result is to be rebound to the left argument to the operator.</span></span> <span data-ttu-id="0bccb-182">例如，</span><span class="sxs-lookup"><span data-stu-id="0bccb-182">For example,</span></span>
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter += 1;
    // ...
}
```
<span data-ttu-id="0bccb-183">递增 `for` 循环的每次迭代中的计数器 `counter` 的值。</span><span class="sxs-lookup"><span data-stu-id="0bccb-183">increments the value of the counter `counter` in each iteration of the `for` loop.</span></span> <span data-ttu-id="0bccb-184">上述代码等效于</span><span class="sxs-lookup"><span data-stu-id="0bccb-184">The code above is equivalent to</span></span> 
```qsharp
mutable counter = 0;
for (i in 1 .. 2 .. 10) {
    set counter = counter + 1;
    // ...
}
```
<span data-ttu-id="0bccb-185">类似的语句可用于所有的二元运算符，其中左侧的类型与表达式类型匹配。</span><span class="sxs-lookup"><span data-stu-id="0bccb-185">Similar statements are available for all binary operators in which the type of the left-hand-side matches the expression type.</span></span> <span data-ttu-id="0bccb-186">这为示例提供了一种简单的方法来累积值：</span><span class="sxs-lookup"><span data-stu-id="0bccb-186">This provides for example a convenient way to accumulate values:</span></span>
```qsharp
mutable results = new Result[0];
for (qubit in qubits) {
    set results += [M(q)];
    // ...
}
```
#### <a name="update-and-reassign-statement"></a><span data-ttu-id="0bccb-187">更新和重新分配语句</span><span class="sxs-lookup"><span data-stu-id="0bccb-187">Update-and-Reassign Statement</span></span>

<span data-ttu-id="0bccb-188">在右侧的复制和更新表达式中存在类似的连接。</span><span class="sxs-lookup"><span data-stu-id="0bccb-188">A similar concatenation exists for copy-and-update expressions on the right hand side.</span></span> <span data-ttu-id="0bccb-189">相应地，对于用户定义的类型中的命名项以及数组项，都存在更新和重新分配语句。</span><span class="sxs-lookup"><span data-stu-id="0bccb-189">Correspondingly, update-and-reassign statements exist for named items in user-defined types as well as for array items.</span></span>  

```qsharp
newtype Complex = (Re : Double, Im : Double);

function ComplexSum(reals : Double[], ims : Double[]) : Complex[] {
    mutable res = Complex(0.,0.);

    for (r in reals) {
        set res w/= Re <- res::Re + r; // update-and-reassign statement
    }
    for (i in ims) {
        set res w/= Im <- res::Im + i; // update-and-reassign statement
    }
    return res;
}
```

<span data-ttu-id="0bccb-190">对于数组，我们的标准库包含用于许多常见数组初始化和操作需求的必需工具，因此有助于避免第一次更新数组项。</span><span class="sxs-lookup"><span data-stu-id="0bccb-190">In the case of arrays, our standard libraries contain the necessary tools for many common array initialization and manipulation needs, and thus help avoid having to update array items in the first place.</span></span> <span data-ttu-id="0bccb-191">如果需要，更新和重新分配语句提供了一种替代方法：</span><span class="sxs-lookup"><span data-stu-id="0bccb-191">Update-and-reassign statements provide an alternative if needed:</span></span>

```qsharp
operation GenerateRandomInts(max : Int, nSamples : Int) : Int[] {
    mutable samples = new Double[0];
    for (i in 1 .. nSamples) {
        set samples += [RandomInt(max)];
    }
    return samples;
}

operation SampleUniformDistrbution(nSamples : Int, nSteps : Int) : Double[] {
    let normalization = 1. / IntAsDouble(nSteps);
    mutable samples = GenerateRandomInts(nSteps, nSamples);
    
    for (i in IndexRange(samples) {
        let value = IntAsDouble(samples[i]);
        set samples w/= i <- normalization * value; // update-and-reassign statement
    }
}

```

> [!TIP]   
> <span data-ttu-id="0bccb-192">通过利用 <xref:microsoft.quantum.arrays>中提供的工具，避免不必要地使用 update 和重新分配语句。</span><span class="sxs-lookup"><span data-stu-id="0bccb-192">Avoid unnecessary use of update-and-reassign statements by leveraging the tools provided in <xref:microsoft.quantum.arrays>.</span></span>

<span data-ttu-id="0bccb-193">函数</span><span class="sxs-lookup"><span data-stu-id="0bccb-193">The function</span></span>
```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    mutable pauliArray = new Pauli[length];
    for (index in 0 .. length - 1) {
        set pauliArray w/= index <- 
            index == location ? pauli | PauliI;
    }    
    return pauliArray;
}
```
<span data-ttu-id="0bccb-194">例如，可以简单地使用 `Microsoft.Quantum.Arrays`中的函数 `ConstantArray`，并返回一个复制和更新表达式：</span><span class="sxs-lookup"><span data-stu-id="0bccb-194">for example can simply be simplified using the function `ConstantArray` in `Microsoft.Quantum.Arrays`, and returning a copy-and-update expression:</span></span>

```qsharp
function PauliEmbedding(pauli : Pauli, length : Int, location : Int) : Pauli[] {
    return ConstantArray(length, PauliI) w/ location <- pauli;
}
```

### <a name="binding-scopes"></a><span data-ttu-id="0bccb-195">绑定范围</span><span class="sxs-lookup"><span data-stu-id="0bccb-195">Binding Scopes</span></span>

<span data-ttu-id="0bccb-196">通常，符号绑定超出范围，并且在中出现的语句块的末尾变为不起作用。</span><span class="sxs-lookup"><span data-stu-id="0bccb-196">In general, symbol bindings go out of scope and become inoperative at the end of the statement block they occur in.</span></span>
<span data-ttu-id="0bccb-197">此规则有两种例外情况：</span><span class="sxs-lookup"><span data-stu-id="0bccb-197">There are two exceptions to this rule:</span></span>

- <span data-ttu-id="0bccb-198">`for` 循环的循环变量的绑定处于 for 循环主体的范围内，而不是在循环结束后。</span><span class="sxs-lookup"><span data-stu-id="0bccb-198">The binding of the loop variable of a `for` loop is in scope for the body of the for loop, but not after the end of the loop.</span></span>
- <span data-ttu-id="0bccb-199">`repeat`/`until` 循环的所有三个部分（正文、测试和修正）都被视为单个作用域，因此，在正文中绑定的符号可用于测试和修复中。</span><span class="sxs-lookup"><span data-stu-id="0bccb-199">All three portions of a `repeat`/`until` loop (the body, the test, and the fixup) are treated as a single scope, so symbols that are bound in the body are available in the test and in the fixup.</span></span>

<span data-ttu-id="0bccb-200">对于这两种类型的循环，每次循环都在其自己的作用域中执行，因此更早传递中的绑定在稍后的传递中不可用。</span><span class="sxs-lookup"><span data-stu-id="0bccb-200">For both types of loops, each pass through the loop executes in its own scope, so bindings from an earlier pass are not available in a later pass.</span></span>

<span data-ttu-id="0bccb-201">来自外部块的符号绑定由内部块继承。</span><span class="sxs-lookup"><span data-stu-id="0bccb-201">Symbol bindings from outer blocks are inherited by inner blocks.</span></span>
<span data-ttu-id="0bccb-202">一个符号只能绑定每个块一次;定义与作用域中的另一个符号名称相同（无 "隐藏"）的符号是非法的。</span><span class="sxs-lookup"><span data-stu-id="0bccb-202">A symbol may only be bound once per block; it is illegal to define a symbol with the same name as another symbol that is within scope (no "shadowing").</span></span>
<span data-ttu-id="0bccb-203">以下顺序是合法的：</span><span class="sxs-lookup"><span data-stu-id="0bccb-203">The following sequences would be legal:</span></span>

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
}
let n = 8;
...                 // n is 8
```

<span data-ttu-id="0bccb-204">and</span><span class="sxs-lookup"><span data-stu-id="0bccb-204">and</span></span>

```qsharp
if (a == b) {
    ...
    let n = 5;
    ...             // n is 5
} else {
    ...
    let n = 8;
    ...             // n is 8
}
```

<span data-ttu-id="0bccb-205">但这是非法的：</span><span class="sxs-lookup"><span data-stu-id="0bccb-205">But this would be illegal:</span></span>

```qsharp
let n = 5;
...                 // n is 5
let n = 8;          // Error!!
...
```

<span data-ttu-id="0bccb-206">如下所示：</span><span class="sxs-lookup"><span data-stu-id="0bccb-206">as would:</span></span>

```qsharp
let n = 8;
if (a == b) {
    ...             // n is 8
    let n = 5;      // Error!
    ...
}
...
```

## <a name="control-flow"></a><span data-ttu-id="0bccb-207">控制流</span><span class="sxs-lookup"><span data-stu-id="0bccb-207">Control Flow</span></span>

### <a name="for-loop"></a><span data-ttu-id="0bccb-208">适用于循环</span><span class="sxs-lookup"><span data-stu-id="0bccb-208">For Loop</span></span>

<span data-ttu-id="0bccb-209">`for` 语句支持对整数范围或数组进行迭代。</span><span class="sxs-lookup"><span data-stu-id="0bccb-209">The `for` statement supports iteration over an integer range or over an array.</span></span>
<span data-ttu-id="0bccb-210">语句由关键字 `for`、左括号 `(`、符号或符号元组、关键字 `in`、类型 `Range` 或数组的表达式、右括号 `)`和语句块组成。</span><span class="sxs-lookup"><span data-stu-id="0bccb-210">The statement consists of the keyword `for`, an open parenthesis `(`, followed by a symbol or symbol tuple, the keyword `in`, an expression of type `Range` or array, a close parenthesis `)`, and a statement block.</span></span>

<span data-ttu-id="0bccb-211">语句块（循环的主体）将重复执行，其中定义的符号（即循环变量）绑定到范围或数组中的每个值。</span><span class="sxs-lookup"><span data-stu-id="0bccb-211">The statement block (the body of the loop) is executed repeatedly, with the defined symbol(s) (the loop variable(s)) bound to each value in the range or array.</span></span>
<span data-ttu-id="0bccb-212">请注意，如果范围表达式的计算结果为空范围或数组，则不会执行主体。</span><span class="sxs-lookup"><span data-stu-id="0bccb-212">Note that if the range expression evaluates to an empty range or array, the body will not be executed at all.</span></span>
<span data-ttu-id="0bccb-213">在进入循环之前，将完全计算该表达式，并且在执行循环时不会更改。</span><span class="sxs-lookup"><span data-stu-id="0bccb-213">The expression is fully evaluated before entering the loop, and will not change while the loop is executing.</span></span>

<span data-ttu-id="0bccb-214">声明的符号的绑定是不可变的，并且与其他变量绑定遵循相同的规则。</span><span class="sxs-lookup"><span data-stu-id="0bccb-214">The binding of the declared symbol(s) is immutable and follows the same rules as other variable bindings.</span></span> <span data-ttu-id="0bccb-215">特别是，在赋值给循环变量时，可能会销毁数组，例如，在数组上循环的数组项。</span><span class="sxs-lookup"><span data-stu-id="0bccb-215">In particular, it is possible to destruct e.g. array items for an iteration over an array upon assignment to the loop variable(s).</span></span>

<span data-ttu-id="0bccb-216">例如，</span><span class="sxs-lookup"><span data-stu-id="0bccb-216">For example,</span></span>

```qsharp
// ...
for (qubit in qubits) { // qubits contains a Qubit[]
    H(qubit);
}

mutable results = new (Int, Results)[Length(qubits)];
for (index in 0 .. Length(qubits) - 1) {
    set results w/= index <- (index, M(qubits[index]));
}

mutable accumulated = 0;
for ((index, measured) in results) {
    if (measured == One) {
        set accumulated += 1 <<< index;
    }
}
```

<span data-ttu-id="0bccb-217">循环变量绑定到循环体的每个入口，并在主体末尾解除绑定。</span><span class="sxs-lookup"><span data-stu-id="0bccb-217">The loop variable is bound at each entrance to the loop body, and unbound at the end of the body.</span></span>
<span data-ttu-id="0bccb-218">具体而言，for 循环完成后不会绑定循环变量。</span><span class="sxs-lookup"><span data-stu-id="0bccb-218">In particular, the loop variable is not bound after the for loop is completed.</span></span>

### <a name="repeat-until-success-loop"></a><span data-ttu-id="0bccb-219">重复执行-成功循环</span><span class="sxs-lookup"><span data-stu-id="0bccb-219">Repeat-Until-Success Loop</span></span>

<span data-ttu-id="0bccb-220">`repeat` 语句支持量程 "重复到成功" 模式。</span><span class="sxs-lookup"><span data-stu-id="0bccb-220">The `repeat` statement supports the quantum “repeat until success” pattern.</span></span>
<span data-ttu-id="0bccb-221">它包含关键字 `repeat`，后跟语句块（_循环体_）、关键字 `until`、布尔表达式、终止分号或关键字 `fixup` 后跟另一个语句块（_修正_）。</span><span class="sxs-lookup"><span data-stu-id="0bccb-221">It consists of the keyword `repeat`, followed by a statement block (the _loop_ body), the keyword `until`, a Boolean expression, and either a terminating semicolon or the keyword `fixup` followed by another statement block (the _fixup_).</span></span>
<span data-ttu-id="0bccb-222">循环体、condition 和修正均视为单个作用域，因此，在主体中绑定的符号可用于条件和修正。</span><span class="sxs-lookup"><span data-stu-id="0bccb-222">The loop body, condition, and fixup are all considered to be a single scope, so symbols bound in the body are available in the condition and fixup.</span></span>

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

<span data-ttu-id="0bccb-223">执行循环体，然后计算条件。</span><span class="sxs-lookup"><span data-stu-id="0bccb-223">The loop body is executed, and then the condition is evaluated.</span></span>
<span data-ttu-id="0bccb-224">如果条件为 true，则语句已完成;否则，将执行修正，并从循环体开始重新执行该语句。</span><span class="sxs-lookup"><span data-stu-id="0bccb-224">If the condition is true, then the statement is completed; otherwise, the fixup is executed, and the statement is re-executed starting with the loop body.</span></span>
<span data-ttu-id="0bccb-225">请注意，完成修正的执行将结束语句的范围，以便在正文或修正范围内进行的符号绑定在后续的重复项中不可用。</span><span class="sxs-lookup"><span data-stu-id="0bccb-225">Note that completing the execution of the fixup ends the scope for the statement, so that symbol bindings made during the body or fixup are not available in subsequent repetitions.</span></span>

<span data-ttu-id="0bccb-226">例如，下面的代码是一种概率线路，可使用 Hadamard 和 T 入口 $V _3 = （\boldone + 2 i Z）/\sqrt{5}$。</span><span class="sxs-lookup"><span data-stu-id="0bccb-226">For example, the following code is a probabilistic circuit that implements an important rotation gate $V_3 = (\boldone + 2 i Z) / \sqrt{5}$ using the Hadamard and T gates.</span></span>
<span data-ttu-id="0bccb-227">循环在 $ \frac 中终止，{8}平均 {5}$ 重复。</span><span class="sxs-lookup"><span data-stu-id="0bccb-227">The loop terminates in $\frac{8}{5}$ repetitions on average.</span></span>
<span data-ttu-id="0bccb-228">有关详细信息，请参阅[*重复截止时间：单 qubit unitaries 的非确定性分解*](https://arxiv.org/abs/1311.1074)（Paetznick 和 Svore，2014）。</span><span class="sxs-lookup"><span data-stu-id="0bccb-228">See [*Repeat-Until-Success: Non-deterministic decomposition of single-qubit unitaries*](https://arxiv.org/abs/1311.1074) (Paetznick and Svore, 2014) for details.</span></span>

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

> [!TIP]   
> <span data-ttu-id="0bccb-229">避免在函数内使用重复-until 循环。</span><span class="sxs-lookup"><span data-stu-id="0bccb-229">Avoid using repeat-until-success loops inside functions.</span></span> <span data-ttu-id="0bccb-230">当函数中的循环时，将提供相应的功能。</span><span class="sxs-lookup"><span data-stu-id="0bccb-230">The corresponding functionality is provided by while loops in functions.</span></span> 

### <a name="while-loop"></a><span data-ttu-id="0bccb-231">While 循环</span><span class="sxs-lookup"><span data-stu-id="0bccb-231">While Loop</span></span>

<span data-ttu-id="0bccb-232">重复-直到成功模式有一个非常特定于量程的内涵。</span><span class="sxs-lookup"><span data-stu-id="0bccb-232">Repeat-until-success patterns have a very quantum-specific connotation.</span></span> <span data-ttu-id="0bccb-233">它们广泛用于特定的量程算法类，因此，它是 Q # 中的专用语言构造。</span><span class="sxs-lookup"><span data-stu-id="0bccb-233">They are widely used in particular classes of quantum algorithms -- hence the dedicated language construct in Q#.</span></span> <span data-ttu-id="0bccb-234">但是，在编译时，需要在量程运行时中特别小心地处理基于某个条件、其执行长度未知的循环。</span><span class="sxs-lookup"><span data-stu-id="0bccb-234">However, loops that break based on a condition and whose execution length is thus unknown at compile time need to be handled with particular care in a quantum runtime.</span></span> <span data-ttu-id="0bccb-235">另一方面，它们在函数中的使用是 unproblematic 的，因为它们仅包含将在常规（非量程）硬件上执行的代码。</span><span class="sxs-lookup"><span data-stu-id="0bccb-235">Their use within functions on the other hand is unproblematic, since these only contain code that will be executed on conventional (non-quantum) hardware.</span></span> 

<span data-ttu-id="0bccb-236">因此，Q # 支持仅在函数内使用 while 循环。</span><span class="sxs-lookup"><span data-stu-id="0bccb-236">Q# therefore supports to use of while loops within functions only.</span></span> <span data-ttu-id="0bccb-237">`while` 语句由关键字 `while`、左括号 `(`、条件（即布尔表达式）、右括号 `)`和语句块组成。</span><span class="sxs-lookup"><span data-stu-id="0bccb-237">A `while` statement consists of the keyword `while`, an open parenthesis `(`, a condition (i.e. a Boolean expression), a close parenthesis `)`, and a statement block.</span></span>
<span data-ttu-id="0bccb-238">只要条件的计算结果为 `true`，就会执行语句块（循环的主体）。</span><span class="sxs-lookup"><span data-stu-id="0bccb-238">The statement block (the body of the loop) is executed as long as the condition evaluates to `true`.</span></span>

```qsharp
// ...
mutable (item, index) = (-1, 0);
while (index < Length(arr) && item < 0) { 
    set item = arr[index];
    set index += 1;
}
```

### <a name="conditional-statement"></a><span data-ttu-id="0bccb-239">条件语句</span><span class="sxs-lookup"><span data-stu-id="0bccb-239">Conditional Statement</span></span>

<span data-ttu-id="0bccb-240">`if` 语句支持条件执行。</span><span class="sxs-lookup"><span data-stu-id="0bccb-240">The `if` statement supports conditional execution.</span></span>
<span data-ttu-id="0bccb-241">它包含关键字 `if`、左括号 `(`、布尔表达式、右括号 `)`和语句块（ _then_块）。</span><span class="sxs-lookup"><span data-stu-id="0bccb-241">It consists of the keyword `if`, an open parenthesis `(`, a Boolean expression, a close parenthesis `)`, and a statement block (the _then_ block).</span></span>
<span data-ttu-id="0bccb-242">这可能后跟任意数量的 else if 子句，其中每个子句都由关键字 `elif`、左括号 `(`、布尔表达式、右括号 `)`和语句块（ _else-if_块）组成。</span><span class="sxs-lookup"><span data-stu-id="0bccb-242">This may be followed by any number of else-if clauses, each of which consists of the keyword `elif`, an open parenthesis `(`, a Boolean expression, a close parenthesis `)`, and a statement block (the _else-if_ block).</span></span>
<span data-ttu-id="0bccb-243">最后，语句可选择使用 else 子句完成，后者由关键字 `else` 后跟另一个语句块（ _else_块）组成。</span><span class="sxs-lookup"><span data-stu-id="0bccb-243">Finally, the statement may optionally finish with an else clause, which consists of the keyword `else` followed by another statement block (the _else_ block).</span></span>
<span data-ttu-id="0bccb-244">计算条件，如果该条件为 true，则执行 then 块。</span><span class="sxs-lookup"><span data-stu-id="0bccb-244">The condition is evaluated, and if it is true, the then block is executed.</span></span>
<span data-ttu-id="0bccb-245">如果条件为 false，则计算第一个 else if 条件;如果为 true，则执行此 else-if block。</span><span class="sxs-lookup"><span data-stu-id="0bccb-245">If the condition is false, then the first else-if condition is evaluated; if it is true, that else-if block is executed.</span></span>
<span data-ttu-id="0bccb-246">否则，将测试第二个 else-if 块，然后是第三个块，依此类推，直到遇到具有 true 条件的子句或没有其他的 else 子句。</span><span class="sxs-lookup"><span data-stu-id="0bccb-246">Otherwise, the second else-if block is tested, and then the third, and so on until either a clause with a true condition is encountered or there are no more else-if clauses.</span></span>
<span data-ttu-id="0bccb-247">如果原始 if 条件和所有 else-if 子句的计算结果为 false，则在提供时将执行 else 块。</span><span class="sxs-lookup"><span data-stu-id="0bccb-247">If the original if condition and all else-if clauses evaluate to false, the else block is executed if one was provided.</span></span>

<span data-ttu-id="0bccb-248">请注意，执行的任何块在其自己的作用域中执行。</span><span class="sxs-lookup"><span data-stu-id="0bccb-248">Note that whichever block is executed is executed in its own scope.</span></span>
<span data-ttu-id="0bccb-249">在 if 语句结束后，在 then、else 或 else 块内进行的绑定将不可见。</span><span class="sxs-lookup"><span data-stu-id="0bccb-249">Bindings made inside of a then, else-if, or else block are not visible after the end of the if statement.</span></span>

<span data-ttu-id="0bccb-250">例如，</span><span class="sxs-lookup"><span data-stu-id="0bccb-250">For example,</span></span>

```qsharp
if (result == One) {
    X(target);
} 
```

<span data-ttu-id="0bccb-251">或</span><span class="sxs-lookup"><span data-stu-id="0bccb-251">or</span></span>

```qsharp
if (i == 1) {
    X(target);
} elif (i == 2) {
    Y(target);
} else {
    Z(target);
}
```

### <a name="return"></a><span data-ttu-id="0bccb-252">返回</span><span class="sxs-lookup"><span data-stu-id="0bccb-252">Return</span></span>

<span data-ttu-id="0bccb-253">Return 语句结束操作或函数的执行，并将值返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="0bccb-253">The return statement ends execution of an operation or function and returns a value to the caller.</span></span>
<span data-ttu-id="0bccb-254">它包含关键字 `return`，后跟适当类型的表达式和终止分号。</span><span class="sxs-lookup"><span data-stu-id="0bccb-254">It consists of the keyword `return`, followed by an expression of the appropriate type, and a terminating semicolon.</span></span>

<span data-ttu-id="0bccb-255">返回空元组 `()`的可调用不需要 return 语句。</span><span class="sxs-lookup"><span data-stu-id="0bccb-255">A callable that returns an empty tuple, `()`, does not require a return statement.</span></span>
<span data-ttu-id="0bccb-256">如果需要提前退出，可在这种情况下使用 `return ()`。</span><span class="sxs-lookup"><span data-stu-id="0bccb-256">If an early exit is desired, `return ()` may be used in this case.</span></span>
<span data-ttu-id="0bccb-257">返回任何其他类型的 Callables 需要最终的 return 语句。</span><span class="sxs-lookup"><span data-stu-id="0bccb-257">Callables that return any other type require a final return statement.</span></span>

<span data-ttu-id="0bccb-258">操作中不存在最大返回语句数。</span><span class="sxs-lookup"><span data-stu-id="0bccb-258">There is no maximum number of return statements within an operation.</span></span>
<span data-ttu-id="0bccb-259">如果语句在块内跟随 return 语句，则编译器可能会发出警告。</span><span class="sxs-lookup"><span data-stu-id="0bccb-259">The compiler may emit a warning if statements follow a return statement within a block.</span></span>

<span data-ttu-id="0bccb-260">例如，</span><span class="sxs-lookup"><span data-stu-id="0bccb-260">For example,</span></span>

```qsharp
return 1;
```

<span data-ttu-id="0bccb-261">或</span><span class="sxs-lookup"><span data-stu-id="0bccb-261">or</span></span>

```qsharp
return ();
```

<span data-ttu-id="0bccb-262">或</span><span class="sxs-lookup"><span data-stu-id="0bccb-262">or</span></span>

```qsharp
return (results, qubits);
```

### <a name="fail"></a><span data-ttu-id="0bccb-263">Fail</span><span class="sxs-lookup"><span data-stu-id="0bccb-263">Fail</span></span>

<span data-ttu-id="0bccb-264">Fail 语句结束操作的执行，并将错误值返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="0bccb-264">The fail statement ends execution of an operation and returns an error value to the caller.</span></span>
<span data-ttu-id="0bccb-265">它由关键字 `fail`组成，后跟一个字符串和一个终止分号。</span><span class="sxs-lookup"><span data-stu-id="0bccb-265">It consists of the keyword `fail`, followed by a string and a terminating semicolon.</span></span>
<span data-ttu-id="0bccb-266">该字符串返回到传统驱动程序作为错误消息。</span><span class="sxs-lookup"><span data-stu-id="0bccb-266">The string is returned to the classical driver as the error message.</span></span>

<span data-ttu-id="0bccb-267">操作中的 fail 语句数量没有限制。</span><span class="sxs-lookup"><span data-stu-id="0bccb-267">There is no restriction on the number of fail statements within an operation.</span></span>
<span data-ttu-id="0bccb-268">如果语句在块中跟随 fail 语句，则编译器可能会发出警告。</span><span class="sxs-lookup"><span data-stu-id="0bccb-268">The compiler may emit a warning if statements follow a fail statement within a block.</span></span>

<span data-ttu-id="0bccb-269">例如，</span><span class="sxs-lookup"><span data-stu-id="0bccb-269">For example,</span></span>

```qsharp
fail $"Impossible state reached";
```

<span data-ttu-id="0bccb-270">或</span><span class="sxs-lookup"><span data-stu-id="0bccb-270">or</span></span>

```qsharp
fail $"Syndrome {syn} is incorrect";
```

## <a name="qubit-management"></a><span data-ttu-id="0bccb-271">Qubit 管理</span><span class="sxs-lookup"><span data-stu-id="0bccb-271">Qubit Management</span></span>

<span data-ttu-id="0bccb-272">请注意，函数的主体内不允许使用这些语句。</span><span class="sxs-lookup"><span data-stu-id="0bccb-272">Note that none of these statements are allowed within the body of a function.</span></span>
<span data-ttu-id="0bccb-273">它们仅在操作内有效。</span><span class="sxs-lookup"><span data-stu-id="0bccb-273">They are only valid within operations.</span></span>

### <a name="clean-qubits"></a><span data-ttu-id="0bccb-274">清理 Qubits</span><span class="sxs-lookup"><span data-stu-id="0bccb-274">Clean Qubits</span></span>

<span data-ttu-id="0bccb-275">`using` 语句用于获取要在语句块中使用的新 qubits。</span><span class="sxs-lookup"><span data-stu-id="0bccb-275">The `using` statement is used to acquire new qubits for use during a statement block.</span></span>
<span data-ttu-id="0bccb-276">Qubits 可以确保初始化为计算 `Zero` 状态。</span><span class="sxs-lookup"><span data-stu-id="0bccb-276">The qubits are guaranteed to be initialized to the computational `Zero` state.</span></span>
<span data-ttu-id="0bccb-277">Qubits 应处于语句块末尾的计算 `Zero` 状态;鼓励模拟器强制实施此要求。</span><span class="sxs-lookup"><span data-stu-id="0bccb-277">The qubits should be in the computational `Zero` state at the end of the statement block; simulators are encouraged to enforce this.</span></span>

<span data-ttu-id="0bccb-278">语句包含关键字 `using`，后跟左括号 `(`、绑定、右括号 `)`和 qubits 将在其中可用的语句块。</span><span class="sxs-lookup"><span data-stu-id="0bccb-278">The statement consists of the keyword `using`, followed by an open parenthesis `(`, a binding, a close parenthesis `)`, and the statement block within which the qubits will be available.</span></span>
<span data-ttu-id="0bccb-279">绑定遵循与 `let` 语句相同的模式：单个符号或符号的元组，后跟一个等号 `=`，一个值或匹配项的匹配元组。</span><span class="sxs-lookup"><span data-stu-id="0bccb-279">The binding follows the same pattern as `let` statements: either a single symbol or a tuple of symbols, followed by an equals sign `=`, and either a single value or a matching tuple of initializers.</span></span>
<span data-ttu-id="0bccb-280">初始值设定项可用于单个 qubit，指示为 `Qubit()`或 qubits 数组，由 `Qubit[`、`Int` 表达式和 `]`指示。</span><span class="sxs-lookup"><span data-stu-id="0bccb-280">Initializers are available either for a single qubit, indicated as `Qubit()`, or an array of qubits, indicated by `Qubit[`, an `Int` expression, and `]`.</span></span>

<span data-ttu-id="0bccb-281">例如，</span><span class="sxs-lookup"><span data-stu-id="0bccb-281">For example,</span></span>

```qsharp
using (qubit = Qubit()) {
    // ...
}
using ((auxiliary, qubits) = (Qubit(), Qubit[bits * 2 + 3])) {
    // ...
}
```

### <a name="borrowed-qubits"></a><span data-ttu-id="0bccb-282">借用 Qubits</span><span class="sxs-lookup"><span data-stu-id="0bccb-282">Borrowed Qubits</span></span>

<span data-ttu-id="0bccb-283">`borrowing` 语句用于获取临时使用的 qubits。</span><span class="sxs-lookup"><span data-stu-id="0bccb-283">The `borrowing` statement is used to obtain qubits for temporary use.</span></span> <span data-ttu-id="0bccb-284">语句包含关键字 `borrowing`，后跟左括号 `(`、绑定、右括号 `)`和 qubits 将在其中可用的语句块。</span><span class="sxs-lookup"><span data-stu-id="0bccb-284">The statement consists of the keyword `borrowing`, followed by an open parenthesis `(`, a binding, a close parenthesis `)`, and the statement block within which the qubits will be available.</span></span>
<span data-ttu-id="0bccb-285">绑定遵循的模式和规则与 `using` 语句中的相同。</span><span class="sxs-lookup"><span data-stu-id="0bccb-285">The binding follows the same pattern and rules as the one in a `using` statement.</span></span>

<span data-ttu-id="0bccb-286">例如，</span><span class="sxs-lookup"><span data-stu-id="0bccb-286">For example,</span></span>

```qsharp
borrowing (qubit = Qubit()) {
    // ...
}
borrowing ((auxiliary, qubits) = (Qubit(), Qubit[bits * 2 + 3])) {
    // ...
}
```

<span data-ttu-id="0bccb-287">借 qubits 处于未知状态，在语句块结束时超出范围。</span><span class="sxs-lookup"><span data-stu-id="0bccb-287">The borrowed qubits are in an unknown state and go out of scope at the end of the statement block.</span></span>
<span data-ttu-id="0bccb-288">借款人提交 qubits，使其在其被借用时处于相同状态，即，它们在语句块开始和结束时的状态应相同。</span><span class="sxs-lookup"><span data-stu-id="0bccb-288">The borrower commits to leaving the qubits in the same state they were in when they were borrowed, i.e. their state at the beginning and at the end of the statement block is expected to be the same.</span></span>
<span data-ttu-id="0bccb-289">此状态特别不一定是经典状态，因此在大多数情况下，借款范围不应包含度量值。</span><span class="sxs-lookup"><span data-stu-id="0bccb-289">This state in particular is not necessarily a classical state, such that in most cases, borrowing scopes should not contain measurements.</span></span> 

<span data-ttu-id="0bccb-290">有关借用 Svore 使用的示例，请参阅[*使用 2n + 2 qubits 与基于 Toffoli 的模块乘法*](https://arxiv.org/abs/1611.07995)（Haner、Roetteler 和 qubit 2017）进行分解。</span><span class="sxs-lookup"><span data-stu-id="0bccb-290">See [*Factoring using 2n+2 qubits with Toffoli based modular multiplication*](https://arxiv.org/abs/1611.07995) (Haner, Roetteler, and Svore 2017) for an example of borrowed qubit use.</span></span>

<span data-ttu-id="0bccb-291">借用 qubits 时，系统将首先尝试填写正在使用的 qubits 中的请求，但不会在 `borrowing` 语句的主体中访问该请求。</span><span class="sxs-lookup"><span data-stu-id="0bccb-291">When borrowing qubits, the system will first try to fill the request from qubits that are in use but that are not accessed during the body of the `borrowing` statement.</span></span>
<span data-ttu-id="0bccb-292">如果没有足够的 qubits，则它将分配新的 qubits 来完成请求。</span><span class="sxs-lookup"><span data-stu-id="0bccb-292">If there aren't enough such qubits, then it will allocate new qubits to complete the request.</span></span>

## <a name="conjugations"></a><span data-ttu-id="0bccb-293">语态</span><span class="sxs-lookup"><span data-stu-id="0bccb-293">Conjugations</span></span>

<span data-ttu-id="0bccb-294">与传统位相比，释放量程内存会稍微增加一点，因为在 qubits 仍放大时，盲目重置 qubits 可能会对剩余计算产生意外影响。</span><span class="sxs-lookup"><span data-stu-id="0bccb-294">In contrast to classical bits, releasing quantum memory is slightly more involved since blindly resetting qubits can have undesired effects on the remaining computation if the qubits are still entangled.</span></span> <span data-ttu-id="0bccb-295">在释放内存之前，可以通过正确的方式 "撤消" 已执行的计算来避免这种情况。</span><span class="sxs-lookup"><span data-stu-id="0bccb-295">This can be avoided by properly "undoing" performed computations prior to releasing the memory.</span></span> <span data-ttu-id="0bccb-296">量程计算的常见模式如下：</span><span class="sxs-lookup"><span data-stu-id="0bccb-296">A common pattern in quantum computing is hence the following:</span></span> 

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

<span data-ttu-id="0bccb-297">：新增：从0.9 版开始，我们支持语态语句来实现上述转换。</span><span class="sxs-lookup"><span data-stu-id="0bccb-297">:new: Starting with our 0.9 release, we support a conjugation statement that implements the transformation above.</span></span> <span data-ttu-id="0bccb-298">使用该语句，可以通过以下方式实现 `ApplyWith` 操作：</span><span class="sxs-lookup"><span data-stu-id="0bccb-298">Using that statement, the operation `ApplyWith` can be implemented in the following way:</span></span>

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
<span data-ttu-id="0bccb-299">如果外部和内部转换不能像操作那样轻松地提供，则这种语态语句就变得非常有用，但通过多个语句组成的块可以更方便地进行描述。</span><span class="sxs-lookup"><span data-stu-id="0bccb-299">Such a conjugation statement obviously becomes far more useful if the outer and inner transformation are not readily available as operations but are instead more convenient to describe by a block consisting of several statements.</span></span> 

<span data-ttu-id="0bccb-300">在内块中定义的语句的反转换是由编译器自动生成的，并在 apply 块完成后执行。</span><span class="sxs-lookup"><span data-stu-id="0bccb-300">The inverse transformation for the statements defined in the within-block is automatically generated by the compiler and executed after the apply-block completes.</span></span> <span data-ttu-id="0bccb-301">由于不能在 apply 块中重新绑定用作内部块的一部分的任何可变变量，因此，生成的转换将保证为内块中计算的 adjoint。</span><span class="sxs-lookup"><span data-stu-id="0bccb-301">Since any mutable variables used as part of the within-block cannot be rebound in the apply-block, the generated transformation is guaranteed to be the adjoint of the computation in the within-block.</span></span> 

## <a name="expression-evaluation-statements"></a><span data-ttu-id="0bccb-302">表达式计算语句</span><span class="sxs-lookup"><span data-stu-id="0bccb-302">Expression Evaluation Statements</span></span>

<span data-ttu-id="0bccb-303">`Unit` 类型的任何调用表达式都可以用作语句。</span><span class="sxs-lookup"><span data-stu-id="0bccb-303">Any call expression of type `Unit` may be used as a statement.</span></span>
<span data-ttu-id="0bccb-304">这主要用于在 qubits 上调用返回 `Unit` 的操作，因为该语句的用途是修改隐式量程状态。</span><span class="sxs-lookup"><span data-stu-id="0bccb-304">This is primarily of use when calling operations on qubits that return `Unit` because the purpose of the statement is to modify the implicit quantum state.</span></span>
<span data-ttu-id="0bccb-305">表达式计算语句需要终止分号。</span><span class="sxs-lookup"><span data-stu-id="0bccb-305">Expression evaluation statements require a terminating semicolon.</span></span>

<span data-ttu-id="0bccb-306">例如，</span><span class="sxs-lookup"><span data-stu-id="0bccb-306">For example,</span></span>

```qsharp
X(q);
CNOT(control, target);
Adjoint T(q);
```
