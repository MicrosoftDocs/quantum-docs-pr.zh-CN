---
title: 文件结构 |Microsoft Docs
description: 'Q # 文件结构'
author: QuantumWriter
uid: microsoft.quantum.language.file-structure
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 364d353c55bda38f227456909755d13dc7e67080
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76821076"
---
# <a name="file-structure"></a><span data-ttu-id="d0487-103">文件结构</span><span class="sxs-lookup"><span data-stu-id="d0487-103">File Structure</span></span>

<span data-ttu-id="d0487-104">Q # 文件由一系列命名空间声明组成。</span><span class="sxs-lookup"><span data-stu-id="d0487-104">A Q# file consists of a sequence of namespace declarations.</span></span>
<span data-ttu-id="d0487-105">每个命名空间声明都包含用户定义的类型、操作和函数的声明。</span><span class="sxs-lookup"><span data-stu-id="d0487-105">Each namespace declaration contains declarations for user-defined types, operations, and functions.</span></span>
<span data-ttu-id="d0487-106">命名空间声明可以包含任何类型的声明，并按任意顺序包含。</span><span class="sxs-lookup"><span data-stu-id="d0487-106">A namespace declaration may contain any number of each type of declaration, and in any order.</span></span>
<span data-ttu-id="d0487-107">可在命名空间声明之外显示的唯一文本为注释。</span><span class="sxs-lookup"><span data-stu-id="d0487-107">The only text that can appear outside of a namespace declaration is comments.</span></span>
<span data-ttu-id="d0487-108">特别是，命名空间的文档注释位于声明之前。</span><span class="sxs-lookup"><span data-stu-id="d0487-108">In particular, documentation comments for a namespace precede the declaration.</span></span>

## <a name="namespace-declarations"></a><span data-ttu-id="d0487-109">命名空间声明</span><span class="sxs-lookup"><span data-stu-id="d0487-109">Namespace Declarations</span></span>

<span data-ttu-id="d0487-110">Q # 文件通常只包含一个命名空间声明，但可能不包含（且为空或只包含注释）或可能包含多个命名空间。</span><span class="sxs-lookup"><span data-stu-id="d0487-110">A Q# file will typically have exactly one namespace declaration, but may have none (and be empty or just contain comments) or may contain multiple namespaces.</span></span>
<span data-ttu-id="d0487-111">命名空间声明不能嵌套。</span><span class="sxs-lookup"><span data-stu-id="d0487-111">Namespace declarations may not be nested.</span></span>

<span data-ttu-id="d0487-112">同一个命名空间可以在编译在一起的多个 Q # 文件中声明，只要不存在具有相同名称的类型、操作或函数声明。</span><span class="sxs-lookup"><span data-stu-id="d0487-112">The same namespace may be declared in multiple Q# files that are compiled together, as long as there are no type, operation, or function declarations with the same name.</span></span>
<span data-ttu-id="d0487-113">具体而言，在多个文件的同一命名空间中定义同一类型是无效的，即使这些声明相同也是如此。</span><span class="sxs-lookup"><span data-stu-id="d0487-113">In particular, it is invalid to define the same type in the same namespace in multiple files, even if the declarations are identical.</span></span>

<span data-ttu-id="d0487-114">命名空间声明包含关键字 `namespace`，后跟命名空间的名称，左大括号 `{`，命名空间中包含的声明，`}`右大括号。</span><span class="sxs-lookup"><span data-stu-id="d0487-114">A namespace declaration consists of the keyword `namespace`, followed by the name of the namespace, an open brace `{`, the declarations contained in the namespace, and a close brace `}`.</span></span>
<span data-ttu-id="d0487-115">命名空间名称遵循由一个或多个合法符号序列组成的 .NET 模式，`.`用句点分隔。</span><span class="sxs-lookup"><span data-stu-id="d0487-115">Namespace names follow the .NET pattern of a sequence of one or more legal symbols separated by periods `.`.</span></span>
<span data-ttu-id="d0487-116">例如，`MyQuantumStuff` 和 `Microsoft.Quantum.Canon` 是有效的命名空间名称。</span><span class="sxs-lookup"><span data-stu-id="d0487-116">For instance, `MyQuantumStuff` and `Microsoft.Quantum.Canon` are valid namespace names.</span></span>
<span data-ttu-id="d0487-117">按照约定，命名空间名称中的符号采用大写形式，但这不是必需的。</span><span class="sxs-lookup"><span data-stu-id="d0487-117">By convention, the symbols in a namespace name are capitalized, but this is not required.</span></span>

<span data-ttu-id="d0487-118">声明可以在命名空间声明中以任意顺序出现。</span><span class="sxs-lookup"><span data-stu-id="d0487-118">Declarations may appear in any order in a namespace declaration.</span></span>
<span data-ttu-id="d0487-119">已正确解析对文件中的向下声明的类型或 callables 的引用。在引用之前，不需要类型、操作或函数声明。</span><span class="sxs-lookup"><span data-stu-id="d0487-119">References to types or callables declared further down in a file are resolved properly; there is no need for the type, operation, or function declaration to precede a reference to it.</span></span>

## <a name="open-directives"></a><span data-ttu-id="d0487-120">打开指令</span><span class="sxs-lookup"><span data-stu-id="d0487-120">Open Directives</span></span>

<span data-ttu-id="d0487-121">在命名空间块中，可以使用 `open` 指令导入在某个命名空间中定义的所有类型和 callables，并按其非限定名称引用它们。</span><span class="sxs-lookup"><span data-stu-id="d0487-121">Within a namespace block, the `open` directive may be used to import all types and callables defined in a certain namespace and refer to them by their unqualified name.</span></span> 

<span data-ttu-id="d0487-122">此类 `open` 指令包含 `open` 关键字，后跟要打开的命名空间和终止分号。</span><span class="sxs-lookup"><span data-stu-id="d0487-122">Such an `open` directive consists of the `open` keyword, followed by the namespace to be opened and a terminating semicolon.</span></span>

<span data-ttu-id="d0487-123">例如，</span><span class="sxs-lookup"><span data-stu-id="d0487-123">For instance,</span></span>

```qsharp
open Microsoft.Quantum.Canon;
```

<span data-ttu-id="d0487-124">（可选）可定义已打开命名空间的短名称，使来自该命名空间的所有元素都可以（并且需要）由定义的短名称限定。</span><span class="sxs-lookup"><span data-stu-id="d0487-124">Optionally, a short name for the opened namespace may be defined such that all elements from that namespace can (and need) to be qualified by the defined short name.</span></span> <span data-ttu-id="d0487-125">这种短名称是通过在 `open` 指令中的分号前添加关键字 `as` 后跟所需的短名称来定义的：</span><span class="sxs-lookup"><span data-stu-id="d0487-125">Such a short name is defined by adding the keyword `as` followed by the desired short name before the semicolon in an `open` directive:</span></span>

```qsharp
open Microsoft.Quantum.Math as Math;
```

<span data-ttu-id="d0487-126">所有 `open` 指令必须出现在命名空间块中的任何 `function`、`operation`或 `newtype` 声明之前。</span><span class="sxs-lookup"><span data-stu-id="d0487-126">All `open` directives must appear before any `function`, `operation`, or `newtype` declarations in the namespace block.</span></span>
<span data-ttu-id="d0487-127">`open` 指令适用于文件中的整个命名空间块。</span><span class="sxs-lookup"><span data-stu-id="d0487-127">The `open` directive applies to the entire namespace block within a file.</span></span>

## <a name="user-defined-type-declarations"></a><span data-ttu-id="d0487-128">用户定义的类型声明</span><span class="sxs-lookup"><span data-stu-id="d0487-128">User-Defined Type Declarations</span></span>

<span data-ttu-id="d0487-129">Q # 为用户提供了一种声明新的用户定义类型的方法，如 " [Q # 类型模型](xref:microsoft.quantum.language.type-model)" 部分所述。</span><span class="sxs-lookup"><span data-stu-id="d0487-129">Q# provides a way for users to declare new user-defined types, as described in the [Q# type model](xref:microsoft.quantum.language.type-model) section.</span></span>
<span data-ttu-id="d0487-130">即使基类型是相同的，用户定义的类型还是不同的。</span><span class="sxs-lookup"><span data-stu-id="d0487-130">User-defined types are distinct even if the base types are identical.</span></span>
<span data-ttu-id="d0487-131">具体而言，两个用户定义类型的值之间不会自动转换，即使基础类型相同也是如此。</span><span class="sxs-lookup"><span data-stu-id="d0487-131">In particular, there is no automatic conversion between values of two user-defined types even if the underlying types are identical.</span></span>

<span data-ttu-id="d0487-132">用户定义的类型声明包含关键字 `newtype`，后跟用户定义类型的名称、`=`、有效类型规范和终止分号。</span><span class="sxs-lookup"><span data-stu-id="d0487-132">A user-defined type declaration consists of the keyword `newtype`, followed by the name of the user-defined type, an `=`, a valid type specification, and a terminating semicolon.</span></span>

<span data-ttu-id="d0487-133">例如：</span><span class="sxs-lookup"><span data-stu-id="d0487-133">For example:</span></span>

```qsharp
newtype PairOfInts = (Int, Int);
```

<span data-ttu-id="d0487-134">每个 Q # 源文件可以声明任意数量的用户定义类型。</span><span class="sxs-lookup"><span data-stu-id="d0487-134">Each Q# source file may declare any number of user-defined types.</span></span>
<span data-ttu-id="d0487-135">类型名称在命名空间中必须是唯一的，且不能与操作和函数名称冲突。</span><span class="sxs-lookup"><span data-stu-id="d0487-135">Type names must be unique within a namespace and may not conflict with operation and function names.</span></span>

<span data-ttu-id="d0487-136">不能定义用户定义类型之间的循环依赖关系。</span><span class="sxs-lookup"><span data-stu-id="d0487-136">It is not possible to define circular dependencies between user defined types.</span></span> <span data-ttu-id="d0487-137">这样就不能在 Q # 内实现递归类型。</span><span class="sxs-lookup"><span data-stu-id="d0487-137">Recursive types are thus not possible within Q#.</span></span>

## <a name="operation-declarations"></a><span data-ttu-id="d0487-138">操作声明</span><span class="sxs-lookup"><span data-stu-id="d0487-138">Operation Declarations</span></span>

<span data-ttu-id="d0487-139">操作是 Q # 的核心，大致类似于其他语言中的函数。</span><span class="sxs-lookup"><span data-stu-id="d0487-139">Operations are the core of Q#, roughly analogous to functions in other languages.</span></span>
<span data-ttu-id="d0487-140">每个 Q # 源文件可以定义任意数量的操作。</span><span class="sxs-lookup"><span data-stu-id="d0487-140">Each Q# source file may define any number of operations.</span></span>

<span data-ttu-id="d0487-141">操作名称在命名空间中必须是唯一的，并且可能不会与类型和函数名称冲突。</span><span class="sxs-lookup"><span data-stu-id="d0487-141">Operation names must be unique within a namespace and may not conflict with type and function names.</span></span>

<span data-ttu-id="d0487-142">操作声明包含关键字 `operation`，后跟作为操作名称的符号、定义操作的参数的类型化标识符元组、冒号 `:`、描述操作结果类型的类型批注、可以选择具有操作特征的批注、左大括号 `{`、操作声明的正文和最终右大括号 `}`。</span><span class="sxs-lookup"><span data-stu-id="d0487-142">An operation declarations consists of the keyword `operation`, followed by the symbol that is the operation’s name, a typed identifier tuple that defines the arguments to the operation, a colon `:`, a type annotation that describes the operation’s result type, optionally an annotation with the operation characteristics, an open brace `{`, the body of the operation declaration, and a final closing brace `}`.</span></span>

<span data-ttu-id="d0487-143">操作声明的主体既包含默认实现，也包含专用化列表。</span><span class="sxs-lookup"><span data-stu-id="d0487-143">The body of the operation declaration either consists of the default implementation or of a list of specializations.</span></span>
<span data-ttu-id="d0487-144">如果只需显式指定默认的正文专用化的实现，则可以在声明中直接指定默认实现。</span><span class="sxs-lookup"><span data-stu-id="d0487-144">The default implementation can be specified directly within the declaration if only the implementation of the default body specialization needs to specified explicitly.</span></span>
<span data-ttu-id="d0487-145">在这种情况下，声明中具有操作特征的批注非常有用，可确保编译器根据默认实现自动生成其他专用化。</span><span class="sxs-lookup"><span data-stu-id="d0487-145">In this case, an annotation with the operation characteristics in the declaration is useful to ensure that the compiler auto-generates other specializations based on the default implementation.</span></span> 

<span data-ttu-id="d0487-146">例如：</span><span class="sxs-lookup"><span data-stu-id="d0487-146">For example</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```

<span data-ttu-id="d0487-147">操作特征定义哪些类型的函子可以应用于声明的操作以及它们有什么影响。</span><span class="sxs-lookup"><span data-stu-id="d0487-147">Operation characteristics define what kinds of functors can be applied to the declared operation, and what effect they have.</span></span> <span data-ttu-id="d0487-148">如果操作实现了单一转换，则可以定义操作在*adjointed*或*控制*时的行为方式。</span><span class="sxs-lookup"><span data-stu-id="d0487-148">If an operation implements a unitary transformation, then it is possible to define how the operation acts when *adjointed* or *controlled*.</span></span>
<span data-ttu-id="d0487-149">这些专用化的存在可以声明为操作签名的一部分。</span><span class="sxs-lookup"><span data-stu-id="d0487-149">The existence of these specializations can be declared as part of the operation signature.</span></span> <span data-ttu-id="d0487-150">然后，编译器将生成每个此类隐式声明的专用化的相应实现。</span><span class="sxs-lookup"><span data-stu-id="d0487-150">The corresponding implementation for each such implicitly declared specialization is then generated by the compiler.</span></span> <span data-ttu-id="d0487-151">在上面的示例中，编译器将生成一个 adjoint、一个控制的和一个控制的 adjoint 专用化。</span><span class="sxs-lookup"><span data-stu-id="d0487-151">In the example above, an adjoint, a controlled, and a controlled adjoint specialization are generated by the compiler.</span></span> 

<span data-ttu-id="d0487-152">如果编译器无法生成实现，则可以显式指定实现。</span><span class="sxs-lookup"><span data-stu-id="d0487-152">In the case where the implementation cannot be generated by the compiler, it can be explicitly specified.</span></span> <span data-ttu-id="d0487-153">此类显式专用化声明可以包含一个合适的生成指令，该指令阐明如何生成特定专用化或用户定义的实现。</span><span class="sxs-lookup"><span data-stu-id="d0487-153">Such explicit specialization declarations can either consist of a suitable generation directive that clarify how a certain specialization is to be built, or a user defined implementation.</span></span> <span data-ttu-id="d0487-154">例如，上面 `PrepareEntangledPair` 中的代码等效于以下代码，其中包含显式专用化声明：</span><span class="sxs-lookup"><span data-stu-id="d0487-154">The code in `PrepareEntangledPair` above for example is equivalent to the code below containing explicit specialization declarations:</span></span> 

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
<span data-ttu-id="d0487-155">关键字 `auto` 指示编译器应该确定如何生成专用化实现。</span><span class="sxs-lookup"><span data-stu-id="d0487-155">The keyword `auto` indicates that the compiler should determine how to generate the specialization implementation.</span></span>
<span data-ttu-id="d0487-156">如果编译器无法为特定专用化生成实现（如更精确的生成指令），或者如果可以提供更有效的实现，则也可以手动定义该实现。</span><span class="sxs-lookup"><span data-stu-id="d0487-156">If the compiler cannot generate the implementation for a certain specialization without further instructions - like a more precise generation directive -, or if a more efficient implementation can be given, then the implementation may also be manually defined.</span></span>

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

<span data-ttu-id="d0487-157">在上面的示例中，`adjoint invert;` 指示将通过反 `controlled adjoint invert;` 体实现生成 adjoint 专用化，并通过反转受控专用化的给定实现来生成受控 adjoint 专用化。</span><span class="sxs-lookup"><span data-stu-id="d0487-157">In the example above, `adjoint invert;` indicates that the adjoint specialization is to be generated by inverting the body implementation, and `controlled adjoint invert;` indicates that the controlled adjoint specialization is to be generated by inverting the given implementation of the controlled specialization.</span></span>

<span data-ttu-id="d0487-158">对于支持 `Adjoint` 和/或 `Controlled` 函子应用程序的操作，必须 `Unit`其返回类型。</span><span class="sxs-lookup"><span data-stu-id="d0487-158">For an operation to support application of the `Adjoint` and/or `Controlled` functor, its return type necessarily needs to be `Unit`.</span></span> 


### <a name="explicit-specialization-declarations"></a><span data-ttu-id="d0487-159">显式专用化声明</span><span class="sxs-lookup"><span data-stu-id="d0487-159">Explicit Specialization Declarations</span></span>

<span data-ttu-id="d0487-160">Q # 操作可能包含以下显式专用化声明：</span><span class="sxs-lookup"><span data-stu-id="d0487-160">Q# operations may contain the following explicit specialization declarations:</span></span>

- <span data-ttu-id="d0487-161">`body` 特殊化指定了在未应用函子的情况中实现操作。</span><span class="sxs-lookup"><span data-stu-id="d0487-161">The `body` specialization specifies the implementation of the operation with no functors applied.</span></span>
- <span data-ttu-id="d0487-162">`adjoint` 特殊化指定应用了 `Adjoint` 函子的操作的实现。</span><span class="sxs-lookup"><span data-stu-id="d0487-162">The `adjoint` specialization specifies the implementation of the operation with the `Adjoint` functor applied.</span></span>
- <span data-ttu-id="d0487-163">`controlled` 特殊化指定应用了 `Controlled` 函子的操作的实现。</span><span class="sxs-lookup"><span data-stu-id="d0487-163">The `controlled` specialization specifies the implementation of the operation with the `Controlled` functor applied.</span></span>
- <span data-ttu-id="d0487-164">`controlled adjoint` 专用化通过应用的 `Adjoint` 和 `Controlled` 指定操作的实现。</span><span class="sxs-lookup"><span data-stu-id="d0487-164">The `controlled adjoint` specialization specifies the implementation of the operation with both the `Adjoint` and `Controlled` functors applied.</span></span>
  <span data-ttu-id="d0487-165">这种特殊化还可以命名为 `adjoint controlled`，因为这两个函子。</span><span class="sxs-lookup"><span data-stu-id="d0487-165">This specialization can also be named `adjoint controlled`, since the two functors commute.</span></span>


<span data-ttu-id="d0487-166">操作特殊化包含专业化标记（如 `body`、`adjoint`等），后跟以下其中之一：</span><span class="sxs-lookup"><span data-stu-id="d0487-166">An operation specialization consists of the specialization tag (like e.g. `body`, or `adjoint`, etc.) followed by one of:</span></span>

- <span data-ttu-id="d0487-167">如下所述的显式声明。</span><span class="sxs-lookup"><span data-stu-id="d0487-167">An explicit declaration as described below.</span></span>
- <span data-ttu-id="d0487-168">告诉编译器如何生成专用化的指令，可以是：</span><span class="sxs-lookup"><span data-stu-id="d0487-168">A directive that tells the compiler how to generate the specialization, one of:</span></span>
  - <span data-ttu-id="d0487-169">`intrinsic`，指示目标计算机提供专用化。</span><span class="sxs-lookup"><span data-stu-id="d0487-169">`intrinsic`, which indicates that the specialization is provided by the target machine.</span></span>
  - <span data-ttu-id="d0487-170">`distribute`，可与 `controlled` 和 `controlled adjoint` 专用化一起使用。</span><span class="sxs-lookup"><span data-stu-id="d0487-170">`distribute`, which may be used with the `controlled` and `controlled adjoint` specializations.</span></span>
    <span data-ttu-id="d0487-171">与 `controlled`一起使用时，它指示编译器应通过将 `Controlled` 应用到 `body`中的所有操作来计算特殊化。</span><span class="sxs-lookup"><span data-stu-id="d0487-171">When used with `controlled`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `body`.</span></span>
    <span data-ttu-id="d0487-172">与 `controlled adjoint`一起使用时，它指示编译器应通过将 `Controlled` 应用到 `adjoint` 专用化中的所有操作来计算特殊化。</span><span class="sxs-lookup"><span data-stu-id="d0487-172">When used with `controlled adjoint`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `adjoint` specialization.</span></span>
  - <span data-ttu-id="d0487-173">`invert`，它指示编译器应通过反序列化 `body`来计算 `adjoint` 特殊化，即反向运算的顺序并将 adjoint 应用于每个操作。</span><span class="sxs-lookup"><span data-stu-id="d0487-173">`invert`, which indicates that the compiler should compute the `adjoint` specialization by inverting the `body`, i.e. reversing the order of operations and applying the adjoint to each one.</span></span>
    <span data-ttu-id="d0487-174">与 `adjoint controlled`一起使用时，它指示编译器应通过反转 `controlled` 专用化来计算特殊化。</span><span class="sxs-lookup"><span data-stu-id="d0487-174">When used with `adjoint controlled`, this indicates that the compiler should compute the specialization by inverting the `controlled` specialization.</span></span>
  - <span data-ttu-id="d0487-175">`self`，指示 adjoint 特殊化与 `body` 特殊化相同。</span><span class="sxs-lookup"><span data-stu-id="d0487-175">`self`, to indicate that the adjoint specialization is the the same as the `body` specialization.</span></span>
    <span data-ttu-id="d0487-176">这对于 `adjoint` 和 `adjoint controlled` 专用化是合法的。</span><span class="sxs-lookup"><span data-stu-id="d0487-176">This is legal for the `adjoint` and `adjoint controlled` specializations.</span></span>
    <span data-ttu-id="d0487-177">对于 `adjoint controlled`，`self` 意味着 `adjoint controlled` 专用化与 `controlled` 特殊化相同。</span><span class="sxs-lookup"><span data-stu-id="d0487-177">For `adjoint controlled`, `self` implies that the `adjoint controlled` specialization is the same as the `controlled` specialization.</span></span>
  - <span data-ttu-id="d0487-178">`auto`，指示编译器应选择要应用的适当指令。</span><span class="sxs-lookup"><span data-stu-id="d0487-178">`auto`, to indicate that the compiler should select an appropriate directive to apply.</span></span>
    <span data-ttu-id="d0487-179">`auto` 不能用于 `body` 专用化。</span><span class="sxs-lookup"><span data-stu-id="d0487-179">`auto` may not be used for the `body` specialization.</span></span>

<span data-ttu-id="d0487-180">指令和 `auto` 都需要右半冒号 `;`。</span><span class="sxs-lookup"><span data-stu-id="d0487-180">The directives and `auto` all require a closing semi-colon `;`.</span></span>
<span data-ttu-id="d0487-181">如果提供了 `body` 的显式声明，则 `auto` 指令可解析为以下生成指令：</span><span class="sxs-lookup"><span data-stu-id="d0487-181">The `auto` directive resolves to the following generation directive if an explicit declaration of the `body` is provided:</span></span>

- <span data-ttu-id="d0487-182">`adjoint` 专用化是根据指令 `invert`生成的。</span><span class="sxs-lookup"><span data-stu-id="d0487-182">The `adjoint` specialization is generated according to the directive `invert`.</span></span>
- <span data-ttu-id="d0487-183">`controlled` 专用化是根据指令 `distribute`生成的。</span><span class="sxs-lookup"><span data-stu-id="d0487-183">The `controlled` specialization is generated according to the directive `distribute`.</span></span>
- <span data-ttu-id="d0487-184">`adjoint controlled` 专用化是根据指令生成的 `invert` 如果为 `controlled` 提供了显式声明，但没有为 `adjoint`提供一个，则为，否则为 `distribute`。</span><span class="sxs-lookup"><span data-stu-id="d0487-184">The `adjoint controlled` specialization is generated according to the directive `invert` if an explicit declaration for `controlled` is given but not one for `adjoint`, and `distribute` otherwise.</span></span>

> [!TIP]   
> <span data-ttu-id="d0487-185">如果操作是自我 adjoint 的，则通过 `self` 生成指令显式指定 adjoint 或受控 adjoint 特殊化，以允许编译器使用该信息进行优化。</span><span class="sxs-lookup"><span data-stu-id="d0487-185">If an operation is self-adjoint, explicitly specify either the adjoint or the controlled adjoint specialization via the generation directive `self` to allow the compiler to make use of that information for optimization purposes.</span></span>

<span data-ttu-id="d0487-186">包含用户定义的实现的专用化声明包含一个参数元组，后面跟有用于实现专用化的 Q # 代码的语句块。</span><span class="sxs-lookup"><span data-stu-id="d0487-186">A specialization declaration containing a user defined implementation consists of an argument tuple followed by a statement block with the Q# code that implements the specialization.</span></span>
<span data-ttu-id="d0487-187">在参数列表中，`...` 用于表示作为一个整体为操作声明的参数。</span><span class="sxs-lookup"><span data-stu-id="d0487-187">In the argument list, `...` is used to represent the arguments declared for the operation as a whole.</span></span>
<span data-ttu-id="d0487-188">对于 `body` 和 `adjoint`，应始终 `(...)`参数列表;对于 `controlled` 和 `adjoint controlled`，参数列表应为表示控件 qubits 数组的符号，后跟 `...`，并用括号括起来。例如，`(controls,...)`。</span><span class="sxs-lookup"><span data-stu-id="d0487-188">For `body` and `adjoint`, the argument list should always be `(...)`; for `controlled` and `adjoint controlled`, the argument list should be a symbol that represents the array of control qubits, followed by `...`, enclosed in parentheses; for example, `(controls,...)`.</span></span>

<span data-ttu-id="d0487-189">如果需要显式声明默认正文之外的一个或多个特殊化，则默认体的实现也需要包装到适当的专用化声明中：</span><span class="sxs-lookup"><span data-stu-id="d0487-189">If one or more specializations besides the default body need to be explicitly declared, then the implementation for the default body needs to be wrapped into a suitable specialization declaration as well:</span></span>

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

### <a name="adjoint"></a><span data-ttu-id="d0487-190">Adjoint</span><span class="sxs-lookup"><span data-stu-id="d0487-190">Adjoint</span></span>

<span data-ttu-id="d0487-191">操作的 adjoint 指定如何实现该操作的复杂共轭转置，即 "反向运行" 操作的操作方式。</span><span class="sxs-lookup"><span data-stu-id="d0487-191">The adjoint of an operation specifies how the complex conjugate transpose of the operation is implemented, i.e. how the operation acts when "run in reverse".</span></span>
<span data-ttu-id="d0487-192">指定一个不带 adjoint 的操作是合法的;例如，测量操作没有 adjoint，因为它们不可逆。</span><span class="sxs-lookup"><span data-stu-id="d0487-192">It is legal to specify an operation with no adjoint; for instance, measurement operations have no adjoint because they are not invertible.</span></span>
<span data-ttu-id="d0487-193">如果操作的声明包含 adjoint 专用化的隐式或显式声明，则该操作支持 `Adjoint` 的函子。</span><span class="sxs-lookup"><span data-stu-id="d0487-193">An operation supports the `Adjoint` functor if its declaration contains an implicit or explicit declaration of an adjoint specialization.</span></span>
<span data-ttu-id="d0487-194">显式声明的受控 adjoint 专用化意味着存在 adjoint 专用化。</span><span class="sxs-lookup"><span data-stu-id="d0487-194">An explicitly declared controlled adjoint specialization implies the existence of an adjoint specialization.</span></span> 

<span data-ttu-id="d0487-195">对于其正文包含重复截止时间循环、set 语句、度量、return 语句或对不支持 `Adjoint` 函子的其他操作的操作，如果不可能，请遵循 `invert` 或 `auto` 指令自动生成 adjoint 特殊化。</span><span class="sxs-lookup"><span data-stu-id="d0487-195">For operation whose body contains repeat-until-success loops, set statements, measurements, return statements, or calls to other operations that do not support the `Adjoint` functor, auto-generating an adjoint specialization following the `invert` or `auto` directive is not possible.</span></span>

### <a name="controlled"></a><span data-ttu-id="d0487-196">操控</span><span class="sxs-lookup"><span data-stu-id="d0487-196">Controlled</span></span>

<span data-ttu-id="d0487-197">操作的受控版本指定如何实现该操作的量程控制版本，即，在应用于量程寄存器状态时操作的行为方式。</span><span class="sxs-lookup"><span data-stu-id="d0487-197">The controlled version of an operation specifies how a quantum-controlled version of the operation is implemented, i.e. how an operation acts when applied conditioned on the state of a quantum register.</span></span>
<span data-ttu-id="d0487-198">[受控](xref:microsoft.quantum.language.type-model#controlled)部分提供了更完整的说明。</span><span class="sxs-lookup"><span data-stu-id="d0487-198">A more complete description is provided in the [Controlled](xref:microsoft.quantum.language.type-model#controlled) section.</span></span>

<span data-ttu-id="d0487-199">指定没有受控版本的操作是合法的;例如，由于不能控制度量操作，因此它没有受控版本。</span><span class="sxs-lookup"><span data-stu-id="d0487-199">It is legal to specify an operation with no controlled version; for instance, measurement operations have no controlled version because they are not controllable.</span></span>
<span data-ttu-id="d0487-200">当且仅当其声明包含受控专用化的隐式或显式声明时，操作才支持 `Controlled` 的函子。</span><span class="sxs-lookup"><span data-stu-id="d0487-200">An operation supports the `Controlled` functor if and only if its declaration contains an implicit or explicit declaration of a controlled specialization.</span></span>
<span data-ttu-id="d0487-201">显式声明的受控 adjoint 专用化意味着存在受控的专用化。</span><span class="sxs-lookup"><span data-stu-id="d0487-201">An explicitly declared controlled adjoint specialization implies the existence of a controlled specialization.</span></span> 

<span data-ttu-id="d0487-202">对于其正文包含对不支持 `Controlled` 函子的其他操作的调用的操作，无法在 `distribute` 或 `auto` 指令后自动生成受控专用化。</span><span class="sxs-lookup"><span data-stu-id="d0487-202">For an operation whose body contains calls to other operations that does not support the `Controlled` functor, auto-generating a controlled specialization following the `distribute` or `auto` directive is not possible.</span></span>

### <a name="controlled-adjoint"></a><span data-ttu-id="d0487-203">受控 Adjoint</span><span class="sxs-lookup"><span data-stu-id="d0487-203">Controlled Adjoint</span></span>

<span data-ttu-id="d0487-204">操作的受控 adjoint 版本指定如何实现该操作的 adjoint 的量程控制版本。</span><span class="sxs-lookup"><span data-stu-id="d0487-204">The controlled adjoint version of an operation specifies how a quantum-controlled version of the adjoint of the operation is implemented.</span></span>
<span data-ttu-id="d0487-205">指定不具有受控 adjoint 版本的操作是合法的;例如，度量操作没有受控的 adjoint 版本，因为它们既不能控制也不可逆。</span><span class="sxs-lookup"><span data-stu-id="d0487-205">It is legal to specify an operation with no controlled adjoint version; for instance, measurement operations have no controlled adjoint version because they are neither controllable nor invertible.</span></span>

<span data-ttu-id="d0487-206">当且仅当存在 adjoint 和受控专用化时，操作的受控 adjoint 专用化才需要存在。</span><span class="sxs-lookup"><span data-stu-id="d0487-206">A controlled adjoint specialization for an operation needs to exist if and only if both an adjoint and a controlled specialization exist.</span></span> <span data-ttu-id="d0487-207">在这种情况下，如果未显式定义实现，则会推断出受控 adjoint 专用化的存在，并由编译器生成合适的专用化。</span><span class="sxs-lookup"><span data-stu-id="d0487-207">In that case, the existence of the controlled adjoint specialization is inferred and an appropriate specialization is generated by the compiler if no implementation has been defined explicitly.</span></span> 

<span data-ttu-id="d0487-208">对于其正文包含对没有受控 adjoint 版本的其他操作的调用的操作，无法在 `invert`后自动生成 adjoint 特殊化，`distribute` 或 `auto` 指令。</span><span class="sxs-lookup"><span data-stu-id="d0487-208">For an operation whose body contains calls to other operations that do not have a controlled adjoint version, auto-generating an adjoint specialization following the `invert`, `distribute` or `auto` directive is not possible.</span></span>


### <a name="examples"></a><span data-ttu-id="d0487-209">示例</span><span class="sxs-lookup"><span data-stu-id="d0487-209">Examples</span></span>

<span data-ttu-id="d0487-210">操作声明可能非常简单，如下所示：定义基元 Pauli X 操作：</span><span class="sxs-lookup"><span data-stu-id="d0487-210">An operation declaration might be as simple as the following, which defines the primitive Pauli X operation:</span></span>

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```

<span data-ttu-id="d0487-211">下面定义了传送操作。</span><span class="sxs-lookup"><span data-stu-id="d0487-211">The following defines the teleport operation.</span></span>

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

## <a name="function-declarations"></a><span data-ttu-id="d0487-212">函数声明</span><span class="sxs-lookup"><span data-stu-id="d0487-212">Function Declarations</span></span>

<span data-ttu-id="d0487-213">函数是 Q # 中纯传统例程。</span><span class="sxs-lookup"><span data-stu-id="d0487-213">Functions are purely classical routines in Q#.</span></span>
<span data-ttu-id="d0487-214">每个 Q # 源文件可以定义任意数量的函数。</span><span class="sxs-lookup"><span data-stu-id="d0487-214">Each Q# source file may define any number of functions.</span></span>

<span data-ttu-id="d0487-215">函数声明包含关键字 `function`，后跟作为函数名称的符号、类型化标识符元组、描述函数的返回类型的类型批注以及描述函数实现的语句块。</span><span class="sxs-lookup"><span data-stu-id="d0487-215">A function declaration consists of the keyword `function`, followed by the symbol that is the function’s name, a typed identifier tuple, a type annotation that describes the function's return type, and a statement block that describes the implementation of the function.</span></span>

<span data-ttu-id="d0487-216">定义函数的语句块必须与任何其他语句块 `{` 和 `}` 括起来。</span><span class="sxs-lookup"><span data-stu-id="d0487-216">The statement block defining a function must be enclosed in `{` and `}` like any other statement block.</span></span>

<span data-ttu-id="d0487-217">函数名称在命名空间中必须是唯一的，且不能与操作和类型名称冲突。</span><span class="sxs-lookup"><span data-stu-id="d0487-217">Function names must be unique within a namespace and may not conflict with operation and type names.</span></span>
<span data-ttu-id="d0487-218">函数不能分配或借用 qubits 或调用操作。</span><span class="sxs-lookup"><span data-stu-id="d0487-218">Functions may not allocate or borrow qubits, or call operations.</span></span> <span data-ttu-id="d0487-219">操作的部分应用或按操作类型化值的方法很好。</span><span class="sxs-lookup"><span data-stu-id="d0487-219">Partial application of operations or passing around operation typed values is fine.</span></span>

<span data-ttu-id="d0487-220">例如，</span><span class="sxs-lookup"><span data-stu-id="d0487-220">For example,</span></span>

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
