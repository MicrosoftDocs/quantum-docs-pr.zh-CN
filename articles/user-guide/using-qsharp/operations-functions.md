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
# <a name="operations-and-functions-in-no-locq"></a><span data-ttu-id="564f1-103">中的操作和函数Q#</span><span class="sxs-lookup"><span data-stu-id="564f1-103">Operations and Functions in Q#</span></span>

## <a name="defining-new-operations"></a><span data-ttu-id="564f1-104">定义新操作</span><span class="sxs-lookup"><span data-stu-id="564f1-104">Defining New Operations</span></span>

<span data-ttu-id="564f1-105">操作是的核心 Q# 。</span><span class="sxs-lookup"><span data-stu-id="564f1-105">Operations are the core of Q#.</span></span>
<span data-ttu-id="564f1-106">声明后，可以从传统的 .NET 应用程序调用它们，例如，使用模拟器或内的其他操作 Q# 。</span><span class="sxs-lookup"><span data-stu-id="564f1-106">Once declared, they can either be called from classical .NET applications, for example, using a simulator or by other operations within Q#.</span></span>
<span data-ttu-id="564f1-107">在中定义的每个操作 Q# 都可以调用任意数量的其他操作，包括由语言定义的内置内部操作。</span><span class="sxs-lookup"><span data-stu-id="564f1-107">Each operation defined in Q# can call any number of other operations, including the built-in intrinsic operations defined by the language.</span></span> <span data-ttu-id="564f1-108">Q#定义这些内部操作的特定方式取决于目标计算机。</span><span class="sxs-lookup"><span data-stu-id="564f1-108">The particular way in which Q# defines these intrinsic operations depends on the target machine.</span></span>
<span data-ttu-id="564f1-109">在编译时，每个操作都表示为可提供给目标计算机的 .NET 类类型。</span><span class="sxs-lookup"><span data-stu-id="564f1-109">When compiled, each operation is represented as a .NET class type that can be provided to target machines.</span></span>

<span data-ttu-id="564f1-110">每个 Q# 源文件都可以定义任意数量的操作。</span><span class="sxs-lookup"><span data-stu-id="564f1-110">Each Q# source file can define any number of operations.</span></span>
<span data-ttu-id="564f1-111">操作名称在命名空间中必须唯一，并且不能与类型或函数名冲突。</span><span class="sxs-lookup"><span data-stu-id="564f1-111">Operation names must be unique within a namespace and can not conflict with type or function names.</span></span>

<span data-ttu-id="564f1-112">操作声明由关键字组成 `operation` ，后跟作为操作名称的符号、定义操作参数的类型化标识符元组、冒号 `:` 、描述操作结果类型的类型批注，还可以是包含操作特征的批注、左大括号和操作声明的正文（括在大括号中） `{ }` 。</span><span class="sxs-lookup"><span data-stu-id="564f1-112">An operation declaration consists of the keyword `operation`, followed by the symbol that is the operation's name, a typed identifier tuple that defines the arguments to the operation, a colon `:`, a type annotation that describes the operation's result type, optionally an annotation with the operation characteristics, an open brace, and then the body of the operation declaration, enclosed in braces `{ }`.</span></span>

<span data-ttu-id="564f1-113">每个操作都使用一个输入，生成一个输出，并为一个或多个专用操作指定实现。</span><span class="sxs-lookup"><span data-stu-id="564f1-113">Each operation takes an input, produces an output, and specifies the implementation for one or more operation specializations.</span></span>
<span data-ttu-id="564f1-114">本文的不同部分详细说明了可能的专用化，以及如何定义和调用它们。</span><span class="sxs-lookup"><span data-stu-id="564f1-114">The possible specializations, and how to define and call them, are detailed in the different sections of this article.</span></span>
<span data-ttu-id="564f1-115">现在，请考虑以下操作，该操作仅定义默认的主体特殊化并使用单个 qubit 作为其输入，然后对 <xref:microsoft.quantum.intrinsic.x> 该输入调用内置操作：</span><span class="sxs-lookup"><span data-stu-id="564f1-115">For now, consider the following operation, which defines only a default body specialization and takes a single qubit as its input, then calls the built-in <xref:microsoft.quantum.intrinsic.x> operation on that input:</span></span>

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

<span data-ttu-id="564f1-116">关键字 `operation` 开始操作定义，后跟名称; 此处为 `BitFlip` 。</span><span class="sxs-lookup"><span data-stu-id="564f1-116">The keyword `operation` begins the operation definition, followed by the name; here, `BitFlip`.</span></span>
<span data-ttu-id="564f1-117">接下来，定义输入类型 (`Qubit`) ，以及 `target` 用于引用新操作中的输入的名称。</span><span class="sxs-lookup"><span data-stu-id="564f1-117">Next, the type of input is defined (`Qubit`), along with a name, `target`, for referring to the input within the new operation.</span></span>
<span data-ttu-id="564f1-118">最后， `Unit` 定义操作的输出为空。</span><span class="sxs-lookup"><span data-stu-id="564f1-118">Lastly, `Unit` defines that the operation's output is empty.</span></span>
<span data-ttu-id="564f1-119">`Unit``void`在 c # 和其他命令式语言中使用方式类似，并且等效于 `unit` F # 和其他功能语言。</span><span class="sxs-lookup"><span data-stu-id="564f1-119">`Unit` is used similarly to `void` in C# and other imperative languages and is equivalent to `unit` in F# and other functional languages.</span></span>

<span data-ttu-id="564f1-120">操作还可以返回比更有趣 `Unit` 的类型。</span><span class="sxs-lookup"><span data-stu-id="564f1-120">Operations can also return more interesting types than `Unit`.</span></span>
<span data-ttu-id="564f1-121">例如， <xref:microsoft.quantum.intrinsic.m> 操作返回类型的输出，该输出 `Result` 表示已执行了一个度量值。</span><span class="sxs-lookup"><span data-stu-id="564f1-121">For instance, the <xref:microsoft.quantum.intrinsic.m> operation returns an output of type `Result`, representing having performed a measurement.</span></span>  <span data-ttu-id="564f1-122">可以将其从操作传递到另一个操作，或将其与 `let` 关键字一起使用来定义新变量。</span><span class="sxs-lookup"><span data-stu-id="564f1-122">You can pass it from an operation to another operation or use it with the `let` keyword to define a new variable.</span></span>

<span data-ttu-id="564f1-123">此方法允许表示在较低级别与量程操作交互的传统计算，如[superdense 编码](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding)：</span><span class="sxs-lookup"><span data-stu-id="564f1-123">This approach allows for representing classical computation that interacts with quantum operations at a low level, such as in [superdense coding](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding):</span></span>

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
> <span data-ttu-id="564f1-124">中的每个操作 Q# 都只采用一个输入，并只返回一个输出。</span><span class="sxs-lookup"><span data-stu-id="564f1-124">Each operation in Q# takes exactly one input and returns exactly one output.</span></span>
> <span data-ttu-id="564f1-125">多个输入和输出使用元组表示，这些*元组*将多个值一起收集到单个值中。</span><span class="sxs-lookup"><span data-stu-id="564f1-125">Multiple inputs and outputs are represented using *tuples*, which collect multiple values together into a single value.</span></span>
> <span data-ttu-id="564f1-126">在这种情况下， Q# 是 "元组" 语言。</span><span class="sxs-lookup"><span data-stu-id="564f1-126">In this regard, Q# is a "tuple-in tuple-out" language.</span></span>
> <span data-ttu-id="564f1-127">按照此概念，应将一组空括号 `()` 作为 "empty" 元组（类型为）进行读取 `Unit` 。</span><span class="sxs-lookup"><span data-stu-id="564f1-127">Following this concept, a set of empty parentheses, `()`, should then be read as the "empty" tuple, which has the type `Unit`.</span></span>

## <a name="controlled-and-adjoint-operations"></a><span data-ttu-id="564f1-128">受控和 Adjoint 操作</span><span class="sxs-lookup"><span data-stu-id="564f1-128">Controlled and Adjoint Operations</span></span>

<span data-ttu-id="564f1-129">如果操作实现了单一转换，就像在中执行许多操作一样 Q# ，然后可以定义操作在*adjointed*或*控制*时的行为方式。</span><span class="sxs-lookup"><span data-stu-id="564f1-129">If an operation implements a unitary transformation, as is the case for many operations in Q#, then it is possible to define how the operation acts when *adjointed* or *controlled*.</span></span> <span data-ttu-id="564f1-130">操作的*adjoint*专用化指定操作的 "反转" 的行为方式，而*受控*专用化指定操作在其应用程序的应用程序在特定量程寄存器状态下运行时的行为方式。</span><span class="sxs-lookup"><span data-stu-id="564f1-130">An *adjoint* specialization of an operation specifies how the "inverse" of the operation acts, while a *controlled* specialization specifies how an operation acts when its application is conditioned on the state of a particular quantum register.</span></span>

<span data-ttu-id="564f1-131">量程操作的 Adjoints 对量程计算的许多方面都至关重要。</span><span class="sxs-lookup"><span data-stu-id="564f1-131">Adjoints of quantum operations are crucial to many aspects of quantum computing.</span></span> <span data-ttu-id="564f1-132">有关在一种有用的编程技术中讨论的这种情况的示例 Q# ，请参阅本文中的[语态](#conjugations)。</span><span class="sxs-lookup"><span data-stu-id="564f1-132">For an example of one such situation discussed alongside a useful Q# programming technique, see [Conjugations](#conjugations) in this article.</span></span> 

<span data-ttu-id="564f1-133">操作的受控版本是新操作，仅当所有控件 qubits 都处于指定状态时，才会有效地应用基本操作。</span><span class="sxs-lookup"><span data-stu-id="564f1-133">The controlled version of an operation is a new operation that effectively applies the base operation only if all of the control qubits are in a specified state.</span></span>
<span data-ttu-id="564f1-134">如果控件 qubits 在 superposition 中，则会将基本操作一致应用到 superposition 的相应部分。</span><span class="sxs-lookup"><span data-stu-id="564f1-134">If the control qubits are in superposition, then the base operation is applied coherently to the appropriate part of the superposition.</span></span>
<span data-ttu-id="564f1-135">因此，受控操作通常用于生成牵连。</span><span class="sxs-lookup"><span data-stu-id="564f1-135">Thus, controlled operations are often used to generate entanglement.</span></span>

<span data-ttu-id="564f1-136">当然，还可以使用*受控的 adjoint*特殊化来指定操作 adjoint 的受控应用。</span><span class="sxs-lookup"><span data-stu-id="564f1-136">Naturally, a *controlled adjoint* specialization could exist as well, specifying the controlled application of an operation's adjoint.</span></span>

> [!NOTE]
> <span data-ttu-id="564f1-137">如果 $U $ 是操作实现的单一转换 `U` ，则 `Adjoint U` 表示 $U ^ \dagger $ 的单一转换，这是复杂的共轭转置。</span><span class="sxs-lookup"><span data-stu-id="564f1-137">If $U$ is the unitary transformation implemented by an operation `U`, then `Adjoint U` represents the unitary transformation $U^\dagger$, which is the complex conjugate transpose.</span></span>
> <span data-ttu-id="564f1-138">依次应用某一操作，然后将其 adjoint 的状态保持不变，如 $UU ^ \dagger = U ^ \dagger U = \id $，则为恒等矩阵。</span><span class="sxs-lookup"><span data-stu-id="564f1-138">Successively applying an operation and then its adjoint to a state leaves the state unchanged, as illustrated by the fact that $UU^\dagger = U^\dagger U = \id$, the identity matrix.</span></span>
> <span data-ttu-id="564f1-139">受控操作的单一表示形式略微微妙，但可以在量程计算概念中找到更多详细信息[：多个 qubits](xref:microsoft.quantum.concepts.multiple-qubits)。</span><span class="sxs-lookup"><span data-stu-id="564f1-139">The unitary representation of a controlled operation is slightly more nuanced, but you can find more details at [Quantum computing concepts: multiple qubits](xref:microsoft.quantum.concepts.multiple-qubits).</span></span>

<span data-ttu-id="564f1-140">以下部分介绍如何在代码中调用这些不同的专用化 Q# ，以及如何定义操作来支持它们。</span><span class="sxs-lookup"><span data-stu-id="564f1-140">The following section describes how to call these various specializations in your Q# code, and how to define operations to support them.</span></span>

### <a name="calling-operation-specializations"></a><span data-ttu-id="564f1-141">调用专用操作</span><span class="sxs-lookup"><span data-stu-id="564f1-141">Calling operation specializations</span></span>

<span data-ttu-id="564f1-142">中*functor*的函子 Q# 是一个工厂，它定义了其他操作的新操作。</span><span class="sxs-lookup"><span data-stu-id="564f1-142">A *functor* in Q# is a factory that defines a new operation from another operation.</span></span>
<span data-ttu-id="564f1-143">中的两个标准函子 Q# 是 `Adjoint` 和 `Controlled` 。</span><span class="sxs-lookup"><span data-stu-id="564f1-143">The two standard functors in Q# are `Adjoint` and `Controlled`.</span></span>

<span data-ttu-id="564f1-144">在定义新操作的实现时，函子有权访问基操作的实现。</span><span class="sxs-lookup"><span data-stu-id="564f1-144">Functors have access to the implementation of the base operation when defining the implementation of the new operation.</span></span>
<span data-ttu-id="564f1-145">因此，函子可以比传统的高级函数执行更复杂的功能。</span><span class="sxs-lookup"><span data-stu-id="564f1-145">Thus, functors can perform more complex functions than traditional higher-level functions.</span></span> <span data-ttu-id="564f1-146">函子在类型系统中没有表示形式 Q# 。</span><span class="sxs-lookup"><span data-stu-id="564f1-146">Functors do not have a representation in the Q# type system.</span></span> <span data-ttu-id="564f1-147">因此，目前不可能将其绑定到变量或将其作为参数传递。</span><span class="sxs-lookup"><span data-stu-id="564f1-147">It is thus currently not possible to bind them to a variable or pass them as arguments.</span></span> 

<span data-ttu-id="564f1-148">通过将函子应用到操作来使用该操作，该操作将返回一个新操作。</span><span class="sxs-lookup"><span data-stu-id="564f1-148">Use a functor by applying it to an operation, which returns a new operation.</span></span>
<span data-ttu-id="564f1-149">例如，将函子应用 `Adjoint` 到操作会 `Y` 返回新操作 `Adjoint Y` 。</span><span class="sxs-lookup"><span data-stu-id="564f1-149">For example, applying the `Adjoint` functor to the `Y` operation returns the new operation `Adjoint Y`.</span></span> <span data-ttu-id="564f1-150">可以像调用任何其他操作一样调用新操作。</span><span class="sxs-lookup"><span data-stu-id="564f1-150">You can invoke the new operation like any other operation.</span></span>
<span data-ttu-id="564f1-151">对于支持或函子应用程序的操作 `Adjoint` `Controlled` ，其返回类型必须为 `Unit` 。</span><span class="sxs-lookup"><span data-stu-id="564f1-151">For an operation to support the application of the `Adjoint` or `Controlled` functors, its return type necessarily needs to be `Unit`.</span></span> 

#### <a name="adjoint-functor"></a><span data-ttu-id="564f1-152">`Adjoint`函子</span><span class="sxs-lookup"><span data-stu-id="564f1-152">`Adjoint` functor</span></span>

<span data-ttu-id="564f1-153">因此， `Adjoint Y(q1)` 会将 `Adjoint` 函子应用到 `Y` 操作以生成新的操作，并将该新操作应用于 `q1` 。</span><span class="sxs-lookup"><span data-stu-id="564f1-153">Thus, `Adjoint Y(q1)` applies the `Adjoint` functor to the `Y` operation to generate a new operation, and applies that new operation to `q1`.</span></span>
<span data-ttu-id="564f1-154">新操作与基本操作具有相同的签名和类型 `Y` 。</span><span class="sxs-lookup"><span data-stu-id="564f1-154">The new operation has the same signature and type as the base operation `Y`.</span></span>
<span data-ttu-id="564f1-155">具体而言，新操作还支持 `Adjoint` ，且 `Controlled` 仅当基本操作为时才支持。</span><span class="sxs-lookup"><span data-stu-id="564f1-155">In particular, the new operation also supports `Adjoint`, and supports `Controlled` if and only if the base operation did.</span></span>
<span data-ttu-id="564f1-156">`Adjoint`函子是其自身的反向; 即， `Adjoint Adjoint Op` 始终与相同 `Op` 。</span><span class="sxs-lookup"><span data-stu-id="564f1-156">The `Adjoint` functor is its own inverse; that is, `Adjoint Adjoint Op` is always the same as `Op`.</span></span>

#### <a name="controlled-functor"></a><span data-ttu-id="564f1-157">`Controlled`函子</span><span class="sxs-lookup"><span data-stu-id="564f1-157">`Controlled` functor</span></span>

<span data-ttu-id="564f1-158">同样， `Controlled X(controls, target)` 将 `Controlled` 函子应用到 `X` 操作以生成新的操作，并将该新操作应用于 `controls` 和 `target` 。</span><span class="sxs-lookup"><span data-stu-id="564f1-158">Similarly, `Controlled X(controls, target)` applies the `Controlled` functor to the `X` operation to generate a new operation, and applies that new operation to `controls` and `target`.</span></span>

> [!NOTE]
> <span data-ttu-id="564f1-159">在中 Q# ，受控制的版本始终采用控件 qubits 数组，并且控制始终基于所有控件 qubits 处于计算 (`PauliZ`) `One` 状态 $ \ket {1} $。</span><span class="sxs-lookup"><span data-stu-id="564f1-159">In Q#, controlled versions always take an array of control qubits, and the controlling is always based on all of the control qubits being in the computational (`PauliZ`) `One` state, $\ket{1}$.</span></span>
> <span data-ttu-id="564f1-160">基于其他状态的控制是通过在受控操作之前向控件 qubits 应用适当的单一操作来实现的，然后在受控操作之后应用单一操作的逆。</span><span class="sxs-lookup"><span data-stu-id="564f1-160">Controlling based on other states is achieved by applying the appropriate unitary operation to the control qubits before the controlled operation, and then applying the inverses of the unitary operation after the controlled operation.</span></span>
> <span data-ttu-id="564f1-161">例如，将操作应用 `X` 于受控操作前后的控件 qubit 会导致操作控制该 `Zero` qubit 的状态 ($ \ket {0} $) ; `H` 在状态上和控件之前和之后应用操作 `PauliX` `One` ，即 Pauli X，$ \ket {-} \mathrel{： =} ( \ket {0} -\ket {1}) /\sqrt {2} $，而不是 `PauliZ` `One` 状态。</span><span class="sxs-lookup"><span data-stu-id="564f1-161">For example, applying an `X` operation to a control qubit before and after a controlled operation causes the operation to control on the `Zero` state ($\ket{0}$) for that qubit; applying an `H` operation before and after controls on the `PauliX` `One` state, that is -1 eigenvalue of Pauli X, $\ket{-} \mathrel{:=} (\ket{0} - \ket{1}) / \sqrt{2}$ rather than the `PauliZ` `One` state.</span></span>

<span data-ttu-id="564f1-162">给定一个操作表达式，你可以使用函子来形成新的操作表达式 `Controlled` 。</span><span class="sxs-lookup"><span data-stu-id="564f1-162">Given an operation expression, you can form a new operation expression by using the `Controlled` functor.</span></span>
<span data-ttu-id="564f1-163">新操作的签名基于原始操作的签名。</span><span class="sxs-lookup"><span data-stu-id="564f1-163">The signature of the new operation is based on the signature of the original operation.</span></span>
<span data-ttu-id="564f1-164">结果类型是相同的，但输入类型是一个具有 qubit 数组的双元组，该数组保存作为第一个元素的控件 qubit () s，作为第二个元素的初始操作的参数。</span><span class="sxs-lookup"><span data-stu-id="564f1-164">The result type is the same, but the input type is a two-tuple with a qubit array that holds the control qubit(s) as the first element and the arguments of the original operation as the second element.</span></span>
<span data-ttu-id="564f1-165">新操作支持 `Controlled` ，且 `Adjoint` 仅当原始操作执行时才支持。</span><span class="sxs-lookup"><span data-stu-id="564f1-165">The new operation supports `Controlled`, and will support `Adjoint` if and only if the original operation did.</span></span>

<span data-ttu-id="564f1-166">如果原始操作只使用了一个参数，则会在此处播放[单独的元组等效](xref:microsoft.quantum.guide.types)性。</span><span class="sxs-lookup"><span data-stu-id="564f1-166">If the original operation took only a single argument, then [singleton tuple equivalence](xref:microsoft.quantum.guide.types) comes into play here.</span></span>
<span data-ttu-id="564f1-167">例如， `Controlled X` 是操作的受控版本 `X` 。</span><span class="sxs-lookup"><span data-stu-id="564f1-167">For instance, `Controlled X` is the controlled version of the `X` operation.</span></span> 
<span data-ttu-id="564f1-168">`X`具有类型 `(Qubit => Unit is Adj + Ctl)` ，因此 `Controlled X` 具有类型 `((Qubit[], (Qubit)) => Unit is Adj + Ctl)` ; 由于单一元组等效，这与相同 `((Qubit[], Qubit) => Unit is Adj + Ctl)` 。</span><span class="sxs-lookup"><span data-stu-id="564f1-168">`X` has type `(Qubit => Unit is Adj + Ctl)`, so `Controlled X` has type `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`; because of singleton tuple equivalence, this is the same as `((Qubit[], Qubit) => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="564f1-169">如果基本操作采用多个参数，请记住将操作的受控版本的相应参数括在括号中，以将其转换为元组。</span><span class="sxs-lookup"><span data-stu-id="564f1-169">If the base operation took several arguments, remember to enclose the corresponding arguments of the controlled version of the operation in parentheses to convert them into a tuple.</span></span>
<span data-ttu-id="564f1-170">例如， `Controlled Rz` 是操作的受控版本 `Rz` 。</span><span class="sxs-lookup"><span data-stu-id="564f1-170">For instance, `Controlled Rz` is the controlled version of the `Rz` operation.</span></span> 
<span data-ttu-id="564f1-171">`Rz`具有类型 `((Double, Qubit) => Unit is Adj + Ctl)` ，因此 `Controlled Rz` 具有类型 `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)` 。</span><span class="sxs-lookup"><span data-stu-id="564f1-171">`Rz` has type `((Double, Qubit) => Unit is Adj + Ctl)`, so `Controlled Rz` has type `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="564f1-172">因此，将 `Controlled Rz(controls, (0.1, target))` 是 (的有效调用， `Controlled Rz` 请注意) 附近的括号 `0.1, target` 。</span><span class="sxs-lookup"><span data-stu-id="564f1-172">Thus, `Controlled Rz(controls, (0.1, target))` would be a valid invocation of `Controlled Rz` (note the parentheses around `0.1, target`).</span></span>

<span data-ttu-id="564f1-173">作为另一个示例， `CNOT(control, target)` 可以实现为 `Controlled X([control], target)` 。</span><span class="sxs-lookup"><span data-stu-id="564f1-173">As another example, `CNOT(control, target)` can be implemented as `Controlled X([control], target)`.</span></span> <span data-ttu-id="564f1-174">如果目标应由两个 control qubits (CCNOT) 控制，请使用 `Controlled X([control1, control2], target)` 语句。</span><span class="sxs-lookup"><span data-stu-id="564f1-174">If a target should be controlled by two control qubits (CCNOT), use a `Controlled X([control1, control2], target)` statement.</span></span>

#### `Controlled Adjoint` 

<span data-ttu-id="564f1-175">`Controlled`和 `Adjoint` 函子的上下班，因此应用或之间没有区别 `Controlled Adjoint Op` `Adjoint Controlled Op` 。</span><span class="sxs-lookup"><span data-stu-id="564f1-175">The `Controlled` and `Adjoint` functors commute, so there is no difference between applying `Controlled Adjoint Op` or `Adjoint Controlled Op`.</span></span>


## <a name="defining-controlled-and-adjoint-implementations"></a><span data-ttu-id="564f1-176">定义受控和 Adjoint 实现</span><span class="sxs-lookup"><span data-stu-id="564f1-176">Defining Controlled and Adjoint Implementations</span></span>

<span data-ttu-id="564f1-177">在前面的示例中的第一个操作声明中，操作 `BitFlip` 和 `DecodeSuperdense` 分别定义为签名 `(Qubit => Unit)` 和 `((Qubit, Qubit) => (Result, Result))` 。</span><span class="sxs-lookup"><span data-stu-id="564f1-177">In the first operation declaration in the previous examples, the operations `BitFlip` and `DecodeSuperdense` were defined with signatures `(Qubit => Unit)` and `((Qubit, Qubit) => (Result, Result))`, respectively.</span></span>
<span data-ttu-id="564f1-178">`DecodeSuperdense`这并不是一个单一的操作，因此，它不是一种单一操作，因此，不能 adjoint 特殊化， (重新调用此类操作返回) 的相关要求 `Unit` 。</span><span class="sxs-lookup"><span data-stu-id="564f1-178">As `DecodeSuperdense` includes measurements, it is not a unitary operation, and therefore neither controlled not adjoint specializations could exist (recall the related requirement that such an operation return `Unit`).</span></span>
<span data-ttu-id="564f1-179">但是， `BitFlip` 只需执行单一 <xref:microsoft.quantum.intrinsic.x> 操作，即可将其定义为专用化。</span><span class="sxs-lookup"><span data-stu-id="564f1-179">However, as `BitFlip` simply performs the unitary <xref:microsoft.quantum.intrinsic.x> operation, you could have defined it with both specializations.</span></span>

<span data-ttu-id="564f1-180">本节详细介绍了如何在操作声明中包括特殊化的存在性 Q# ，从而使它们能够与 `Adjoint` 或函子一起调用 `Controlled` 。</span><span class="sxs-lookup"><span data-stu-id="564f1-180">This section details how to include the existence of specializations in your Q# operation declarations, hence giving them the ability to called in conjunction with the `Adjoint` or `Controlled` functors.</span></span>
<span data-ttu-id="564f1-181">若要详细了解它是有效的或无效的声明特定专用化的某些情况，请参阅本文中[的有效定义专用](#circumstances-for-validly-defining-specializations)化的情况。</span><span class="sxs-lookup"><span data-stu-id="564f1-181">For more information about some of the situations in which it is either valid or not valid to declare certain specializations, see [Circumstances for validly defining specializations](#circumstances-for-validly-defining-specializations) in this article.</span></span>

<span data-ttu-id="564f1-182">操作特征定义可应用于声明的操作的函子类型，以及它们的影响。</span><span class="sxs-lookup"><span data-stu-id="564f1-182">Operation characteristics define what kinds of functors you can apply to the declared operation, and what effect they have.</span></span> <span data-ttu-id="564f1-183">这些专用化的存在可以声明为操作签名的一部分，具体而言，具有操作特征： `is Adj` 、 `is Ctl` 或 `is Adj + Ctl` 。</span><span class="sxs-lookup"><span data-stu-id="564f1-183">The existence of these specializations can be declared as part of the operation signature, specifically through an annotation with the operation characteristics: either `is Adj`, `is Ctl`, or `is Adj + Ctl`.</span></span>
<span data-ttu-id="564f1-184">可以*隐式*或*显式*定义每个特殊化的实际实现。</span><span class="sxs-lookup"><span data-stu-id="564f1-184">The actual implementation of each specialization can either be *implicitly* or *explicitly* defined.</span></span>

### <a name="implicitly-specifying-implementations"></a><span data-ttu-id="564f1-185">隐式指定实现</span><span class="sxs-lookup"><span data-stu-id="564f1-185">Implicitly specifying implementations</span></span>

<span data-ttu-id="564f1-186">在这种情况下，操作声明的主体只包含默认实现。</span><span class="sxs-lookup"><span data-stu-id="564f1-186">In this case, the body of the operation declaration consists solely of the default implementation.</span></span> <span data-ttu-id="564f1-187">例如：</span><span class="sxs-lookup"><span data-stu-id="564f1-187">For example:</span></span>

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```
<span data-ttu-id="564f1-188">此处，编译器会自动生成每个此类隐式声明的专用化的对应实现，以在 `Adjoint` 使用或 `Controlled` 函子时执行。</span><span class="sxs-lookup"><span data-stu-id="564f1-188">Here, the corresponding implementation for each such implicitly declared specialization is automatically generated by the compiler, to be performed if the `Adjoint` or `Controlled` functors are used.</span></span>

<span data-ttu-id="564f1-189">因此，对的调用 `Adjoint PrepareEntangledPair` 将导致编译器实现的 adjoint `CNOT` ，然后实现的 adjoint `H` 。</span><span class="sxs-lookup"><span data-stu-id="564f1-189">So, a call of `Adjoint PrepareEntangledPair` would result in the compiler implementing the adjoint of `CNOT` and then the adjoint of `H`.</span></span>
<span data-ttu-id="564f1-190">这些单独的操作都是 adjoint 的，因此，生成的 `Adjoint PrepareEntangledPair` 操作只包含应用 `CNOT(here, there)` 和 `H(here)` 。</span><span class="sxs-lookup"><span data-stu-id="564f1-190">These individual operations are both self-adjoint, so the resulting `Adjoint PrepareEntangledPair` operation would simply consist of applying `CNOT(here, there)` and then `H(here)`.</span></span>
<span data-ttu-id="564f1-191">因此，你可以使用此 `DecodeSuperdense` 方法，通过使用 adjoint `PrepareEntangledPair` 将放大状态转换回 qubits 的 unentangled 对，来更简洁地地编写上一个示例中的。</span><span class="sxs-lookup"><span data-stu-id="564f1-191">Hence you can use this to write the `DecodeSuperdense` in the previous example more compactly, by using the adjoint of `PrepareEntangledPair` to transform the entangled state back into an unentangled pair of qubits:</span></span>

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

<span data-ttu-id="564f1-192">声明中具有操作特征的批注非常有用，可确保编译器根据默认实现自动生成其他专用化。</span><span class="sxs-lookup"><span data-stu-id="564f1-192">The annotation with the operation characteristics in the declaration is useful to ensure that the compiler auto-generates other specializations based on the default implementation.</span></span> 

<span data-ttu-id="564f1-193">设计用于函子的操作时，需要考虑几个重要的限制。</span><span class="sxs-lookup"><span data-stu-id="564f1-193">There are several important limitations to consider when designing operations for use with functors.</span></span>
<span data-ttu-id="564f1-194">大多数情况下，编译器*不能*自动生成使用任何其他操作的输出值的操作的专用化，因为在此类操作中，如何对语句重新排序以获得相同的效果。</span><span class="sxs-lookup"><span data-stu-id="564f1-194">Most critically, specializations for an operation that uses the output value of any other operation *cannot* be auto-generated by the compiler, as it is ambiguous how to reorder the statements in such an operation to obtain the same effect.</span></span>

<span data-ttu-id="564f1-195">因此，显式指定各种实现通常非常有用。</span><span class="sxs-lookup"><span data-stu-id="564f1-195">Therefore, it is often useful to explicitly specify the various implementations.</span></span>

### <a name="explicitly-specifying-implementations"></a><span data-ttu-id="564f1-196">显式指定实现</span><span class="sxs-lookup"><span data-stu-id="564f1-196">Explicitly specifying implementations</span></span>

<span data-ttu-id="564f1-197">如果编译器无法生成实现，则可以显式指定它。</span><span class="sxs-lookup"><span data-stu-id="564f1-197">In the case where the compiler cannot generate the implementation, you can specify it explicitly.</span></span> <span data-ttu-id="564f1-198">此类显式专用化声明可以包含合适的*生成指令*或用户定义的实现。</span><span class="sxs-lookup"><span data-stu-id="564f1-198">Such explicit specialization declarations can consist of a suitable *generation directive* or a user-defined implementation.</span></span>
<span data-ttu-id="564f1-199">下面是各种可能性，其中有一些显式特殊化的示例。</span><span class="sxs-lookup"><span data-stu-id="564f1-199">Following are the full range of possibilities, with some examples of explicit specialization.</span></span> 


#### <a name="explicit-specialization-declarations"></a><span data-ttu-id="564f1-200">显式专用化声明</span><span class="sxs-lookup"><span data-stu-id="564f1-200">Explicit specialization declarations</span></span>

<span data-ttu-id="564f1-201">Q#操作可以包含以下显式专用化声明：</span><span class="sxs-lookup"><span data-stu-id="564f1-201">Q# operations can contain the following explicit specialization declarations:</span></span>

- <span data-ttu-id="564f1-202">`body`专用化指定未应用函子的操作的实现。</span><span class="sxs-lookup"><span data-stu-id="564f1-202">The `body` specialization specifies the implementation of the operation with no functors applied.</span></span>
- <span data-ttu-id="564f1-203">`adjoint`专用化指定应用了函子的操作的实现 `Adjoint` 。</span><span class="sxs-lookup"><span data-stu-id="564f1-203">The `adjoint` specialization specifies the implementation of the operation with the `Adjoint` functor applied.</span></span>
- <span data-ttu-id="564f1-204">`controlled`专用化指定应用了函子的操作的实现 `Controlled` 。</span><span class="sxs-lookup"><span data-stu-id="564f1-204">The `controlled` specialization specifies the implementation of the operation with the `Controlled` functor applied.</span></span>
- <span data-ttu-id="564f1-205">`controlled adjoint`专用化指定操作的实现，同时 `Adjoint` `Controlled` 应用和函子。</span><span class="sxs-lookup"><span data-stu-id="564f1-205">The `controlled adjoint` specialization specifies the implementation of the operation with both the `Adjoint` and `Controlled` functors applied.</span></span>
  <span data-ttu-id="564f1-206">此特殊化还可以命名 `adjoint controlled` ，因为这两个函子。</span><span class="sxs-lookup"><span data-stu-id="564f1-206">This specialization can also be named `adjoint controlled`, since the two functors commute.</span></span>


<span data-ttu-id="564f1-207">操作特殊化包含专业化标记 (例如， `body` 或 `adjoint`) 后跟以下其中之一：</span><span class="sxs-lookup"><span data-stu-id="564f1-207">An operation specialization consists of the specialization tag (for example, `body` or `adjoint`) followed by one of:</span></span>

- <span data-ttu-id="564f1-208">如下所述的显式声明。</span><span class="sxs-lookup"><span data-stu-id="564f1-208">An explicit declaration as described in the following.</span></span>
- <span data-ttu-id="564f1-209">告诉编译器*如何*生成专用化的*指令*，可以是：</span><span class="sxs-lookup"><span data-stu-id="564f1-209">A *directive* that tells the compiler *how* to generate the specialization, one of:</span></span>
  - <span data-ttu-id="564f1-210">`intrinsic`，它指示目标计算机提供专用化。</span><span class="sxs-lookup"><span data-stu-id="564f1-210">`intrinsic`, which indicates that the target machine provides the specialization.</span></span>
  - <span data-ttu-id="564f1-211">`distribute`，与和专用化一起使用 `controlled` `controlled adjoint` 。</span><span class="sxs-lookup"><span data-stu-id="564f1-211">`distribute`, used with the `controlled` and `controlled adjoint` specializations.</span></span>
    <span data-ttu-id="564f1-212">当与一起使用时 `controlled` ，它指示编译器应通过将应用 `Controlled` 到中的所有操作来计算特殊化 `body` 。</span><span class="sxs-lookup"><span data-stu-id="564f1-212">When used with `controlled`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `body`.</span></span>
    <span data-ttu-id="564f1-213">当与一起使用时 `controlled adjoint` ，它指示编译器应通过将应用 `Controlled` 到专用化中的所有操作来计算特殊化 `adjoint` 。</span><span class="sxs-lookup"><span data-stu-id="564f1-213">When used with `controlled adjoint`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `adjoint` specialization.</span></span>
  - <span data-ttu-id="564f1-214">`invert`，它指示编译器应 `adjoint` 通过反序列化来计算特殊化 `body` ，例如，反转运算顺序并将 adjoint 应用于每个操作。</span><span class="sxs-lookup"><span data-stu-id="564f1-214">`invert`, which indicates that the compiler should compute the `adjoint` specialization by inverting the `body`, for example, reversing the order of operations and applying the adjoint to each one.</span></span>
    <span data-ttu-id="564f1-215">当与一起使用时 `adjoint controlled` ，这指示编译器应通过反转专用化来计算特殊化 `controlled` 。</span><span class="sxs-lookup"><span data-stu-id="564f1-215">When used with `adjoint controlled`, this indicates that the compiler should compute the specialization by inverting the `controlled` specialization.</span></span>
  - <span data-ttu-id="564f1-216">`self`，指示 adjoint 专用化与 `body` 专用化相同。</span><span class="sxs-lookup"><span data-stu-id="564f1-216">`self`, to indicate that the adjoint specialization is the same as the `body` specialization.</span></span>
    <span data-ttu-id="564f1-217">`self`对于和专用化，使用是合法的 `adjoint` `adjoint controlled` 。</span><span class="sxs-lookup"><span data-stu-id="564f1-217">Using `self` is legal for the `adjoint` and `adjoint controlled` specializations.</span></span>
    <span data-ttu-id="564f1-218">对于 `adjoint controlled` ， `self` 表示 `adjoint controlled` 专用化与 `controlled` 特殊化相同。</span><span class="sxs-lookup"><span data-stu-id="564f1-218">For `adjoint controlled`, `self` implies that the `adjoint controlled` specialization is the same as the `controlled` specialization.</span></span>
  - <span data-ttu-id="564f1-219">`auto`，指示编译器应选择要应用的适当指令。</span><span class="sxs-lookup"><span data-stu-id="564f1-219">`auto`, to indicate that the compiler should select an appropriate directive to apply.</span></span>
    <span data-ttu-id="564f1-220">不能将 `auto` 用于 `body` 专用化。</span><span class="sxs-lookup"><span data-stu-id="564f1-220">You cannot use`auto` for the `body` specialization.</span></span>

<span data-ttu-id="564f1-221">指令和 `auto` 都需要右分号 `;` 。</span><span class="sxs-lookup"><span data-stu-id="564f1-221">The directives and `auto` all require a closing semi-colon `;`.</span></span>
<span data-ttu-id="564f1-222">`auto`如果提供了的显式声明，则指令将解析为以下生成的指令 `body` ：</span><span class="sxs-lookup"><span data-stu-id="564f1-222">The `auto` directive resolves to the following generated directive if an explicit declaration of the `body` is provided:</span></span>

- <span data-ttu-id="564f1-223">`adjoint`根据指令生成专用化 `invert` 。</span><span class="sxs-lookup"><span data-stu-id="564f1-223">The `adjoint` specialization generates according to the directive `invert`.</span></span>
- <span data-ttu-id="564f1-224">`controlled`根据指令生成专用化 `distribute` 。</span><span class="sxs-lookup"><span data-stu-id="564f1-224">The `controlled` specialization generates according to the directive `distribute`.</span></span>
- <span data-ttu-id="564f1-225">`adjoint controlled` `invert` 如果为 `controlled` 指定了显式声明，而不是为指定了一个，则根据指令生成专用化 `adjoint` `distribute` 。</span><span class="sxs-lookup"><span data-stu-id="564f1-225">The `adjoint controlled` specialization  generates according to the directive `invert` if an explicit declaration for `controlled` is given but not one for `adjoint`, and `distribute` otherwise.</span></span>

> [!TIP]   
> <span data-ttu-id="564f1-226">如果操作是自我 adjoint 的，则通过生成指令显式指定 adjoint 或受控 adjoint 专用化，以便 `self` 编译器可以利用该信息进行优化。</span><span class="sxs-lookup"><span data-stu-id="564f1-226">If an operation is self-adjoint, explicitly specify either the adjoint or the controlled adjoint specialization via the generation directive `self` to allow the compiler to make use of that information for optimization purposes.</span></span>

<span data-ttu-id="564f1-227">包含用户定义的实现的专用化声明包含一个参数元组，后面跟有用于 Q# 实现专用化的代码的语句块。</span><span class="sxs-lookup"><span data-stu-id="564f1-227">A specialization declaration containing a user-defined implementation consists of an argument tuple followed by a statement block with the Q# code that implements the specialization.</span></span>
<span data-ttu-id="564f1-228">在参数列表中， `...` 用于表示作为一个整体为操作声明的参数。</span><span class="sxs-lookup"><span data-stu-id="564f1-228">In the argument list, `...` is used to represent the arguments declared for the operation as a whole.</span></span>
<span data-ttu-id="564f1-229">对于 `body` 和 `adjoint` ，参数列表应始终为 `(...)` ; 对于 `controlled` 和 `adjoint controlled` ，参数列表应为表示控件 qubits 数组的符号，后面跟有 `...` 括号括在括号中; 例如， `(controls,...)` 。</span><span class="sxs-lookup"><span data-stu-id="564f1-229">For `body` and `adjoint`, the argument list should always be `(...)`; for `controlled` and `adjoint controlled`, the argument list should be a symbol that represents the array of control qubits, followed by `...`, enclosed in parentheses; for example, `(controls,...)`.</span></span>

### <a name="examples"></a><span data-ttu-id="564f1-230">示例</span><span class="sxs-lookup"><span data-stu-id="564f1-230">Examples</span></span>

<span data-ttu-id="564f1-231">操作声明可能非常简单，如下所示：定义基元 Pauli X 操作：</span><span class="sxs-lookup"><span data-stu-id="564f1-231">An operation declaration might be as simple as the following, which defines the primitive Pauli X operation:</span></span>

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```
<span data-ttu-id="564f1-232">请注意，Pauli X 操作的 adjoint 是使用指令定义的， `self` 因为按定义 `X` 是其自身的反向运算。</span><span class="sxs-lookup"><span data-stu-id="564f1-232">Note that the adjoint of the Pauli X operation is defined with the directive `self` because by definition `X` is its own inverse.</span></span>

<span data-ttu-id="564f1-233">在前面的 `PrepareEntangledPair` 示例中，代码等效于以下包含显式专用化声明的代码：</span><span class="sxs-lookup"><span data-stu-id="564f1-233">In the earlier `PrepareEntangledPair` example, the code is equivalent to the following code containing explicit specialization declarations:</span></span> 

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
<span data-ttu-id="564f1-234">关键字 `auto` 指示编译器应该确定如何生成专用化实现。</span><span class="sxs-lookup"><span data-stu-id="564f1-234">The keyword `auto` indicates that the compiler should determine how to generate the specialization implementation.</span></span>

#### <a name="user-defined-specialization-implementation"></a><span data-ttu-id="564f1-235">用户定义的特殊化实现</span><span class="sxs-lookup"><span data-stu-id="564f1-235">User-defined specialization implementation</span></span>

<span data-ttu-id="564f1-236">如果编译器无法自动生成特定专用化的实现，或者如果可以提供更有效的实现，则可以手动定义实现。</span><span class="sxs-lookup"><span data-stu-id="564f1-236">If the compiler cannot generate the implementation for a certain specialization automatically, or if a more efficient implementation can be given, then you can manually define the implementation.</span></span>

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
<span data-ttu-id="564f1-237">在上面的示例中， `adjoint invert;` 指示 adjoint 专用化是通过反转正文实现生成的，并指示将 `controlled adjoint invert;` 通过反转受控专用化的给定实现生成受控 adjoint 特殊化。</span><span class="sxs-lookup"><span data-stu-id="564f1-237">In the previous example, `adjoint invert;` indicates that the adjoint specialization is to be generated by inverting the body implementation, and `controlled adjoint invert;` indicates that the controlled adjoint specialization is to be generated by inverting the given implementation of the controlled specialization.</span></span>

<span data-ttu-id="564f1-238">如果需要显式声明默认正文之外的一个或多个特殊化，则默认体的实现也需要包装到适当的专用化声明中：</span><span class="sxs-lookup"><span data-stu-id="564f1-238">If one or more specializations besides the default body need to be explicitly declared, then the implementation for the default body needs to be wrapped into a suitable specialization declaration as well:</span></span>

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

### <a name="circumstances-for-validly-defining-specializations"></a><span data-ttu-id="564f1-239">有效定义专用化的情况</span><span class="sxs-lookup"><span data-stu-id="564f1-239">Circumstances for validly defining specializations</span></span>

#### <a name="operation-declarations-with-adjointcontrolled"></a><span data-ttu-id="564f1-240">带有 adjoint/控制的操作声明</span><span class="sxs-lookup"><span data-stu-id="564f1-240">Operation declarations with adjoint/controlled</span></span>

<span data-ttu-id="564f1-241">指定不具有 adjoint 或受控版本的操作是合法的。</span><span class="sxs-lookup"><span data-stu-id="564f1-241">It is legal to specify an operation with no adjoint or controlled versions.</span></span> <span data-ttu-id="564f1-242">例如，由于度量值不可逆或可控制，因此它们不是可逆的。</span><span class="sxs-lookup"><span data-stu-id="564f1-242">For instance, measurement operations have neither because they are not invertible or controllable.</span></span>

<span data-ttu-id="564f1-243">如果操作的 `Adjoint` `Controlled` 声明包含各自专用化的隐式或显式声明，则操作支持和函子。</span><span class="sxs-lookup"><span data-stu-id="564f1-243">An operation supports the `Adjoint` and `Controlled` functors if its declaration contains an implicit or explicit declaration of the respective specializations.</span></span>

<span data-ttu-id="564f1-244">显式声明的 adjoint/受控专用化意味着存在 adjoint/受控专用化。</span><span class="sxs-lookup"><span data-stu-id="564f1-244">An explicitly declared adjoint/controlled specialization implies the existence of an adjoint/controlled specialization.</span></span> 

<span data-ttu-id="564f1-245">对于正文包含重复执行循环、set 语句、度量、return 语句或对不支持函子的其他操作的操作 `Adjoint` ， `invert` 不能通过或指令自动生成 adjoint 专用化 `auto` 。</span><span class="sxs-lookup"><span data-stu-id="564f1-245">For an operation whose body contains repeat-until-success loops, set statements, measurements, return statements, or calls to other operations that do not support the `Adjoint` functor, auto-generating an adjoint specialization following the `invert` or `auto` directive is not possible.</span></span>

<span data-ttu-id="564f1-246">对于包含对不支持函子的其他操作的调用的操作 `Controlled` ， `distribute` 不能在或指令后自动生成受控专用化 `auto` 。</span><span class="sxs-lookup"><span data-stu-id="564f1-246">For an operation whose body contains calls to other operations that do not support the `Controlled` functor, auto-generating a controlled specialization following the `distribute` or `auto` directive is not possible.</span></span>

#### <a name="controlled-adjoint"></a><span data-ttu-id="564f1-247">受控 Adjoint</span><span class="sxs-lookup"><span data-stu-id="564f1-247">Controlled Adjoint</span></span>

<span data-ttu-id="564f1-248">操作的受控 adjoint 版本指定如何实现该操作的 adjoint 的量程控制版本。</span><span class="sxs-lookup"><span data-stu-id="564f1-248">The controlled adjoint version of an operation specifies how to implement a quantum-controlled version of the adjoint of the operation.</span></span>
<span data-ttu-id="564f1-249">指定不具有受控 adjoint 版本的操作是合法的;例如，度量操作没有受控的 adjoint 版本，因为它们既不能控制也不可逆。</span><span class="sxs-lookup"><span data-stu-id="564f1-249">It is legal to specify an operation with no controlled adjoint version; for instance, measurement operations have no controlled adjoint version because they are neither controllable nor invertible.</span></span>

<span data-ttu-id="564f1-250">当且仅当存在 adjoint 和受控专用化时，操作的受控 adjoint 专用化才需要存在。</span><span class="sxs-lookup"><span data-stu-id="564f1-250">A controlled adjoint specialization for an operation needs to exist if and only if both an adjoint and a controlled specialization exist.</span></span> <span data-ttu-id="564f1-251">在这种情况下，将推断出是否存在受控 adjoint 专用化。</span><span class="sxs-lookup"><span data-stu-id="564f1-251">In that case, the existence of the controlled adjoint specialization is inferred.</span></span> <span data-ttu-id="564f1-252">如果未显式定义实现，编译将生成适当的专用化。</span><span class="sxs-lookup"><span data-stu-id="564f1-252">If no implementation is explicitly defined, the compile generates an appropriate specialization.</span></span>

<span data-ttu-id="564f1-253">对于其正文包含对没有受控 adjoint 版本的其他操作的调用的操作， `invert` 无法在、 `distribute` 或指令后自动生成 adjoint 特殊化 `auto` 。</span><span class="sxs-lookup"><span data-stu-id="564f1-253">For an operation whose body contains calls to other operations that do not have a controlled adjoint version, auto-generating an adjoint specialization following the `invert`, `distribute`, or `auto` directive is not possible.</span></span>


### <a name="type-compatibility"></a><span data-ttu-id="564f1-254">类型兼容性</span><span class="sxs-lookup"><span data-stu-id="564f1-254">Type Compatibility</span></span>

<span data-ttu-id="564f1-255">使用具有更少函子但签名相同的操作的其他函子支持的操作。</span><span class="sxs-lookup"><span data-stu-id="564f1-255">Use an operation with additional functors supported anywhere you use an operation with fewer functors but the same signature.</span></span> <span data-ttu-id="564f1-256">例如，使用类型为的操作的 `(Qubit => Unit is Adj)` 任何地方的类型运算 `(Qubit => Unit)` 。</span><span class="sxs-lookup"><span data-stu-id="564f1-256">For instance, use an operation of type `(Qubit => Unit is Adj)` anywhere you use an operation of type `(Qubit => Unit)`.</span></span>

<span data-ttu-id="564f1-257">Q#对于可调用的返回类型是*协变*的：返回类型的可调用与 `'A` 具有相同输入类型的可调用和与兼容的结果类型兼容 `'A` 。</span><span class="sxs-lookup"><span data-stu-id="564f1-257">Q# is *covariant* with respect to callable return types: a callable that returns a type `'A` is compatible with a callable with the same input type and a result type that is compatible with `'A` .</span></span>

<span data-ttu-id="564f1-258">Q#对于输入类型是*逆变*的：将类型作为输入的可调用与 `'A` 具有相同结果类型的可调用和兼容的输入类型兼容 `'A` 。</span><span class="sxs-lookup"><span data-stu-id="564f1-258">Q# is *contravariant* with respect to input types: a callable that takes a type `'A` as input is compatible with a callable with the same result type and an input type that is compatible with `'A`.</span></span>

<span data-ttu-id="564f1-259">即，给定以下定义，</span><span class="sxs-lookup"><span data-stu-id="564f1-259">That is, given the following definitions,</span></span>

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

<span data-ttu-id="564f1-260">您可以</span><span class="sxs-lookup"><span data-stu-id="564f1-260">you can</span></span>

- <span data-ttu-id="564f1-261">`ConjugateInvertWith`使用或的参数调用函数 `inner` `Invert` `ApplyUnitary` 。</span><span class="sxs-lookup"><span data-stu-id="564f1-261">Invoke the function `ConjugateInvertWith` with an `inner` argument of either `Invert` or `ApplyUnitary`.</span></span>
- <span data-ttu-id="564f1-262">`ConjugateUnitaryWith`使用的 `inner` 参数 `ApplyUnitary` （而不是）调用函数 `Invert` 。</span><span class="sxs-lookup"><span data-stu-id="564f1-262">Invoke the function `ConjugateUnitaryWith` with an `inner` argument of `ApplyUnitary`, but not `Invert`.</span></span>
- <span data-ttu-id="564f1-263">从返回一个类型的 `(Qubit[] => Unit is Adj + Ctl)` 值 `ConjugateInvertWith` 。</span><span class="sxs-lookup"><span data-stu-id="564f1-263">Return a value of type `(Qubit[] => Unit is Adj + Ctl)` from `ConjugateInvertWith`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="564f1-264">Q#0.3 引入了用户定义类型的行为的显著差异。</span><span class="sxs-lookup"><span data-stu-id="564f1-264">Q# 0.3 introduced a significant difference in the behavior of user-defined types.</span></span>

<span data-ttu-id="564f1-265">用户定义的类型被视为基础类型的包装版本，而不是作为子类型。</span><span class="sxs-lookup"><span data-stu-id="564f1-265">User-defined types are treated as a wrapped version of the underlying type, rather than as a subtype.</span></span>
<span data-ttu-id="564f1-266">这意味着用户定义类型的值在预期基础类型的值为时不能使用。</span><span class="sxs-lookup"><span data-stu-id="564f1-266">This means that a value of a user-defined type is not usable where you expect a value of the underlying type is.</span></span>


### <a name="conjugations"></a><span data-ttu-id="564f1-267">语态</span><span class="sxs-lookup"><span data-stu-id="564f1-267">Conjugations</span></span>

<span data-ttu-id="564f1-268">与传统位相比，释放量程内存会稍微增加一点，因为在 qubits 仍放大时，盲目重置 qubits 可能会对剩余计算产生意外影响。</span><span class="sxs-lookup"><span data-stu-id="564f1-268">In contrast to classical bits, releasing quantum memory is slightly more involved since blindly resetting qubits can have undesired effects on the remaining computation if the qubits are still entangled.</span></span> <span data-ttu-id="564f1-269">在释放内存之前，可以通过适当的方式 "撤消" 已执行的计算来避免这些效果。</span><span class="sxs-lookup"><span data-stu-id="564f1-269">These effects can be avoided by properly "undoing" performed computations prior to releasing the memory.</span></span> <span data-ttu-id="564f1-270">量程计算的常见模式如下：</span><span class="sxs-lookup"><span data-stu-id="564f1-270">A common pattern in quantum computing is hence the following:</span></span> 

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

<span data-ttu-id="564f1-271">从0.9 版本开始， Q# 支持实现前面转换的语态语句。</span><span class="sxs-lookup"><span data-stu-id="564f1-271">Starting with our 0.9 release, Q# supports a conjugation statement that implements the preceding transformation.</span></span> <span data-ttu-id="564f1-272">使用该语句，可以通过 `ApplyWith` 以下方式实现操作：</span><span class="sxs-lookup"><span data-stu-id="564f1-272">Using that statement, the operation `ApplyWith` can be implemented in the following way:</span></span>

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
<span data-ttu-id="564f1-273">如果外部和内部转换不能像操作那样轻松地提供，则这种语态语句就变得更加有用，但通过多个语句组成的块可以更方便地进行描述。</span><span class="sxs-lookup"><span data-stu-id="564f1-273">Such a conjugation statement becomes far more useful if the outer and inner transformations are not readily available as operations but are instead more convenient to describe by a block consisting of several statements.</span></span> 

<span data-ttu-id="564f1-274">在内块中定义的语句的反转换是由编译器自动生成的，并在应用块完成后运行。</span><span class="sxs-lookup"><span data-stu-id="564f1-274">The inverse transformation for the statements defined in the within-block is automatically generated by the compiler and run after the apply-block completes.</span></span>
<span data-ttu-id="564f1-275">由于不能在 apply 块中重新绑定用作内部块的一部分的任何可变变量，因此，生成的转换将保证为内块中计算的 adjoint。</span><span class="sxs-lookup"><span data-stu-id="564f1-275">Since any mutable variables used as part of the within-block cannot be rebound in the apply-block, the generated transformation is guaranteed to be the adjoint of the computation in the within-block.</span></span> 


## <a name="defining-new-functions"></a><span data-ttu-id="564f1-276">定义新函数</span><span class="sxs-lookup"><span data-stu-id="564f1-276">Defining New Functions</span></span>

<span data-ttu-id="564f1-277">函数在中是纯粹确定性的传统例程 Q# ，不同于操作，因为它们不允许在计算输出值之前有任何影响。</span><span class="sxs-lookup"><span data-stu-id="564f1-277">Functions are purely deterministic, classical routines in Q#, which are distinct from operations in that they are not allowed to have any effects beyond calculating an output value.</span></span>
<span data-ttu-id="564f1-278">特别是，函数不能调用操作;操作、分配或借用 qubits;示例随机数;否则，依赖于输入值超出函数的状态。</span><span class="sxs-lookup"><span data-stu-id="564f1-278">In particular, functions cannot call operations; act on, allocate, or borrow qubits; sample random numbers; or otherwise depend on state beyond the input value to a function.</span></span>
<span data-ttu-id="564f1-279">因此， Q# 函数是*纯*的，因为它们始终将相同的输入值映射到相同的输出值。</span><span class="sxs-lookup"><span data-stu-id="564f1-279">As a consequence, Q# functions are *pure*, in that they always map the same input values to the same output values.</span></span>
<span data-ttu-id="564f1-280">此行为允许 Q# 编译器在生成操作专用化时，对调用函数的方式和时间进行安全重新排序。</span><span class="sxs-lookup"><span data-stu-id="564f1-280">This behavior allows the Q# compiler to safely reorder how and when to call functions when generating operation specializations.</span></span>

<span data-ttu-id="564f1-281">每个 Q# 源文件都可以定义任意数量的函数。</span><span class="sxs-lookup"><span data-stu-id="564f1-281">Each Q# source file can define any number of functions.</span></span>
<span data-ttu-id="564f1-282">函数名称在命名空间中必须是唯一的，且不能与操作或类型名称冲突。</span><span class="sxs-lookup"><span data-stu-id="564f1-282">Function names must be unique within a namespace and cannot conflict with operation or type names.</span></span>

<span data-ttu-id="564f1-283">定义函数的工作方式与定义操作类似，但不能为函数定义 adjoint 或受控专用化。</span><span class="sxs-lookup"><span data-stu-id="564f1-283">Defining a function works similarly to defining an operation, except that no adjoint or controlled specializations can be defined for a function.</span></span>
<span data-ttu-id="564f1-284">例如：</span><span class="sxs-lookup"><span data-stu-id="564f1-284">For instance:</span></span>

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```

<span data-ttu-id="564f1-285">or</span><span class="sxs-lookup"><span data-stu-id="564f1-285">or</span></span> 

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

### <a name="classical-logic-in-functions--good"></a><span data-ttu-id="564f1-286">函数 = = 良好中的传统逻辑</span><span class="sxs-lookup"><span data-stu-id="564f1-286">Classical logic in functions == good</span></span>

<span data-ttu-id="564f1-287">只要有可能，就可以根据函数（而不是操作）编写传统逻辑，使操作能够更轻松地使用它。</span><span class="sxs-lookup"><span data-stu-id="564f1-287">Whenever it is possible to do so, it is helpful to write out classical logic in terms of functions rather than operations so that operations can more readily use it.</span></span> <span data-ttu-id="564f1-288">例如，如果您已编写了前面的 `Square` 声明作为*运算*，则编译器不能保证使用相同的输入调用它会一致地生成相同的输出。</span><span class="sxs-lookup"><span data-stu-id="564f1-288">For example, if you had written the earlier `Square` declaration as an *operation*, then the compiler would not have been able to guarantee that calling it with the same input would consistently produce the same outputs.</span></span>

<span data-ttu-id="564f1-289">为了下划线函数和操作之间的差异，请考虑经典在操作中采样随机数字的问题 Q# ：</span><span class="sxs-lookup"><span data-stu-id="564f1-289">To underscore the difference between functions and operations, consider the problem of classically sampling a random number from within a Q# operation:</span></span>

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

<span data-ttu-id="564f1-290">每次 `U` 调用时，它将对执行不同的操作 `target` 。</span><span class="sxs-lookup"><span data-stu-id="564f1-290">Each time that `U` is called, it has a different action on `target`.</span></span>
<span data-ttu-id="564f1-291">特别是，如果您将一个专用化声明添加到，则该编译器无法保证，它作为 `adjoint auto` `U` 一种 `U(target); Adjoint U(target);` 无操作)  (。</span><span class="sxs-lookup"><span data-stu-id="564f1-291">In particular, the compiler cannot guarantee that if you add an `adjoint auto` specialization declaration to `U`, then `U(target); Adjoint U(target);` acts as identity (that is, as a no-op).</span></span>
<span data-ttu-id="564f1-292">这违反了在[向量和矩阵](xref:microsoft.quantum.concepts.vectors)中定义的 adjoint 的定义，使编译器能够在调用操作的操作中自动生成 adjoint 特殊化，这 <xref:microsoft.quantum.math.randomreal> 会破坏编译器提供的保证; <xref:microsoft.quantum.math.randomreal> 是不存在 adjoint 或受控版本的操作。</span><span class="sxs-lookup"><span data-stu-id="564f1-292">This violates the definition of the adjoint defined in [Vectors and Matrices](xref:microsoft.quantum.concepts.vectors), such that allowing the compiler to auto-generate an adjoint specialization in an operation where you call the operation <xref:microsoft.quantum.math.randomreal> would break the guarantees provided by the compiler; <xref:microsoft.quantum.math.randomreal> is an operation for which no adjoint or controlled version exists.</span></span>

<span data-ttu-id="564f1-293">另一方面，允许函数调用（如） `Square` 是安全的，并确保编译器仅需保留输入以 `Square` 保持其输出稳定。</span><span class="sxs-lookup"><span data-stu-id="564f1-293">On the other hand, allowing function calls such as `Square` is safe, and assures the compiler that it only needs to preserve the input to `Square` to keep its output stable.</span></span>
<span data-ttu-id="564f1-294">因此，将尽可能多的传统逻辑隔离到函数中，可以轻松地在其他函数和操作中重复使用该逻辑。</span><span class="sxs-lookup"><span data-stu-id="564f1-294">Thus, isolating as much classical logic as possible into functions makes it easy to reuse that logic in other functions and operations alike.</span></span>


## <a name="generic-type-parameterized-callables"></a><span data-ttu-id="564f1-295">泛型 (类型参数化) Callables</span><span class="sxs-lookup"><span data-stu-id="564f1-295">Generic (Type-Parameterized) Callables</span></span>

<span data-ttu-id="564f1-296">您可能想要定义的许多函数和操作实际上不依赖于其输入的类型，而只是通过其他函数或操作隐式使用其类型。</span><span class="sxs-lookup"><span data-stu-id="564f1-296">Many functions and operations that you might wish to define do not actually heavily rely on the types of their inputs, but rather only implicitly use their types via some other function or operation.</span></span>
<span data-ttu-id="564f1-297">例如，请考虑许多功能语言共有的*地图*概念;给定函数 $f (x) $ 和值的集合 $ \{ x_1，x_2，\dots ..，x_n \} $，map 将返回一个新的集合 $ f (x_1)  (x_2)  (\{ \} $。</span><span class="sxs-lookup"><span data-stu-id="564f1-297">For example, consider the *map* concept common to many functional languages; given a function $f(x)$ and a collection of values $\{x_1, x_2, \dots, x_n\}$, map returns a new collection $\{f(x_1), f(x_2), \dots, f(x_n)\}$.</span></span>
<span data-ttu-id="564f1-298">若要在中实现此 Q# 功能，请利用函数是第一类这一事实。</span><span class="sxs-lookup"><span data-stu-id="564f1-298">To implement this in Q#, take advantage of the fact that functions are first class.</span></span>
<span data-ttu-id="564f1-299">下面是的一个快速示例 `Map` ，使用 `T` 作为占位符，同时找出所需的类型。</span><span class="sxs-lookup"><span data-stu-id="564f1-299">Here is a quick example of `Map`, using `T` as a placeholder while you figure out what types you need.</span></span>

```qsharp
function Map(fn : (T -> T), values : T[]) : T[] {
    mutable mappedValues = new T[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="564f1-300">请注意，无论替换的实际类型是什么，此函数的外观都是相同的。</span><span class="sxs-lookup"><span data-stu-id="564f1-300">Note that this function looks very much the same no matter what actual types you substitute in.</span></span>
<span data-ttu-id="564f1-301">例如，从整数到 Paulis 的映射与从浮点数到字符串的映射大致相同：</span><span class="sxs-lookup"><span data-stu-id="564f1-301">A map from integers to Paulis, for instance, looks much the same as a map from floating-point numbers to strings:</span></span>

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

<span data-ttu-id="564f1-302">原则上，你可以 `Map` 为你遇到的每对类型编写一个版本，但这会带来一些困难。</span><span class="sxs-lookup"><span data-stu-id="564f1-302">In principle, you could write a version of `Map` for every pair of types that you encounter, but this introduces several difficulties.</span></span>
<span data-ttu-id="564f1-303">例如，如果在中发现 bug，则 `Map` 必须确保在的所有版本中统一应用此修补程序 `Map` 。</span><span class="sxs-lookup"><span data-stu-id="564f1-303">For instance, if you find a bug in `Map`, then you must ensure that the fix is applied uniformly across all versions of `Map`.</span></span>
<span data-ttu-id="564f1-304">此外，如果您构造新的元组或 UDT，则您现在必须构造一个新的 `Map` 来与新类型一起工作。</span><span class="sxs-lookup"><span data-stu-id="564f1-304">Moreover, if you construct a new tuple or UDT, then you must now also construct a new `Map` to go along with the new type.</span></span>
<span data-ttu-id="564f1-305">虽然这对于少量此类函数是易的，但当你收集与相同窗体的更多函数时， `Map` 引入新类型的成本将以相当短的顺序变为太。</span><span class="sxs-lookup"><span data-stu-id="564f1-305">While this is tractable for a small number of such functions, as you collect more and more functions of the same form as `Map`, the cost of introducing new types becomes unreasonably large in fairly short order.</span></span>

<span data-ttu-id="564f1-306">但是，这种情况很难产生这种情况，因为您没有为编译器提供所需的信息来识别的不同版本 `Map` 是如何相关的。</span><span class="sxs-lookup"><span data-stu-id="564f1-306">However, much of this difficulty results from the fact that you have not given the compiler the information it needs to recognize how the different versions of `Map` are related.</span></span>
<span data-ttu-id="564f1-307">实际上，你希望编译器将 `Map` 类型中的某种数学函数视为 Q# *types* Q# 函数。</span><span class="sxs-lookup"><span data-stu-id="564f1-307">Effectively, you want the compiler to treat `Map` as some kind of mathematical function from Q# *types* to Q# functions.</span></span>

<span data-ttu-id="564f1-308">Q#通过允许函数和操作具有*类型参数*，以及其普通元组参数，实现了这一概念的形式。</span><span class="sxs-lookup"><span data-stu-id="564f1-308">Q# formalizes this notion by allowing functions and operations to have *type parameters*, as well as their ordinary tuple parameters.</span></span>
<span data-ttu-id="564f1-309">在前面的示例中，您希望在 `Map` 第一种情况下将类型形参视为 `Int, Pauli` ， `Double, String` 在第二种情况下。</span><span class="sxs-lookup"><span data-stu-id="564f1-309">In the previous examples, you wish to think of `Map` as having type parameters `Int, Pauli` in the first case and `Double, String` in the second case.</span></span>
<span data-ttu-id="564f1-310">大多数情况下，使用这些类型参数，如同它们是普通类型。</span><span class="sxs-lookup"><span data-stu-id="564f1-310">For the most part, use these type parameters as though they were ordinary types.</span></span> <span data-ttu-id="564f1-311">使用类型参数的值来生成数组和元组，调用函数和操作，并将其分配给普通或可变变量。</span><span class="sxs-lookup"><span data-stu-id="564f1-311">Use values of type parameters to make arrays and tuples, call functions and operations, and assign to ordinary or mutable variables.</span></span>

> [!NOTE]
> <span data-ttu-id="564f1-312">间接依赖关系的最极端情况是 qubits，其中 Q# 程序不能直接依赖类型的结构， `Qubit` 而是**必须**将此类类型传递给其他操作和函数。</span><span class="sxs-lookup"><span data-stu-id="564f1-312">The most extreme case of indirect dependence is that of qubits, where a Q# program cannot directly rely on the structure of the `Qubit` type but **must** pass such types to other operations and functions.</span></span>

<span data-ttu-id="564f1-313">返回到前面的示例，然后您将看到 `Map` 需要具有类型参数，一个用于表示输入，另一个用于 `fn` 表示的输出 `fn` 。</span><span class="sxs-lookup"><span data-stu-id="564f1-313">Returning to the earlier example, then, you see that `Map` needs to have type parameters, one to represent the input to `fn` and one to represent the output from `fn`.</span></span>
<span data-ttu-id="564f1-314">在中 Q# ，通过在 `<>` 其声明中的函数或操作的名称后面添加尖括号 (（而不是 brakets $ \braket {} $！ ) ），并列出每个类型参数来编写这种情况。</span><span class="sxs-lookup"><span data-stu-id="564f1-314">In Q#, this is written by adding angle brackets (that's `<>`, not brakets $\braket{}$!) after the name of a function or operation in its declaration, and by listing each type parameter.</span></span>
<span data-ttu-id="564f1-315">每个类型形参的名称必须以计时周期开始 `'` ，这表示它是一个类型形参，而不是一个普通类型 (也称为) 的*具体*类型。</span><span class="sxs-lookup"><span data-stu-id="564f1-315">The name of each type parameter must start with a tick `'`, indicating that it is a type parameter and not a ordinary type (also known as a *concrete* type).</span></span>
<span data-ttu-id="564f1-316">因此， `Map` 将编写：</span><span class="sxs-lookup"><span data-stu-id="564f1-316">Thus, `Map`, is written:</span></span>

```qsharp
function Map<'Input, 'Output>(fn : ('Input -> 'Output), values : 'Input[]) : 'Output[] {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="564f1-317">请注意，的定义 `Map<'Input, 'Output>` 看起来非常类似于 previoius 版本。</span><span class="sxs-lookup"><span data-stu-id="564f1-317">Note that the definition of `Map<'Input, 'Output>` looks extremely similar to the previoius versions.</span></span>
<span data-ttu-id="564f1-318">唯一的不同之处在于，你已明确通知编译器 `Map` 不直接依赖哪些内容 `'Input` `'Output` ，但通过间接通过使用这两种类型来实现这一功能 `fn` 。</span><span class="sxs-lookup"><span data-stu-id="564f1-318">The only difference is that you have explicitly informed the compiler that `Map` doesn't directly depend on what `'Input` and `'Output` are, but works for any two types by using them indirectly through `fn`.</span></span>
<span data-ttu-id="564f1-319">`Map<'Input, 'Output>`通过这种方式定义后，可以像调用普通函数一样调用它：</span><span class="sxs-lookup"><span data-stu-id="564f1-319">Once you have defined `Map<'Input, 'Output>` in this way, you can call it as though it was an ordinary function:</span></span>

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> <span data-ttu-id="564f1-320">编写泛型函数和操作是一个位置，其中 "元组 out" 是一种非常有用的方法，用于考虑 Q# 函数和操作。</span><span class="sxs-lookup"><span data-stu-id="564f1-320">Writing generic functions and operations is one place where "tuple-in tuple-out" is a very useful way to think about Q# functions and operations.</span></span>
> <span data-ttu-id="564f1-321">由于每个函数只采用一个输入并返回一个输出，因此类型的输入 `'T -> 'U` 与*任何* Q# 函数都匹配。</span><span class="sxs-lookup"><span data-stu-id="564f1-321">Since every function takes exactly one input and returns exactly one output, an input of type `'T -> 'U` matches *any* Q# function whatsoever.</span></span>
> <span data-ttu-id="564f1-322">同样，可以将任何操作传递到类型为的输入 `'T => 'U` 。</span><span class="sxs-lookup"><span data-stu-id="564f1-322">Similarly, you can pass any operation to an input of type `'T => 'U`.</span></span>

<span data-ttu-id="564f1-323">作为第二个示例，请考虑编写一个函数，该函数返回两个其他函数的组合：</span><span class="sxs-lookup"><span data-stu-id="564f1-323">As a second example, consider the challenge of writing a function that returns the composition of two other functions:</span></span>

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="564f1-324">在此，您必须指定确切的 `A` 、 `B` 和， `C` 从而严格限制新函数的实用工具 `Compose` 。</span><span class="sxs-lookup"><span data-stu-id="564f1-324">Here, you must specify exactly what `A`, `B`, and `C` are, hence severely limiting the utility of our new `Compose` function.</span></span>
<span data-ttu-id="564f1-325">毕竟， `Compose` 只依赖于 `A` 、和， `B` 并 `C` *通过* `innerFn` 和 `outerFn` 。</span><span class="sxs-lookup"><span data-stu-id="564f1-325">After all, `Compose` only depends on `A`, `B`, and `C` *via* `innerFn` and `outerFn`.</span></span>
<span data-ttu-id="564f1-326">作为替代方法，可以将类型参数添加到 `Compose` ，这表示它适用于*任何* `A` 、 `B` 和 `C` ，前提是这些参数与和所需的参数匹配 `innerFn` `outerFn` ：</span><span class="sxs-lookup"><span data-stu-id="564f1-326">As an alternative, then, you can add type parameters to `Compose` that indicate that it works for *any* `A`, `B`, and `C`, so long as these parameters match those expected by `innerFn` and `outerFn`:</span></span>

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="564f1-327">Q#标准库提供了一系列这样的类型参数化操作和函数，使更高顺序控制流更易于表达。</span><span class="sxs-lookup"><span data-stu-id="564f1-327">The Q# standard libraries provide a range of such type-parameterized operations and functions to make higher-order control flow easier to express.</span></span>
<span data-ttu-id="564f1-328">[ Q# 标准库指南](xref:microsoft.quantum.libraries.standard.intro)中进一步讨论了这些情况。</span><span class="sxs-lookup"><span data-stu-id="564f1-328">These are discussed further in the [Q# standard library guide](xref:microsoft.quantum.libraries.standard.intro).</span></span>


## <a name="callables-as-first-class-values"></a><span data-ttu-id="564f1-329">Callables 作为第一类值</span><span class="sxs-lookup"><span data-stu-id="564f1-329">Callables as First-Class Values</span></span>

<span data-ttu-id="564f1-330">使用函数（而不是操作）对控制流和传统逻辑的推理的一项重要技巧是，使用中的操作和函数是 Q# *第一类*。</span><span class="sxs-lookup"><span data-stu-id="564f1-330">One critical technique for reasoning about control flow and classical logic using functions rather than operations is to utilize that operations and functions in Q# are *first-class*.</span></span>
<span data-ttu-id="564f1-331">也就是说，它们本身就是语言中的每个值。</span><span class="sxs-lookup"><span data-stu-id="564f1-331">That is, they are each values in the language in their own right.</span></span>
<span data-ttu-id="564f1-332">例如，下面是一个非常有效的 Q# 代码，如果是间接的：</span><span class="sxs-lookup"><span data-stu-id="564f1-332">For instance, the following is perfectly valid Q# code, if a little indirect:</span></span>

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

<span data-ttu-id="564f1-333">`ourH`上一个代码段中的变量的值就是操作 <xref:microsoft.quantum.intrinsic.h> ，因此可以像任何其他操作一样调用该值。</span><span class="sxs-lookup"><span data-stu-id="564f1-333">The value of the variable `ourH` in the previous snippet is then the operation <xref:microsoft.quantum.intrinsic.h>, such that you can call that value like any other operation.</span></span>
<span data-ttu-id="564f1-334">利用此功能，您可以编写将操作作为其输入的一部分执行的操作，形成更高顺序的控制流概念。</span><span class="sxs-lookup"><span data-stu-id="564f1-334">With this ability, you can write operations that take operations as a part of their input, forming higher-order control flow concepts.</span></span>
<span data-ttu-id="564f1-335">例如，你可能想要通过将其应用到同一个目标 qubit 来 "正方形" 的操作。</span><span class="sxs-lookup"><span data-stu-id="564f1-335">For instance, you could imagine wanting to "square" an operation by applying it twice to the same target qubit.</span></span>

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

### <a name="returning-operations-from-a-function"></a><span data-ttu-id="564f1-336">从函数返回操作</span><span class="sxs-lookup"><span data-stu-id="564f1-336">Returning operations from a function</span></span>

<span data-ttu-id="564f1-337">必须强调的是，您还可以在输出过程中返回操作，以便可以将某些类型的传统条件逻辑隔离为传统函数，这将以操作的形式返回量程程序的说明。</span><span class="sxs-lookup"><span data-stu-id="564f1-337">It's important to emphasize that you can also return operations as a part of outputs, such that you can isolate some kinds of classical conditional logic as a classical function, which returns a description of a quantum program in the form of an operation.</span></span>
<span data-ttu-id="564f1-338">作为一个简单的示例，请考虑 teleportation 示例，在该示例中，接收两位传统消息的参与方需要使用该消息将其 qubit 解码为正确的 teleported 状态。</span><span class="sxs-lookup"><span data-stu-id="564f1-338">As a simple example, consider the teleportation example, in which the party receiving a two-bit classical message needs to use the message to decode their qubit into the proper teleported state.</span></span>
<span data-ttu-id="564f1-339">您可以编写一个函数，该函数采用这两个传统位并返回正确的解码操作。</span><span class="sxs-lookup"><span data-stu-id="564f1-339">You could write this in terms of a function that takes those two classical bits and returns the proper decoding operation.</span></span>

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

<span data-ttu-id="564f1-340">此新函数确实是一个函数，在这种情况下，如果使用和的相同值调用该函数 `hereBit` `thereBit` ，则总是返回相同的操作。</span><span class="sxs-lookup"><span data-stu-id="564f1-340">This new function is indeed a function, in that if you call it with the same values of `hereBit` and `thereBit`, you always get back the same operation.</span></span>
<span data-ttu-id="564f1-341">这样，解码器就可以安全地在操作内运行，而无需考虑解码逻辑如何与不同操作专用化的定义进行交互。</span><span class="sxs-lookup"><span data-stu-id="564f1-341">Thus, the decoder can safely run inside operations without having to reason about how the decoding logic interacts with the definitions of the different operation specializations.</span></span>
<span data-ttu-id="564f1-342">也就是说，函数内的传统逻辑是独立的，从而保证编译器函数调用可以与 impunity 重新排序，只要输入已保留。</span><span class="sxs-lookup"><span data-stu-id="564f1-342">That is, the classical logic inside a function is isolated, guaranteeing to the compiler that the function call can be reordered with impunity so long as the input is preserved.</span></span>


## <a name="partial-application"></a><span data-ttu-id="564f1-343">部分应用程序</span><span class="sxs-lookup"><span data-stu-id="564f1-343">Partial Application</span></span>

<span data-ttu-id="564f1-344">通过使用*部分应用程序*返回操作的函数，你可以更多地执行此操作，在该应用程序中，你可以向函数或操作提供一个或多个输入部分，而无需实际调用它。</span><span class="sxs-lookup"><span data-stu-id="564f1-344">You can do significantly more with functions that return operations by using *partial application*, in which you provide one or more parts of the input to a function or operation without actually calling it.</span></span> <span data-ttu-id="564f1-345">在前面的 `ApplyTwice` 示例中，您可以指示您不希望立即指定输入操作应应用到的 qubit：</span><span class="sxs-lookup"><span data-stu-id="564f1-345">In the earlier `ApplyTwice` example, you can indicate that you don't want to specify, right away, to which qubit the input operation should apply:</span></span>

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

<span data-ttu-id="564f1-346">在这种情况下，局部变量 `twiceOp` 包含部分应用的操作 `ApplyTwice(op, _)` ，其中 `_` 指示输入中尚未指定的部分。</span><span class="sxs-lookup"><span data-stu-id="564f1-346">In this case, the local variable `twiceOp` holds the partially applied operation `ApplyTwice(op, _)`, where `_` indicates parts of the input that have not yet been specified.</span></span>
<span data-ttu-id="564f1-347">`twiceOp`在下一行中调用时，会将输入的所有剩余部分作为初始操作的所有剩余部分传递给部分应用的操作。</span><span class="sxs-lookup"><span data-stu-id="564f1-347">When you call `twiceOp` in the next line, you pass as input to the partially applied operation all of the remaining parts of the input to the original operation.</span></span>
<span data-ttu-id="564f1-348">因此，前面的代码段与直接调用相同 `ApplyTwice(op, target)` ，因为您引入了一个新的局部变量，因此您可以延迟调用，同时提供输入的某些部分。</span><span class="sxs-lookup"><span data-stu-id="564f1-348">Thus, the previous snippet is effectively identical to having called `ApplyTwice(op, target)` directly, save for that you have introduced a new local variable so you can delay the call while providing some parts of the input.</span></span>

<span data-ttu-id="564f1-349">由于未实际调用已部分应用的操作，在提供其整个输入之前，可以安全地部分应用操作，即使是在函数内。</span><span class="sxs-lookup"><span data-stu-id="564f1-349">Since an operation that has been partially applied is not actually called until its entire input has been provided, you can safely partially apply operations even from within functions.</span></span>

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

<span data-ttu-id="564f1-350">原则上，中的传统逻辑 `SquareOperation` 可能会更多地涉及到，但它仍与操作的其余部分隔离，因为编译器可以提供函数。</span><span class="sxs-lookup"><span data-stu-id="564f1-350">In principle, the classical logic within `SquareOperation` could have been much more involved, but it is still isolated from the rest of an operation by the guarantees that the compiler can offer about functions.</span></span> <span data-ttu-id="564f1-351">Q#标准库在整个过程中都使用这种方法，以一种可让量子程序随时使用的方式表示传统的控制流。</span><span class="sxs-lookup"><span data-stu-id="564f1-351">The Q# standard library uses this approach throughout for expressing classical control flow in a way that quantum programs can readily use.</span></span>


## <a name="recursion"></a><span data-ttu-id="564f1-352">递归</span><span class="sxs-lookup"><span data-stu-id="564f1-352">Recursion</span></span>

<span data-ttu-id="564f1-353">Q#允许直接或间接递归 callables。</span><span class="sxs-lookup"><span data-stu-id="564f1-353">Q# callables are allowed to be directly or indirectly recursive.</span></span>
<span data-ttu-id="564f1-354">也就是说，操作或函数可以调用自身，也可以调用可直接或间接调用可调用操作的另一个可调用的。</span><span class="sxs-lookup"><span data-stu-id="564f1-354">That is, an operation or function can call itself, or it can call another callable that directly or indirectly calls the callable operation.</span></span>

<span data-ttu-id="564f1-355">不过，有两个关于递归使用的重要说明：</span><span class="sxs-lookup"><span data-stu-id="564f1-355">There are two important comments about the use of recursion, however:</span></span>

- <span data-ttu-id="564f1-356">在操作中使用递归可能会干扰某些优化。</span><span class="sxs-lookup"><span data-stu-id="564f1-356">The use of recursion in operations is likely to interfere with certain optimizations.</span></span>
  <span data-ttu-id="564f1-357">此干扰可能会对算法的执行时间产生重大影响。</span><span class="sxs-lookup"><span data-stu-id="564f1-357">This interference can have a substantial impact on the execution time of the algorithm.</span></span>
- <span data-ttu-id="564f1-358">在实际的量程设备上运行时，堆栈空间可能会受到限制，因此深度递归可能导致运行时错误。</span><span class="sxs-lookup"><span data-stu-id="564f1-358">When running on an actual quantum device, stack space might be limited, and so deep recursion can lead to a runtime error.</span></span>
  <span data-ttu-id="564f1-359">具体而言， Q# 编译器和运行时不会标识和优化尾递归。</span><span class="sxs-lookup"><span data-stu-id="564f1-359">In particular, the Q# compiler and runtime do not identify and optimize tail recursion.</span></span>

## <a name="next-steps"></a><span data-ttu-id="564f1-360">后续步骤</span><span class="sxs-lookup"><span data-stu-id="564f1-360">Next steps</span></span>

<span data-ttu-id="564f1-361">了解中[Variables](xref:microsoft.quantum.guide.variables)的变量 Q# 。</span><span class="sxs-lookup"><span data-stu-id="564f1-361">Learn about [Variables](xref:microsoft.quantum.guide.variables) in Q#.</span></span>