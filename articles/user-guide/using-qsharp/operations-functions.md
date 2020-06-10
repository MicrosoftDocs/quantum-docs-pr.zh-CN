---
title: 问答中的操作和函数#
description: 如何定义和调用操作和函数，以及受控和 adjoint 操作专用化。
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.operationsfunctions
ms.openlocfilehash: 6cfc1b14d86e86a1cbf0109d5e81dfe50c3a80bf
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630215"
---
# <a name="operations-and-functions-in-q"></a><span data-ttu-id="1bffb-103">问答中的操作和函数#</span><span class="sxs-lookup"><span data-stu-id="1bffb-103">Operations and Functions in Q#</span></span>

## <a name="defining-new-operations"></a><span data-ttu-id="1bffb-104">定义新操作</span><span class="sxs-lookup"><span data-stu-id="1bffb-104">Defining New Operations</span></span>

<span data-ttu-id="1bffb-105">操作是 Q # 的核心。</span><span class="sxs-lookup"><span data-stu-id="1bffb-105">Operations are the core of Q#.</span></span>
<span data-ttu-id="1bffb-106">声明后，可以从传统 .NET 应用程序（例如，使用模拟器）调用，也可以由 Q # 内的其他操作调用。</span><span class="sxs-lookup"><span data-stu-id="1bffb-106">Once declared, they can either be called from classical .NET applications, e.g., using a simulator, or by other operations within Q#.</span></span>
<span data-ttu-id="1bffb-107">在 Q # 中定义的每个操作都可以调用任意数量的其他操作，包括由语言定义的内置内部操作。</span><span class="sxs-lookup"><span data-stu-id="1bffb-107">Each operation defined in Q# may then call any number of other operations, including the built-in intrinsic operations defined by the language.</span></span> <span data-ttu-id="1bffb-108">定义这些内部操作的特定方式取决于目标计算机。</span><span class="sxs-lookup"><span data-stu-id="1bffb-108">The particular way in which these intrinsic operations are defined depends on the target machine.</span></span>
<span data-ttu-id="1bffb-109">在编译时，每个操作都表示为可提供给目标计算机的 .NET 类类型。</span><span class="sxs-lookup"><span data-stu-id="1bffb-109">When compiled, each operation is represented as a .NET class type that can be provided to target machines.</span></span>

<span data-ttu-id="1bffb-110">每个 Q # 源文件可以定义任意数量的操作。</span><span class="sxs-lookup"><span data-stu-id="1bffb-110">Each Q# source file may define any number of operations.</span></span>
<span data-ttu-id="1bffb-111">操作名称在命名空间中必须唯一，并且不能与类型或函数名冲突。</span><span class="sxs-lookup"><span data-stu-id="1bffb-111">Operation names must be unique within a namespace and may not conflict with type or function names.</span></span>

<span data-ttu-id="1bffb-112">操作声明由关键字组成 `operation` ，后跟作为操作名称的符号、定义操作的参数的类型化标识符元组、冒号 `:` 、描述操作结果类型的类型批注、有操作特征的批注、左大括号 `{` 、操作声明的正文和最终右大括号 `}` 。</span><span class="sxs-lookup"><span data-stu-id="1bffb-112">An operation declaration consists of the keyword `operation`, followed by the symbol that is the operation's name, a typed identifier tuple that defines the arguments to the operation, a colon `:`, a type annotation that describes the operation's result type, optionally an annotation with the operation characteristics, an open brace `{`, the body of the operation declaration, and a final closing brace `}`.</span></span>

<span data-ttu-id="1bffb-113">每个操作都使用一个输入，生成一个输出，并为一个或多个专用操作指定实现。</span><span class="sxs-lookup"><span data-stu-id="1bffb-113">Each operation takes an input, produces an output, and specifies the implementation for one or more operation specializations.</span></span>
<span data-ttu-id="1bffb-114">下面详细说明了可能的专用化，以及如何定义/调用它们。</span><span class="sxs-lookup"><span data-stu-id="1bffb-114">The possible specializations, and how to define/call them, are detailed further below.</span></span>
<span data-ttu-id="1bffb-115">现在，请考虑以下操作，该操作仅定义默认的主体特殊化并使用单个 qubit 作为其输入，然后对 <xref:microsoft.quantum.intrinsic.x> 该输入调用内置操作：</span><span class="sxs-lookup"><span data-stu-id="1bffb-115">For now, consider the following operation, which defines only a default body specialization and takes a single qubit as its input, then calls the built-in <xref:microsoft.quantum.intrinsic.x> operation on that input:</span></span>

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

<span data-ttu-id="1bffb-116">关键字将 `operation` 开始操作定义，后跟名称; 此处为 `BitFlip` 。</span><span class="sxs-lookup"><span data-stu-id="1bffb-116">The keyword `operation` begins the operation definition, and is followed by the name; here, `BitFlip`.</span></span>
<span data-ttu-id="1bffb-117">接下来，输入的类型定义为，并 `Qubit` 将定义为 `target` 在新操作中引用输入。</span><span class="sxs-lookup"><span data-stu-id="1bffb-117">Next, the type of the input is defined as `Qubit`, along with a name `target` for referring to the input within the new operation.</span></span>
<span data-ttu-id="1bffb-118">同样， `Unit` 定义操作的输出为空。</span><span class="sxs-lookup"><span data-stu-id="1bffb-118">Similarly, the `Unit` defines that the operation's output is empty.</span></span>
<span data-ttu-id="1bffb-119">这类似于 `void` c # 和其他命令式语言，与 `unit` F # 和其他功能语言等效。</span><span class="sxs-lookup"><span data-stu-id="1bffb-119">This is used similarly to `void` in C# and other imperative languages, and is equivalent to `unit` in F# and other functional languages.</span></span>

<span data-ttu-id="1bffb-120">操作还可以返回比更有趣 `Unit` 的类型。</span><span class="sxs-lookup"><span data-stu-id="1bffb-120">Operations can also return more interesting types than `Unit`.</span></span>
<span data-ttu-id="1bffb-121">例如， <xref:microsoft.quantum.intrinsic.m> 操作返回类型的输出，该输出 `Result` 表示已执行了一个度量值。</span><span class="sxs-lookup"><span data-stu-id="1bffb-121">For instance, the <xref:microsoft.quantum.intrinsic.m> operation returns an output of type `Result`, representing having performed a measurement.</span></span> <span data-ttu-id="1bffb-122">我们可以将操作的输出传递给另一个操作，也可以将其与关键字一起使用 `let` 来定义新变量。</span><span class="sxs-lookup"><span data-stu-id="1bffb-122">We can either pass the output from an operation to another operation, or can use it with the `let` keyword to define a new variable.</span></span>

<span data-ttu-id="1bffb-123">这允许表示在较低级别与量程操作交互的传统计算，如[superdense 编码](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding)：</span><span class="sxs-lookup"><span data-stu-id="1bffb-123">This allows for representing classical computation that interacts with quantum operations at a low level, such as in [superdense coding](https://github.com/microsoft/QuantumKatas/tree/master/SuperdenseCoding):</span></span>

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
> <span data-ttu-id="1bffb-124">Q # 中的每个操作都只采用一个输入，并只返回一个输出。</span><span class="sxs-lookup"><span data-stu-id="1bffb-124">Each operation in Q# takes exactly one input and returns exactly one output.</span></span>
> <span data-ttu-id="1bffb-125">然后使用*元组*表示多个输入和输出，并将多个值一起收集到单个值中。</span><span class="sxs-lookup"><span data-stu-id="1bffb-125">Multiple inputs and outputs are then represented using *tuples*, which collect multiple values together into a single value.</span></span>
> <span data-ttu-id="1bffb-126">非正式地说，Q # 是一种 "元组 out" 语言。</span><span class="sxs-lookup"><span data-stu-id="1bffb-126">Informally, we say that Q# is a "tuple-in tuple-out" language.</span></span>
> <span data-ttu-id="1bffb-127">遵循此概念后， `()` 应将其作为 "empty" 元组（类型为）进行读取 `Unit` 。</span><span class="sxs-lookup"><span data-stu-id="1bffb-127">Following this concept, `()` should then be read as the "empty" tuple, which has the type `Unit`.</span></span>


## <a name="controlled-and-adjoint-operations"></a><span data-ttu-id="1bffb-128">受控和 Adjoint 操作</span><span class="sxs-lookup"><span data-stu-id="1bffb-128">Controlled and Adjoint Operations</span></span>

<span data-ttu-id="1bffb-129">如果某个操作实现了单一转换（如 Q # 中的多个操作），则可以定义操作在*adjointed*或*控制*时的行为方式。</span><span class="sxs-lookup"><span data-stu-id="1bffb-129">If an operation implements a unitary transformation, as is the case for many operations in Q#, then it is possible to define how the operation acts when *adjointed* or *controlled*.</span></span> <span data-ttu-id="1bffb-130">操作的*adjoint*专用化指定操作的 "反转" 的行为方式，而*受控*专用化指定操作在其应用程序的应用程序在特定量程寄存器状态下运行时的行为方式。</span><span class="sxs-lookup"><span data-stu-id="1bffb-130">An *adjoint* specialization of an operation specifies how the "inverse" of the operation acts, while a *controlled* specialization specifies how an operation acts when its application is conditioned on the state of a particular quantum register.</span></span>

<span data-ttu-id="1bffb-131">量程操作的 Adjoints 对量程计算的许多方面都至关重要。</span><span class="sxs-lookup"><span data-stu-id="1bffb-131">Adjoints of quantum operations are crucial to many aspects of quantum computing.</span></span> <span data-ttu-id="1bffb-132">接下来，在 "[语态](#conjugations)" 部分中，你将发现一种此类情况与有用的 Q # 编程方法一起讨论。</span><span class="sxs-lookup"><span data-stu-id="1bffb-132">Further below, in the [Conjugations](#conjugations) section, you will find one such situation discussed alongside a useful Q# programming technique.</span></span>

<span data-ttu-id="1bffb-133">操作的受控版本是新操作，仅当所有控件 qubits 都处于指定状态时，才会有效地应用基本操作。</span><span class="sxs-lookup"><span data-stu-id="1bffb-133">The controlled version of an operation is a new operation that effectively applies the base operation only if all of the control qubits are in a specified state.</span></span>
<span data-ttu-id="1bffb-134">如果控件 qubits 在 superposition 中，则会将基本操作一致应用到 superposition 的相应部分。</span><span class="sxs-lookup"><span data-stu-id="1bffb-134">If the control qubits are in superposition, then the base operation is applied coherently to the appropriate part of the superposition.</span></span>
<span data-ttu-id="1bffb-135">因此，受控操作通常用于生成牵连。</span><span class="sxs-lookup"><span data-stu-id="1bffb-135">Thus, controlled operations are often used to generate entanglement.</span></span>

<span data-ttu-id="1bffb-136">当然，还可以使用*受控的 adjoint*特殊化来指定操作 adjoint 的受控应用。</span><span class="sxs-lookup"><span data-stu-id="1bffb-136">Naturally, a *controlled adjoint* specialization could exist as well, specifying the controlled application of an operation's adjoint.</span></span>

> [!NOTE]
> <span data-ttu-id="1bffb-137">如果 $U $ 是操作实现的单一转换 `U` ，则 `Adjoint U` 表示 $U ^ \dagger $ 的单一转换，这是复杂的共轭转置。</span><span class="sxs-lookup"><span data-stu-id="1bffb-137">If $U$ is the unitary transformation implemented by an operation `U`, then `Adjoint U` represents the unitary transformation $U^\dagger$, which is the complex conjugate transpose.</span></span>
> <span data-ttu-id="1bffb-138">依次应用某一操作，然后将其 adjoint 的状态保持不变，如 $UU ^ \dagger = U ^ \dagger U = \id $，则为恒等矩阵。</span><span class="sxs-lookup"><span data-stu-id="1bffb-138">Successively applying an operation and then its adjoint to a state leaves the state unchanged, as illustrated by the fact that $UU^\dagger = U^\dagger U = \id$, the identity matrix.</span></span>
> <span data-ttu-id="1bffb-139">受控操作的单一表示形式略微微妙，但可以在量程计算概念中找到更多详细信息[：多个 qubits](xref:microsoft.quantum.concepts.multiple-qubits)。</span><span class="sxs-lookup"><span data-stu-id="1bffb-139">The unitary representation of a controlled operation is slightly more nuanced, but you can find more details at [Quantum computing concepts: multiple qubits](xref:microsoft.quantum.concepts.multiple-qubits).</span></span>

<span data-ttu-id="1bffb-140">以下部分介绍如何在 Q # 代码中调用这些不同的专用化。</span><span class="sxs-lookup"><span data-stu-id="1bffb-140">The following section describes how to call these various specializations in your Q# code.</span></span>
<span data-ttu-id="1bffb-141">下面详细介绍了如何定义操作来支持它们。</span><span class="sxs-lookup"><span data-stu-id="1bffb-141">Below, we detail how to define operations to support them.</span></span>

### <a name="calling-operation-specializations"></a><span data-ttu-id="1bffb-142">调用专用操作</span><span class="sxs-lookup"><span data-stu-id="1bffb-142">Calling operation specializations</span></span>

<span data-ttu-id="1bffb-143">Q # 中的*函子*是一个工厂，它定义了其他操作的新操作。</span><span class="sxs-lookup"><span data-stu-id="1bffb-143">A *functor* in Q# is a factory that defines a new operation from another operation.</span></span>
<span data-ttu-id="1bffb-144">Q # 中的两个标准函子是 `Adjoint` 和 `Controlled` 。</span><span class="sxs-lookup"><span data-stu-id="1bffb-144">The two standard functors in Q# are `Adjoint` and `Controlled`.</span></span>

<span data-ttu-id="1bffb-145">在定义新操作的实现时，函子有权访问基操作的实现。</span><span class="sxs-lookup"><span data-stu-id="1bffb-145">Functors have access to the implementation of the base operation when defining the implementation of the new operation.</span></span>
<span data-ttu-id="1bffb-146">因此，函子可以比传统的高级函数执行更复杂的功能。</span><span class="sxs-lookup"><span data-stu-id="1bffb-146">Thus, functors can perform more complex functions than traditional higher-level functions.</span></span> <span data-ttu-id="1bffb-147">函子在 Q # 类型系统中没有表示形式。</span><span class="sxs-lookup"><span data-stu-id="1bffb-147">Functors do not have a representation in the Q# type system.</span></span> <span data-ttu-id="1bffb-148">因此，目前不可能将其绑定到变量或将其作为参数传递。</span><span class="sxs-lookup"><span data-stu-id="1bffb-148">It is thus currently not possible to bind them to a variable or pass them as arguments.</span></span> 

<span data-ttu-id="1bffb-149">函子可通过将其应用于操作来使用，返回新操作。</span><span class="sxs-lookup"><span data-stu-id="1bffb-149">A functor is used by applying it to an operation, returning a new operation.</span></span>
<span data-ttu-id="1bffb-150">例如，将 `Adjoint` 函子应用到操作后生成的操作 `Y` 将编写为 `Adjoint Y` 。</span><span class="sxs-lookup"><span data-stu-id="1bffb-150">For example, the operation that results from applying the `Adjoint` functor to the `Y` operation is written as `Adjoint Y`.</span></span>
<span data-ttu-id="1bffb-151">然后，可以像任何其他操作一样调用新操作。</span><span class="sxs-lookup"><span data-stu-id="1bffb-151">The new operation may then be invoked like any other operation.</span></span>
<span data-ttu-id="1bffb-152">对于支持 `Adjoint` 和/或函子的应用程序的操作 `Controlled` ，其返回类型必须为 `Unit` 。</span><span class="sxs-lookup"><span data-stu-id="1bffb-152">For an operation to support application of the `Adjoint` and/or `Controlled` functors, its return type necessarily needs to be `Unit`.</span></span> 

#### <a name="adjoint-functor"></a><span data-ttu-id="1bffb-153">`Adjoint`函子</span><span class="sxs-lookup"><span data-stu-id="1bffb-153">`Adjoint` functor</span></span>

<span data-ttu-id="1bffb-154">因此，将 `Adjoint Y(q1)` Adjoint 函子应用于 `Y` 操作以生成新的操作，并将该新操作应用于 `q1` 。</span><span class="sxs-lookup"><span data-stu-id="1bffb-154">Thus, `Adjoint Y(q1)` applies the Adjoint functor to the `Y` operation to generate a new operation, and applies that new operation to `q1`.</span></span>
<span data-ttu-id="1bffb-155">新操作与基本操作具有相同的签名和类型 `Y` 。</span><span class="sxs-lookup"><span data-stu-id="1bffb-155">The new operation has the same signature and type as the base operation `Y`.</span></span>
<span data-ttu-id="1bffb-156">具体而言，新操作也允许 `Adjoint` ，并且 `Controlled` 仅当基本操作执行时才允许。</span><span class="sxs-lookup"><span data-stu-id="1bffb-156">In particular, the new operation also allows `Adjoint`, and will allow `Controlled` if and only if the base operation did.</span></span>
<span data-ttu-id="1bffb-157">Adjoint 函子是其自身的反向;也就是说， `Adjoint Adjoint Op` 始终与相同 `Op` 。</span><span class="sxs-lookup"><span data-stu-id="1bffb-157">The Adjoint functor is its own inverse; that is, `Adjoint Adjoint Op` is always the same as `Op`.</span></span>

#### <a name="controlled-functor"></a><span data-ttu-id="1bffb-158">`Controlled`函子</span><span class="sxs-lookup"><span data-stu-id="1bffb-158">`Controlled` functor</span></span>

<span data-ttu-id="1bffb-159">同样， `Controlled X(controls, target)` 将受控函子应用于 `X` 操作以生成新的操作，并将该新操作应用于 `controls` 和 `target` 。</span><span class="sxs-lookup"><span data-stu-id="1bffb-159">Similarly, `Controlled X(controls, target)` applies the Controlled functor to the `X` operation to generate a new operation, and applies that new operation to `controls` and `target`.</span></span>

> [!NOTE]
> <span data-ttu-id="1bffb-160">在 Q # 中，受控版本始终采用控件 qubits 的数组，并且指定的状态始终是所有控件 qubits 都处于计算（ `PauliZ` ） `One` 状态 $ \ket {1} $。</span><span class="sxs-lookup"><span data-stu-id="1bffb-160">In Q#, controlled versions always take an array of control qubits, and the specified state is always for all of the control qubits to be in the computational (`PauliZ`) `One` state, $\ket{1}$.</span></span>
> <span data-ttu-id="1bffb-161">可以通过将适当的单一操作应用于受控操作之前的控件 qubits 来实现基于其他状态的控制，然后在受控操作后应用单一操作的逆。</span><span class="sxs-lookup"><span data-stu-id="1bffb-161">Controlling based on other states may be achieved by applying the appropriate unitary operation to the control qubits before the controlled operation, and then applying the inverses of the unitary operation after the controlled operation.</span></span>
> <span data-ttu-id="1bffb-162">例如， `X` 将操作应用于受控操作前后的控件 qubit 会导致操作控制 `Zero` 该 qubit 的状态（$ \ket {0} $）; 应用 `H` 操作之前和之后，将控制该 `PauliX` `One` 状态，即-1 eigenvalue of Pauli X，$ \ket {-} \mathrel{： =} （\ket {0} -\ket {1} ）/\sqrt {2} $，而不是 `PauliZ` `One` 状态。</span><span class="sxs-lookup"><span data-stu-id="1bffb-162">For example, applying an `X` operation to a control qubit before and after a controlled operation will cause the operation to control on the `Zero` state ($\ket{0}$) for that qubit; applying an `H` operation before and after will control on the `PauliX` `One` state, that is -1 eigenvalue of Pauli X, $\ket{-} \mathrel{:=} (\ket{0} - \ket{1}) / \sqrt{2}$ rather than the `PauliZ` `One` state.</span></span>

<span data-ttu-id="1bffb-163">给定操作表达式，可以使用函子生成新的操作表达式 `Controlled` 。</span><span class="sxs-lookup"><span data-stu-id="1bffb-163">Given an operation expression, a new operation expression may be formed using the `Controlled` functor.</span></span>
<span data-ttu-id="1bffb-164">新操作的签名基于原始操作的签名。</span><span class="sxs-lookup"><span data-stu-id="1bffb-164">The signature of the new operation is based on the signature of the original operation.</span></span>
<span data-ttu-id="1bffb-165">结果类型是相同的，但输入类型是具有 qubit 数组的两元组，它将控件 qubit 保存为第一个元素，并将原始操作的参数作为第二个元素。</span><span class="sxs-lookup"><span data-stu-id="1bffb-165">The result type is the same, but the input type is a two-tuple with a qubit array that holds the control qubit(s) as the first element and the arguments of the original operation as the second element.</span></span>
<span data-ttu-id="1bffb-166">新操作支持 `Controlled` ，且 `Adjoint` 仅当原始操作执行时才支持。</span><span class="sxs-lookup"><span data-stu-id="1bffb-166">The new operation supports `Controlled`, and will support `Adjoint` if and only if the original operation did.</span></span>

<span data-ttu-id="1bffb-167">如果原始操作只使用了一个参数，则会在此处播放单独的元组等效性。</span><span class="sxs-lookup"><span data-stu-id="1bffb-167">If the original operation took only a single argument, then singleton tuple equivalence will come into play here.</span></span>
<span data-ttu-id="1bffb-168">例如， `Controlled X` 是操作的受控版本 `X` 。</span><span class="sxs-lookup"><span data-stu-id="1bffb-168">For instance, `Controlled X` is the controlled version of the `X` operation.</span></span> 
<span data-ttu-id="1bffb-169">`X`具有类型 `(Qubit => Unit is Adj + Ctl)` ，因此 `Controlled X` 具有类型 `((Qubit[], (Qubit)) => Unit is Adj + Ctl)` ; 由于单一元组等效，这与相同 `((Qubit[], Qubit) => Unit is Adj + Ctl)` 。</span><span class="sxs-lookup"><span data-stu-id="1bffb-169">`X` has type `(Qubit => Unit is Adj + Ctl)`, so `Controlled X` has type `((Qubit[], (Qubit)) => Unit is Adj + Ctl)`; because of singleton tuple equivalence, this is the same as `((Qubit[], Qubit) => Unit is Adj + Ctl)`.</span></span>

<span data-ttu-id="1bffb-170">如果基本操作采用多个参数，请记住将操作的受控版本的相应参数括在括号中，以将其转换为元组。</span><span class="sxs-lookup"><span data-stu-id="1bffb-170">If the base operation took several arguments, remember to enclose the corresponding arguments of the controlled version of the operation in parentheses to convert them into a tuple.</span></span>
<span data-ttu-id="1bffb-171">例如， `Controlled Rz` 是操作的受控版本 `Rz` 。</span><span class="sxs-lookup"><span data-stu-id="1bffb-171">For instance, `Controlled Rz` is the controlled version of the `Rz` operation.</span></span> 
<span data-ttu-id="1bffb-172">`Rz`具有类型 `((Double, Qubit) => Unit is Adj + Ctl)` ，因此 `Controlled Rz` 具有类型 `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)` 。</span><span class="sxs-lookup"><span data-stu-id="1bffb-172">`Rz` has type `((Double, Qubit) => Unit is Adj + Ctl)`, so `Controlled Rz` has type `((Qubit[], (Double, Qubit)) => Unit is Adj + Ctl)`.</span></span>
<span data-ttu-id="1bffb-173">因此，将 `Controlled Rz(controls, (0.1, target))` 是的有效调用 `Controlled Rz` （请注意两边的括号 `0.1, target` ）。</span><span class="sxs-lookup"><span data-stu-id="1bffb-173">Thus, `Controlled Rz(controls, (0.1, target))` would be a valid invocation of `Controlled Rz` (note the parentheses around `0.1, target`).</span></span>

<span data-ttu-id="1bffb-174">作为另一个示例， `CNOT(control, target)` 可以实现为 `Controlled X([control], target)` 。</span><span class="sxs-lookup"><span data-stu-id="1bffb-174">As another example, `CNOT(control, target)` can be implemented as `Controlled X([control], target)`.</span></span> <span data-ttu-id="1bffb-175">如果目标应由2个 control qubits （CCNOT）控制，则可以使用 `Controlled X([control1, control2], target)` 语句。</span><span class="sxs-lookup"><span data-stu-id="1bffb-175">If a target should be controlled by 2 control qubits (CCNOT), we can use `Controlled X([control1, control2], target)` statement.</span></span>

#### `Controlled Adjoint` 

<span data-ttu-id="1bffb-176">`Controlled`和 `Adjoint` 函子的上下班，因此应用或之间没有区别 `Controlled Adjoint Op` `Adjoint Controlled Op` 。</span><span class="sxs-lookup"><span data-stu-id="1bffb-176">The `Controlled` and `Adjoint` functors commute, so there is no difference between applying `Controlled Adjoint Op` or `Adjoint Controlled Op`.</span></span>


## <a name="defining-controlled-and-adjoint-implementations"></a><span data-ttu-id="1bffb-177">定义受控和 Adjoint 实现</span><span class="sxs-lookup"><span data-stu-id="1bffb-177">Defining Controlled and Adjoint Implementations</span></span>

<span data-ttu-id="1bffb-178">在上面的第一个操作声明示例中，操作 `BitFlip` 和 `DecodeSuperdense` 分别定义为签名 `(Qubit => Unit)` 和 `((Qubit, Qubit) => (Result, Result))` 。</span><span class="sxs-lookup"><span data-stu-id="1bffb-178">In the first operation declaration examples above, the operations `BitFlip` and `DecodeSuperdense` were defined with signatures `(Qubit => Unit)` and `((Qubit, Qubit) => (Result, Result))`, respectively.</span></span>
<span data-ttu-id="1bffb-179">`DecodeSuperdense`这并不是一个单一的操作，因此，它不是单一操作，因此，不能有控制的 adjoint 专用化不能存在（重新调用此类操作返回的相关要求 `Unit` ）。</span><span class="sxs-lookup"><span data-stu-id="1bffb-179">As `DecodeSuperdense` includes measurements, it is not a unitary operation, and therefore neither controlled not adjoint specializations could exist (recall the related requirement that such an operation return `Unit`).</span></span>
<span data-ttu-id="1bffb-180">但是， `BitFlip` 只需执行单一 <xref:microsoft.quantum.intrinsic.x> 操作，就可以将其定义为专用化。</span><span class="sxs-lookup"><span data-stu-id="1bffb-180">However, as `BitFlip` simply performs the unitary <xref:microsoft.quantum.intrinsic.x> operation, we could have defined it with both specializations.</span></span>

<span data-ttu-id="1bffb-181">在这里，我们详细介绍了如何在 Q # 操作声明中包含特殊化的存在性，从而使它们能够与 `Adjoint` and/or 函子一起调用 `Controlled` 。</span><span class="sxs-lookup"><span data-stu-id="1bffb-181">Here, we detail how to include the existence of specializations in your Q# operation declarations, hence giving them the ability to called in conjunction with the `Adjoint` and/or `Controlled` functors.</span></span>
<span data-ttu-id="1bffb-182">在[下面](#circumstances-for-validly-defining-specializations)的部分中，我们介绍了在声明特定专用化的有效或无效情况下的某些情况。</span><span class="sxs-lookup"><span data-stu-id="1bffb-182">Further [below](#circumstances-for-validly-defining-specializations), we describe some of the situations in which it is either valid or not valid to declare certain specializations.</span></span>

<span data-ttu-id="1bffb-183">操作特征定义哪些类型的函子可以应用于声明的操作以及它们有什么影响。</span><span class="sxs-lookup"><span data-stu-id="1bffb-183">Operation characteristics define what kinds of functors can be applied to the declared operation, and what effect they have.</span></span> <span data-ttu-id="1bffb-184">这些专用化的存在可以声明为操作签名的一部分，具体而言，具有操作特征： `is Adj` 、 `is Ctl` 或 `is Adj + Ctl` 。</span><span class="sxs-lookup"><span data-stu-id="1bffb-184">The existence of these specializations can be declared as part of the operation signature, specifically through an annotation with the operation characteristics: either `is Adj`, `is Ctl`, or `is Adj + Ctl`.</span></span>
<span data-ttu-id="1bffb-185">可以*隐式*或*显式*定义每个特殊化的实际实现。</span><span class="sxs-lookup"><span data-stu-id="1bffb-185">The actual implementation of each specialization can either be *implicitly* or *explicitly* defined.</span></span>

### <a name="implicitly-specifying-implementations"></a><span data-ttu-id="1bffb-186">隐式指定实现</span><span class="sxs-lookup"><span data-stu-id="1bffb-186">Implicitly specifying implementations</span></span>

<span data-ttu-id="1bffb-187">在这种情况下，操作声明的主体只包含默认实现。</span><span class="sxs-lookup"><span data-stu-id="1bffb-187">In this case, the body of the operation declaration consists solely of the default implementation.</span></span> <span data-ttu-id="1bffb-188">例如：</span><span class="sxs-lookup"><span data-stu-id="1bffb-188">For example:</span></span>

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit 
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```
<span data-ttu-id="1bffb-189">此处，编译器会自动生成每个此类隐式声明的专用化的对应实现，以在 `Adjoint` 使用或 `Controlled` 函子时执行。</span><span class="sxs-lookup"><span data-stu-id="1bffb-189">Here, the corresponding implementation for each such implicitly declared specialization is automatically generated by the compiler, to be performed if the `Adjoint` or `Controlled` functors are used.</span></span>

<span data-ttu-id="1bffb-190">因此，对的调用 `Adjoint PrepareEntangledPair` 将导致编译器实现的 adjoint `CNOT` ，然后实现的 adjoint `H` 。</span><span class="sxs-lookup"><span data-stu-id="1bffb-190">So, a call of `Adjoint PrepareEntangledPair` would result in the compiler implementing the adjoint of `CNOT` and then the adjoint of `H`.</span></span>
<span data-ttu-id="1bffb-191">这些单独的操作都是 adjoint 的，因此，生成的 `Adjoint PrepareEntangledPair` 操作只包含应用 `CNOT(here, there)` 和 `H(here)` 。</span><span class="sxs-lookup"><span data-stu-id="1bffb-191">These individual operations are both self-adjoint, so the resulting `Adjoint PrepareEntangledPair` operation would simply consist of applying `CNOT(here, there)` and then `H(here)`.</span></span>
<span data-ttu-id="1bffb-192">因此，我们可以 `DecodeSuperdense` 通过使用 adjoint `PrepareEntangledPair` 将放大状态转换回 qubits 的 unentangled 对，使用它来编写更简洁地的示例：</span><span class="sxs-lookup"><span data-stu-id="1bffb-192">Hence we can use this to write the `DecodeSuperdense` example above more compactly, by using the adjoint of `PrepareEntangledPair` to transform the entangled state back into an unentangled pair of qubits:</span></span>

```qsharp
operation DecodeSuperdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

<span data-ttu-id="1bffb-193">声明中具有操作特征的批注非常有用，可确保编译器根据默认实现自动生成其他专用化。</span><span class="sxs-lookup"><span data-stu-id="1bffb-193">The annotation with the operation characteristics in the declaration is useful to ensure that the compiler auto-generates other specializations based on the default implementation.</span></span> 

<span data-ttu-id="1bffb-194">设计用于函子的操作时，需要考虑一些重要的限制。</span><span class="sxs-lookup"><span data-stu-id="1bffb-194">There are a number of important limitations to consider when designing operations for use with functors.</span></span>
<span data-ttu-id="1bffb-195">大多数情况下，编译器*不能*自动生成使用任何其他操作的输出值的操作的专用化，因为在此类操作中，如何对语句重新排序以获得相同的效果。</span><span class="sxs-lookup"><span data-stu-id="1bffb-195">Most critically, specializations for an operation that uses the output value of any other operation *cannot* be auto-generated by the compiler, as it is ambiguous how to reorder the statements in such an operation to obtain the same effect.</span></span>

<span data-ttu-id="1bffb-196">因此，显式指定各种实现通常非常有用。</span><span class="sxs-lookup"><span data-stu-id="1bffb-196">Therefore, it is often useful to explicitly specify the various implementations.</span></span>

### <a name="explicitly-specifying-implementations"></a><span data-ttu-id="1bffb-197">显式指定实现</span><span class="sxs-lookup"><span data-stu-id="1bffb-197">Explicitly specifying implementations</span></span>

<span data-ttu-id="1bffb-198">如果编译器无法生成实现，则可以显式指定实现。</span><span class="sxs-lookup"><span data-stu-id="1bffb-198">In the case where the implementation cannot be generated by the compiler, it can be explicitly specified.</span></span> <span data-ttu-id="1bffb-199">此类显式专用化声明可以包含合适的*生成指令*或用户定义的实现。</span><span class="sxs-lookup"><span data-stu-id="1bffb-199">Such explicit specialization declarations can consist of a suitable *generation directive* or a user-defined implementation.</span></span>
<span data-ttu-id="1bffb-200">在这里，我们提供了各种可能性，其中包含以下示例。</span><span class="sxs-lookup"><span data-stu-id="1bffb-200">Here we provide the full range of possibilities, with examples following below.</span></span>


#### <a name="explicit-specialization-declarations"></a><span data-ttu-id="1bffb-201">显式专用化声明</span><span class="sxs-lookup"><span data-stu-id="1bffb-201">Explicit specialization declarations</span></span>

<span data-ttu-id="1bffb-202">Q # 操作可能包含以下显式专用化声明：</span><span class="sxs-lookup"><span data-stu-id="1bffb-202">Q# operations may contain the following explicit specialization declarations:</span></span>

- <span data-ttu-id="1bffb-203">`body`专用化指定未应用函子的操作的实现。</span><span class="sxs-lookup"><span data-stu-id="1bffb-203">The `body` specialization specifies the implementation of the operation with no functors applied.</span></span>
- <span data-ttu-id="1bffb-204">`adjoint`专用化指定应用了函子的操作的实现 `Adjoint` 。</span><span class="sxs-lookup"><span data-stu-id="1bffb-204">The `adjoint` specialization specifies the implementation of the operation with the `Adjoint` functor applied.</span></span>
- <span data-ttu-id="1bffb-205">`controlled`专用化指定应用了函子的操作的实现 `Controlled` 。</span><span class="sxs-lookup"><span data-stu-id="1bffb-205">The `controlled` specialization specifies the implementation of the operation with the `Controlled` functor applied.</span></span>
- <span data-ttu-id="1bffb-206">`controlled adjoint`专用化指定操作的实现，同时 `Adjoint` `Controlled` 应用和函子。</span><span class="sxs-lookup"><span data-stu-id="1bffb-206">The `controlled adjoint` specialization specifies the implementation of the operation with both the `Adjoint` and `Controlled` functors applied.</span></span>
  <span data-ttu-id="1bffb-207">此特殊化还可以命名 `adjoint controlled` ，因为这两个函子。</span><span class="sxs-lookup"><span data-stu-id="1bffb-207">This specialization can also be named `adjoint controlled`, since the two functors commute.</span></span>


<span data-ttu-id="1bffb-208">操作特殊化包含专业化标记（如或等）， `body` `adjoint` 后跟以下其中之一：</span><span class="sxs-lookup"><span data-stu-id="1bffb-208">An operation specialization consists of the specialization tag (e.g. `body`, or `adjoint`, etc.) followed by one of:</span></span>

- <span data-ttu-id="1bffb-209">如下所述的显式声明。</span><span class="sxs-lookup"><span data-stu-id="1bffb-209">An explicit declaration as described below.</span></span>
- <span data-ttu-id="1bffb-210">告诉编译器*如何*生成专用化的*指令*，可以是：</span><span class="sxs-lookup"><span data-stu-id="1bffb-210">A *directive* that tells the compiler *how* to generate the specialization, one of:</span></span>
  - <span data-ttu-id="1bffb-211">`intrinsic`，它指示目标计算机提供专用化。</span><span class="sxs-lookup"><span data-stu-id="1bffb-211">`intrinsic`, which indicates that the specialization is provided by the target machine.</span></span>
  - <span data-ttu-id="1bffb-212">`distribute`，可与和专用化一起 `controlled` 使用 `controlled adjoint` 。</span><span class="sxs-lookup"><span data-stu-id="1bffb-212">`distribute`, which may be used with the `controlled` and `controlled adjoint` specializations.</span></span>
    <span data-ttu-id="1bffb-213">当与一起使用时 `controlled` ，它指示编译器应通过将应用 `Controlled` 到中的所有操作来计算特殊化 `body` 。</span><span class="sxs-lookup"><span data-stu-id="1bffb-213">When used with `controlled`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `body`.</span></span>
    <span data-ttu-id="1bffb-214">当与一起使用时 `controlled adjoint` ，它指示编译器应通过将应用 `Controlled` 到专用化中的所有操作来计算特殊化 `adjoint` 。</span><span class="sxs-lookup"><span data-stu-id="1bffb-214">When used with `controlled adjoint`, it indicates that the compiler should compute the specialization by applying `Controlled` to all of the operations in the `adjoint` specialization.</span></span>
  - <span data-ttu-id="1bffb-215">`invert`，它指示编译器应 `adjoint` 通过反序列化来计算特殊化 `body` ，即反转运算顺序并将 adjoint 应用于每个操作。</span><span class="sxs-lookup"><span data-stu-id="1bffb-215">`invert`, which indicates that the compiler should compute the `adjoint` specialization by inverting the `body`, i.e. reversing the order of operations and applying the adjoint to each one.</span></span>
    <span data-ttu-id="1bffb-216">当与一起使用时 `adjoint controlled` ，这指示编译器应通过反转专用化来计算特殊化 `controlled` 。</span><span class="sxs-lookup"><span data-stu-id="1bffb-216">When used with `adjoint controlled`, this indicates that the compiler should compute the specialization by inverting the `controlled` specialization.</span></span>
  - <span data-ttu-id="1bffb-217">`self`，指示 adjoint 专用化与 `body` 专用化相同。</span><span class="sxs-lookup"><span data-stu-id="1bffb-217">`self`, to indicate that the adjoint specialization is the the same as the `body` specialization.</span></span>
    <span data-ttu-id="1bffb-218">这对和专用化是合法的 `adjoint` `adjoint controlled` 。</span><span class="sxs-lookup"><span data-stu-id="1bffb-218">This is legal for the `adjoint` and `adjoint controlled` specializations.</span></span>
    <span data-ttu-id="1bffb-219">对于 `adjoint controlled` ， `self` 表示 `adjoint controlled` 专用化与 `controlled` 特殊化相同。</span><span class="sxs-lookup"><span data-stu-id="1bffb-219">For `adjoint controlled`, `self` implies that the `adjoint controlled` specialization is the same as the `controlled` specialization.</span></span>
  - <span data-ttu-id="1bffb-220">`auto`，指示编译器应选择要应用的适当指令。</span><span class="sxs-lookup"><span data-stu-id="1bffb-220">`auto`, to indicate that the compiler should select an appropriate directive to apply.</span></span>
    <span data-ttu-id="1bffb-221">`auto`不能用于 `body` 专用化。</span><span class="sxs-lookup"><span data-stu-id="1bffb-221">`auto` may not be used for the `body` specialization.</span></span>

<span data-ttu-id="1bffb-222">指令和 `auto` 都需要右分号 `;` 。</span><span class="sxs-lookup"><span data-stu-id="1bffb-222">The directives and `auto` all require a closing semi-colon `;`.</span></span>
<span data-ttu-id="1bffb-223">`auto`如果提供了的显式声明，则指令将解析为以下生成指令 `body` ：</span><span class="sxs-lookup"><span data-stu-id="1bffb-223">The `auto` directive resolves to the following generation directive if an explicit declaration of the `body` is provided:</span></span>

- <span data-ttu-id="1bffb-224">`adjoint`根据指令生成专用化 `invert` 。</span><span class="sxs-lookup"><span data-stu-id="1bffb-224">The `adjoint` specialization is generated according to the directive `invert`.</span></span>
- <span data-ttu-id="1bffb-225">`controlled`根据指令生成专用化 `distribute` 。</span><span class="sxs-lookup"><span data-stu-id="1bffb-225">The `controlled` specialization is generated according to the directive `distribute`.</span></span>
- <span data-ttu-id="1bffb-226">`adjoint controlled` `invert` 如果为 `controlled` 指定了显式声明，而不是为指定了一个，则根据指令生成专用化 `adjoint` `distribute` 。</span><span class="sxs-lookup"><span data-stu-id="1bffb-226">The `adjoint controlled` specialization is generated according to the directive `invert` if an explicit declaration for `controlled` is given but not one for `adjoint`, and `distribute` otherwise.</span></span>

> [!TIP]   
> <span data-ttu-id="1bffb-227">如果操作是自我 adjoint 的，则通过生成指令显式指定 adjoint 或受控 adjoint 专用化，以便 `self` 编译器可以利用该信息进行优化。</span><span class="sxs-lookup"><span data-stu-id="1bffb-227">If an operation is self-adjoint, explicitly specify either the adjoint or the controlled adjoint specialization via the generation directive `self` to allow the compiler to make use of that information for optimization purposes.</span></span>

<span data-ttu-id="1bffb-228">包含用户定义的实现的专用化声明包含一个参数元组，后面跟有用于实现专用化的 Q # 代码的语句块。</span><span class="sxs-lookup"><span data-stu-id="1bffb-228">A specialization declaration containing a user-defined implementation consists of an argument tuple followed by a statement block with the Q# code that implements the specialization.</span></span>
<span data-ttu-id="1bffb-229">在参数列表中， `...` 用于表示作为一个整体为操作声明的参数。</span><span class="sxs-lookup"><span data-stu-id="1bffb-229">In the argument list, `...` is used to represent the arguments declared for the operation as a whole.</span></span>
<span data-ttu-id="1bffb-230">对于 `body` 和 `adjoint` ，参数列表应始终为 `(...)` ; 对于 `controlled` 和 `adjoint controlled` ，参数列表应为表示控件 qubits 数组的符号，后面跟有 `...` 括号括在括号中; 例如， `(controls,...)` 。</span><span class="sxs-lookup"><span data-stu-id="1bffb-230">For `body` and `adjoint`, the argument list should always be `(...)`; for `controlled` and `adjoint controlled`, the argument list should be a symbol that represents the array of control qubits, followed by `...`, enclosed in parentheses; for example, `(controls,...)`.</span></span>

### <a name="examples"></a><span data-ttu-id="1bffb-231">示例</span><span class="sxs-lookup"><span data-stu-id="1bffb-231">Examples</span></span>

<span data-ttu-id="1bffb-232">操作声明可能非常简单，如下所示：定义基元 Pauli X 操作：</span><span class="sxs-lookup"><span data-stu-id="1bffb-232">An operation declaration might be as simple as the following, which defines the primitive Pauli X operation:</span></span>

```qsharp
operation X (qubit : Qubit) : Unit
is Adj + Ctl {
    body intrinsic;
    adjoint self;
}
```
<span data-ttu-id="1bffb-233">请注意，Pauli X 操作的 adjoint 是使用指令定义的， `self` 因为按定义 `X` 是其自身的反向运算。</span><span class="sxs-lookup"><span data-stu-id="1bffb-233">Note that the adjoint of the Pauli X operation is defined with the directive `self` because by definition `X` is its own inverse.</span></span>

<span data-ttu-id="1bffb-234">上例中的代码 `PrepareEntangledPair` 等效于下面的代码，其中包含显式专用化声明：</span><span class="sxs-lookup"><span data-stu-id="1bffb-234">The code in `PrepareEntangledPair` above for example is equivalent to the code below containing explicit specialization declarations:</span></span> 

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
<span data-ttu-id="1bffb-235">关键字 `auto` 指示编译器应该确定如何生成专用化实现。</span><span class="sxs-lookup"><span data-stu-id="1bffb-235">The keyword `auto` indicates that the compiler should determine how to generate the specialization implementation.</span></span>

#### <a name="user-defined-specialization-implementation"></a><span data-ttu-id="1bffb-236">用户定义的特殊化实现</span><span class="sxs-lookup"><span data-stu-id="1bffb-236">User-defined specialization implementation</span></span>

<span data-ttu-id="1bffb-237">如果编译器无法自动生成特定专用化的实现，或者如果可以提供更有效的实现，则也可以手动定义该实现。</span><span class="sxs-lookup"><span data-stu-id="1bffb-237">If the compiler cannot generate the implementation for a certain specialization automatically, or if a more efficient implementation can be given, then the implementation may also be manually defined.</span></span>

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
<span data-ttu-id="1bffb-238">在上面的示例中， `adjoint invert;` 指示 adjoint 专用化是通过反转正文实现生成的，并指示将 `controlled adjoint invert;` 通过反转受控专用化的给定实现生成受控 adjoint 专用化。</span><span class="sxs-lookup"><span data-stu-id="1bffb-238">In the example above, `adjoint invert;` indicates that the adjoint specialization is to be generated by inverting the body implementation, and `controlled adjoint invert;` indicates that the controlled adjoint specialization is to be generated by inverting the given implementation of the controlled specialization.</span></span>

<span data-ttu-id="1bffb-239">如果需要显式声明默认正文之外的一个或多个特殊化，则默认体的实现也需要包装到适当的专用化声明中：</span><span class="sxs-lookup"><span data-stu-id="1bffb-239">If one or more specializations besides the default body need to be explicitly declared, then the implementation for the default body needs to be wrapped into a suitable specialization declaration as well:</span></span>

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

### <a name="circumstances-for-validly-defining-specializations"></a><span data-ttu-id="1bffb-240">有效定义专用化的情况</span><span class="sxs-lookup"><span data-stu-id="1bffb-240">Circumstances for validly defining specializations</span></span>

#### <a name="operation-declarations-with-adjointcontrolled"></a><span data-ttu-id="1bffb-241">带有 adjoint/控制的操作声明</span><span class="sxs-lookup"><span data-stu-id="1bffb-241">Operation declarations with adjoint/controlled</span></span>

<span data-ttu-id="1bffb-242">指定不具有 adjoint 或受控版本的操作是合法的。</span><span class="sxs-lookup"><span data-stu-id="1bffb-242">It is legal to specify an operation with no adjoint or controlled versions.</span></span> <span data-ttu-id="1bffb-243">例如，度量操作不具有，因为它们不可逆或可控制。</span><span class="sxs-lookup"><span data-stu-id="1bffb-243">For instance, measurement operations have neither, because they are not invertible or controllable.</span></span>

<span data-ttu-id="1bffb-244">如果操作的 `Adjoint` `Controlled` 声明包含各自专用化的隐式或显式声明，则操作支持和/或函子。</span><span class="sxs-lookup"><span data-stu-id="1bffb-244">An operation supports the `Adjoint` and/or `Controlled` functors if its declaration contains an implicit or explicit declaration of the respective specializations.</span></span>

<span data-ttu-id="1bffb-245">显式声明的 adjoint/受控专用化意味着存在 adjoint/受控专用化。</span><span class="sxs-lookup"><span data-stu-id="1bffb-245">An explicitly declared adjoint/controlled specialization implies the existence of an adjoint/controlled specialization.</span></span> 

<span data-ttu-id="1bffb-246">对于正文包含重复执行循环、set 语句、度量、return 语句或对不支持函子的其他操作的操作 `Adjoint` ， `invert` 不能通过或指令自动生成 adjoint 专用化 `auto` 。</span><span class="sxs-lookup"><span data-stu-id="1bffb-246">For an operation whose body contains repeat-until-success loops, set statements, measurements, return statements, or calls to other operations that do not support the `Adjoint` functor, auto-generating an adjoint specialization following the `invert` or `auto` directive is not possible.</span></span>

<span data-ttu-id="1bffb-247">对于其主体包含对不支持函子的其他操作的调用的操作 `Controlled` ，无法在或指令后自动生成受控专用 `distribute` 化 `auto` 。</span><span class="sxs-lookup"><span data-stu-id="1bffb-247">For an operation whose body contains calls to other operations that does not support the `Controlled` functor, auto-generating a controlled specialization following the `distribute` or `auto` directive is not possible.</span></span>

#### <a name="controlled-adjoint"></a><span data-ttu-id="1bffb-248">受控 Adjoint</span><span class="sxs-lookup"><span data-stu-id="1bffb-248">Controlled Adjoint</span></span>

<span data-ttu-id="1bffb-249">操作的受控 adjoint 版本指定如何实现该操作的 adjoint 的量程控制版本。</span><span class="sxs-lookup"><span data-stu-id="1bffb-249">The controlled adjoint version of an operation specifies how a quantum-controlled version of the adjoint of the operation is implemented.</span></span>
<span data-ttu-id="1bffb-250">指定不具有受控 adjoint 版本的操作是合法的;例如，度量操作没有受控的 adjoint 版本，因为它们既不能控制也不可逆。</span><span class="sxs-lookup"><span data-stu-id="1bffb-250">It is legal to specify an operation with no controlled adjoint version; for instance, measurement operations have no controlled adjoint version because they are neither controllable nor invertible.</span></span>

<span data-ttu-id="1bffb-251">当且仅当存在 adjoint 和受控专用化时，操作的受控 adjoint 专用化才需要存在。</span><span class="sxs-lookup"><span data-stu-id="1bffb-251">A controlled adjoint specialization for an operation needs to exist if and only if both an adjoint and a controlled specialization exist.</span></span> <span data-ttu-id="1bffb-252">在这种情况下，如果未显式定义实现，则会推断出受控 adjoint 专用化的存在，并由编译器生成合适的专用化。</span><span class="sxs-lookup"><span data-stu-id="1bffb-252">In that case, the existence of the controlled adjoint specialization is inferred and an appropriate specialization is generated by the compiler if no implementation has been defined explicitly.</span></span> 

<span data-ttu-id="1bffb-253">对于其正文包含对没有受控 adjoint 版本的其他操作的调用的操作，不能在之后自动生成 adjoint 特殊化 `invert` `distribute` `auto` 。</span><span class="sxs-lookup"><span data-stu-id="1bffb-253">For an operation whose body contains calls to other operations that do not have a controlled adjoint version, auto-generating an adjoint specialization following the `invert`, `distribute` or `auto` directive is not possible.</span></span>


### <a name="type-compatibility"></a><span data-ttu-id="1bffb-254">类型兼容性</span><span class="sxs-lookup"><span data-stu-id="1bffb-254">Type Compatibility</span></span>

<span data-ttu-id="1bffb-255">具有更多函子支持的操作可能会在具有较少函子但需要相同签名的操作的任何位置使用。</span><span class="sxs-lookup"><span data-stu-id="1bffb-255">An operation with additional functors supported may be used anywhere an operation with fewer functors but the same signature is expected.</span></span>
<span data-ttu-id="1bffb-256">例如，类型的操作可以在 `(Qubit => Unit is Adj)` 预期类型为的操作的任何位置使用 `(Qubit => Unit)` 。</span><span class="sxs-lookup"><span data-stu-id="1bffb-256">For instance, an operation of type `(Qubit => Unit is Adj)` may be used anywhere an operation of type `(Qubit => Unit)` is expected.</span></span>

<span data-ttu-id="1bffb-257">Q # 对于可调用的返回类型是*协变*的：返回类型的可调用与 `'A` 具有相同输入类型的可调用和与兼容的结果类型兼容 `'A` 。</span><span class="sxs-lookup"><span data-stu-id="1bffb-257">Q# is *covariant* with respect to callable return types: a callable that returns a type `'A` is compatible with a callable with the same input type and a result type that `'A` is compatible with.</span></span>

<span data-ttu-id="1bffb-258">Q # 对于输入类型是*逆变*的：将类型作为输入的可调用与 `'A` 具有相同结果类型和与兼容的输入类型的可调用兼容 `'A` 。</span><span class="sxs-lookup"><span data-stu-id="1bffb-258">Q# is *contravariant* with respect to input types: a callable that takes a type `'A` as input is compatible with a callable with the same result type and an input type that is compatible with `'A`.</span></span>

<span data-ttu-id="1bffb-259">也就是说，提供以下定义：</span><span class="sxs-lookup"><span data-stu-id="1bffb-259">That is, given the following definitions:</span></span>

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

<span data-ttu-id="1bffb-260">以下为 true：</span><span class="sxs-lookup"><span data-stu-id="1bffb-260">the following are true:</span></span>

- <span data-ttu-id="1bffb-261">`ConjugateInvertWith`可以使用或的参数调用函数 `inner` `Invert` `ApplyUnitary` 。</span><span class="sxs-lookup"><span data-stu-id="1bffb-261">The function `ConjugateInvertWith` may be invoked with an `inner` argument of either `Invert` or `ApplyUnitary`.</span></span>
- <span data-ttu-id="1bffb-262">`ConjugateUnitaryWith`可以使用 `inner` 参数 `ApplyUnitary` （而不是）调用函数 `Invert` 。</span><span class="sxs-lookup"><span data-stu-id="1bffb-262">The function `ConjugateUnitaryWith` may be invoked with an `inner` argument of `ApplyUnitary`, but not `Invert`.</span></span>
- <span data-ttu-id="1bffb-263">类型的值 `(Qubit[] => Unit is Adj + Ctl)` 可以从返回 `ConjugateInvertWith` 。</span><span class="sxs-lookup"><span data-stu-id="1bffb-263">A value of type `(Qubit[] => Unit is Adj + Ctl)` may be returned from `ConjugateInvertWith`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1bffb-264">Q # 0.3 引入了用户定义类型的行为方面的显著差异。</span><span class="sxs-lookup"><span data-stu-id="1bffb-264">Q# 0.3 introduced a significant difference in the behavior of user-defined types.</span></span>

<span data-ttu-id="1bffb-265">用户定义的类型被视为基础类型的包装版本，而不是作为子类型。</span><span class="sxs-lookup"><span data-stu-id="1bffb-265">User-defined types are treated as a wrapped version of the underlying type, rather than as a subtype.</span></span>
<span data-ttu-id="1bffb-266">这意味着，如果需要基础类型的值，用户定义类型的值将无法使用。</span><span class="sxs-lookup"><span data-stu-id="1bffb-266">This means that a value of a user-defined type is not usable where a value of the underlying type is expected.</span></span>


### <a name="conjugations"></a><span data-ttu-id="1bffb-267">语态</span><span class="sxs-lookup"><span data-stu-id="1bffb-267">Conjugations</span></span>

<span data-ttu-id="1bffb-268">与传统位相比，释放量程内存会稍微增加一点，因为在 qubits 仍放大时，盲目重置 qubits 可能会对剩余计算产生意外影响。</span><span class="sxs-lookup"><span data-stu-id="1bffb-268">In contrast to classical bits, releasing quantum memory is slightly more involved since blindly resetting qubits can have undesired effects on the remaining computation if the qubits are still entangled.</span></span> <span data-ttu-id="1bffb-269">在释放内存之前，可以通过正确的方式 "撤消" 已执行的计算来避免这种情况。</span><span class="sxs-lookup"><span data-stu-id="1bffb-269">This can be avoided by properly "undoing" performed computations prior to releasing the memory.</span></span> <span data-ttu-id="1bffb-270">量程计算的常见模式如下：</span><span class="sxs-lookup"><span data-stu-id="1bffb-270">A common pattern in quantum computing is hence the following:</span></span> 

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

<span data-ttu-id="1bffb-271">从0.9 版本开始，我们支持语态语句来实现上述转换。</span><span class="sxs-lookup"><span data-stu-id="1bffb-271">Starting with our 0.9 release, we support a conjugation statement that implements the transformation above.</span></span> <span data-ttu-id="1bffb-272">使用该语句，可以通过 `ApplyWith` 以下方式实现操作：</span><span class="sxs-lookup"><span data-stu-id="1bffb-272">Using that statement, the operation `ApplyWith` can be implemented in the following way:</span></span>

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
<span data-ttu-id="1bffb-273">如果外部和内部转换不能像操作那样轻松地提供，则这种语态语句就变得非常有用，但通过多个语句组成的块可以更方便地进行描述。</span><span class="sxs-lookup"><span data-stu-id="1bffb-273">Such a conjugation statement obviously becomes far more useful if the outer and inner transformation are not readily available as operations but are instead more convenient to describe by a block consisting of several statements.</span></span> 

<span data-ttu-id="1bffb-274">在内块中定义的语句的反转换是由编译器自动生成的，并在 apply 块完成后执行。</span><span class="sxs-lookup"><span data-stu-id="1bffb-274">The inverse transformation for the statements defined in the within-block is automatically generated by the compiler and executed after the apply-block completes.</span></span>
<span data-ttu-id="1bffb-275">由于不能在 apply 块中重新绑定用作内部块的一部分的任何可变变量，因此，生成的转换将保证为内块中计算的 adjoint。</span><span class="sxs-lookup"><span data-stu-id="1bffb-275">Since any mutable variables used as part of the within-block cannot be rebound in the apply-block, the generated transformation is guaranteed to be the adjoint of the computation in the within-block.</span></span> 


## <a name="defining-new-functions"></a><span data-ttu-id="1bffb-276">定义新函数</span><span class="sxs-lookup"><span data-stu-id="1bffb-276">Defining New Functions</span></span>

<span data-ttu-id="1bffb-277">函数是在 Q # 中纯粹确定的传统例程，不同于操作，因为它们不允许在计算输出值之前有任何影响。</span><span class="sxs-lookup"><span data-stu-id="1bffb-277">Functions are purely deterministic, classical routines in Q#, which are distinct from operations in that they are not allowed to have any effects beyond calculating an output value.</span></span>
<span data-ttu-id="1bffb-278">特别是，函数不能调用操作;操作、分配或借用 qubits;示例随机数;否则，依赖于输入值超出函数的状态。</span><span class="sxs-lookup"><span data-stu-id="1bffb-278">In particular, functions cannot call operations; act on, allocate, or borrow qubits; sample random numbers; or otherwise depend on state beyond the input value to a function.</span></span>
<span data-ttu-id="1bffb-279">因此，Q # 函数是*纯*的，因为它们始终将相同的输入值映射到相同的输出值。</span><span class="sxs-lookup"><span data-stu-id="1bffb-279">As a consequence, Q# functions are *pure*, in that they always map the same input values to the same output values.</span></span>
<span data-ttu-id="1bffb-280">这样，在生成操作专用化时，Q # 编译器就可以安全地重新排序调用函数的方式和时间。</span><span class="sxs-lookup"><span data-stu-id="1bffb-280">This allows the Q# compiler to safely reorder how and when functions are called when generating operation specializations.</span></span>

<span data-ttu-id="1bffb-281">每个 Q # 源文件可以定义任意数量的函数。</span><span class="sxs-lookup"><span data-stu-id="1bffb-281">Each Q# source file may define any number of functions.</span></span>
<span data-ttu-id="1bffb-282">函数名称在命名空间中必须是唯一的，并且可能不会与操作或类型名称冲突。</span><span class="sxs-lookup"><span data-stu-id="1bffb-282">Function names must be unique within a namespace and may not conflict with operation or type names.</span></span>

<span data-ttu-id="1bffb-283">定义函数的工作方式与定义操作类似，但不能为函数定义 adjoint 或受控专用化。</span><span class="sxs-lookup"><span data-stu-id="1bffb-283">Defining a function works similarly to defining an operation, except that no adjoint or controlled specializations can be defined for a function.</span></span>
<span data-ttu-id="1bffb-284">例如：</span><span class="sxs-lookup"><span data-stu-id="1bffb-284">For instance:</span></span>

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```

<span data-ttu-id="1bffb-285">或</span><span class="sxs-lookup"><span data-stu-id="1bffb-285">or</span></span> 

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

### <a name="classical-logic-in-functions--good"></a><span data-ttu-id="1bffb-286">函数 = = 良好中的传统逻辑</span><span class="sxs-lookup"><span data-stu-id="1bffb-286">Classical logic in functions == good</span></span>

<span data-ttu-id="1bffb-287">只要有可能，就可以根据函数（而不是操作）编写传统逻辑，以便可以更轻松地在操作中使用。</span><span class="sxs-lookup"><span data-stu-id="1bffb-287">Whenever it is possible to do so, it is helpful to write out classical logic in terms of functions rather than operations, so that it can be more readily used from within operations.</span></span>
<span data-ttu-id="1bffb-288">例如，如果我们 `Square` 已编写上述声明作为*运算*，则编译器将无法确保使用相同的输入调用它会一致地生成相同的输出。</span><span class="sxs-lookup"><span data-stu-id="1bffb-288">For example, if we had written the `Square` declaration above as an *operation*, then the compiler would not have been able to guarantee that calling it with the same input would consistently produce the same outputs.</span></span>

<span data-ttu-id="1bffb-289">若要在函数和操作之间使用下划线，请考虑经典的问题：从 Q # 操作中采样随机数字：</span><span class="sxs-lookup"><span data-stu-id="1bffb-289">To underscore the difference between functions and operations, consider the problem of classically sampling a random number from within a Q# operation:</span></span>

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

<span data-ttu-id="1bffb-290">每次 `U` 调用时，它将对执行不同的操作 `target` 。</span><span class="sxs-lookup"><span data-stu-id="1bffb-290">Each time that `U` is called, it will have a different action on `target`.</span></span>
<span data-ttu-id="1bffb-291">特别是，如果我们将 `adjoint auto` 专用化声明添加到，则编译器无法保证将作为 `U` `U(target); Adjoint U(target);` 标识（即，非 op）。</span><span class="sxs-lookup"><span data-stu-id="1bffb-291">In particular, the compiler cannot guarantee that if we added an `adjoint auto` specialization declaration to `U`, then `U(target); Adjoint U(target);` acts as identity (that is, as a no-op).</span></span>
<span data-ttu-id="1bffb-292">这违反了我们在[矢量和矩阵](xref:microsoft.quantum.concepts.vectors)中看到的 adjoint 定义，使你能够在我们调用了该操作的操作中自动生成 adjoint 特殊化，这 <xref:microsoft.quantum.math.randomreal> 会破坏编译器提供的保证; <xref:microsoft.quantum.math.randomreal> 是不存在 adjoint 或受控版本的操作。</span><span class="sxs-lookup"><span data-stu-id="1bffb-292">This violates the definition of the adjoint that we saw in [Vectors and Matrices](xref:microsoft.quantum.concepts.vectors), such that allowing to auto-generate an adjoint specialization in an operation where we have called the operation <xref:microsoft.quantum.math.randomreal> would break the guarantees provided by the compiler; <xref:microsoft.quantum.math.randomreal> is an operation for which no adjoint or controlled version exists.</span></span>

<span data-ttu-id="1bffb-293">另一方面，允许函数调用（如） `Square` 是安全的，因为编译器可以确保只需将输入保留为，以便 `Square` 保持其输出稳定。</span><span class="sxs-lookup"><span data-stu-id="1bffb-293">On the other hand, allowing function calls such as `Square` is safe, in that the compiler can be assured that it only needs to preserve the input to `Square` in order to keep its output stable.</span></span>
<span data-ttu-id="1bffb-294">因此，将尽可能多的传统逻辑隔离到函数中，可以轻松地在其他函数和操作中重复使用该逻辑。</span><span class="sxs-lookup"><span data-stu-id="1bffb-294">Thus, isolating as much classical logic as possible into functions makes it easy to reuse that logic in other functions and operations alike.</span></span>


## <a name="generic-type-parameterized-callables"></a><span data-ttu-id="1bffb-295">泛型（类型参数化） Callables</span><span class="sxs-lookup"><span data-stu-id="1bffb-295">Generic (Type-Parameterized) Callables</span></span>

<span data-ttu-id="1bffb-296">我们可能想要定义的许多函数和操作实际上不依赖于其输入类型，而只是通过其他函数或操作隐式使用其类型。</span><span class="sxs-lookup"><span data-stu-id="1bffb-296">Many functions and operations that we might wish to define do not actually heavily rely on the types of their inputs, but rather only implicitly use their types via some other function or operation.</span></span>
<span data-ttu-id="1bffb-297">例如，请考虑许多功能语言共有的*地图*概念;给定一个函数 $f （x） $，值为 $ x_1 的集合 \{ ，x_2，\dots ..，x_n \} $，map 返回一个新的集合 $ \{ f （x_1）、f （x_2）、\dots ..、f （x_n） \} $。</span><span class="sxs-lookup"><span data-stu-id="1bffb-297">For example, consider the *map* concept common to many functional languages; given a function $f(x)$ and a collection of values $\{x_1, x_2, \dots, x_n\}$, map returns a new collection $\{f(x_1), f(x_2), \dots, f(x_n)\}$.</span></span>
<span data-ttu-id="1bffb-298">若要在 Q # 中实现此功能，我们可以利用该函数作为第一类。</span><span class="sxs-lookup"><span data-stu-id="1bffb-298">To implement this in Q#, we can take advantage of that functions are first class.</span></span>
<span data-ttu-id="1bffb-299">让我们简单地编写一个示例 `Map` ，使用★作为占位符，同时找出所需的类型。</span><span class="sxs-lookup"><span data-stu-id="1bffb-299">Let's write out a quick example of `Map`, using ★ as a placeholder while we figure out what types we need.</span></span>

```qsharp
function Map(fn : (★ -> ★), values : ★[]) : ★[] {
    mutable mappedValues = new ★[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="1bffb-300">请注意，无论替换的实际类型是什么，此函数的外观都是相同的。</span><span class="sxs-lookup"><span data-stu-id="1bffb-300">Note this function looks very much the same no matter what actual types we substitute in.</span></span>
<span data-ttu-id="1bffb-301">例如，从整数到 Paulis 的映射与从浮点数到字符串的映射大致相同：</span><span class="sxs-lookup"><span data-stu-id="1bffb-301">A map from integers to Paulis, for instance, looks much the same as a map from floating-point numbers to strings:</span></span>

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

<span data-ttu-id="1bffb-302">原则上，我们可以 `Map` 为我们遇到的每对类型编写一个版本的，但这会带来很多麻烦。</span><span class="sxs-lookup"><span data-stu-id="1bffb-302">In principle, we could write a version of `Map` for every pair of types that we encounter, but this introduces a number of difficulties.</span></span>
<span data-ttu-id="1bffb-303">例如，如果我们发现中的 bug `Map` ，则必须确保在的所有版本中统一应用此修补程序 `Map` 。</span><span class="sxs-lookup"><span data-stu-id="1bffb-303">For instance, if we find a bug in `Map`, then we must ensure that the fix is applied uniformly across all versions of `Map`.</span></span>
<span data-ttu-id="1bffb-304">此外，如果我们构造新的元组或 UDT，则现在还必须构建一个新的 `Map` 来与新类型一起工作。</span><span class="sxs-lookup"><span data-stu-id="1bffb-304">Moreover, if we construct a new tuple or UDT, then we must now also construct a new `Map` to go along with the new type.</span></span>
<span data-ttu-id="1bffb-305">虽然这对于少量此类函数是易的，但由于我们收集与相同窗体的更多功能， `Map` 引入新类型的成本在很大程度上将变为太。</span><span class="sxs-lookup"><span data-stu-id="1bffb-305">While this is tractable for a small number of such functions, as we collect more and more functions of the same form as `Map`, the cost of introducing new types becomes unreasonably large in fairly short order.</span></span>

<span data-ttu-id="1bffb-306">但这种情况很难得到，因为我们没有为编译器提供所需的信息，以确定不同版本的 `Map` 关联方式。</span><span class="sxs-lookup"><span data-stu-id="1bffb-306">Much of this difficulty results, however, from that the we have not given the compiler the information it needs to recognize how the different versions of `Map` are related.</span></span>
<span data-ttu-id="1bffb-307">实际上，我们希望编译器将 `Map` q #*类型*中的某种数学函数视为 q # 函数。</span><span class="sxs-lookup"><span data-stu-id="1bffb-307">Effectively, we want the compiler to treat `Map` as some kind of mathematical function from Q# *types* to Q# functions.</span></span>

<span data-ttu-id="1bffb-308">此概念的形式为：允许函数和操作具有*类型参数*，以及其普通元组参数。</span><span class="sxs-lookup"><span data-stu-id="1bffb-308">This notion is formalized by allowing functions and operations to have *type parameters*, as well as their ordinary tuple parameters.</span></span>
<span data-ttu-id="1bffb-309">在上面的示例中，我们希望在 `Map` 第一种情况下将类型形参视为， `Int, Pauli` `Double, String` 在第二种情况下。</span><span class="sxs-lookup"><span data-stu-id="1bffb-309">In the examples above, we wish to think of `Map` as having type parameters `Int, Pauli` in the first case and `Double, String` in the second case.</span></span>
<span data-ttu-id="1bffb-310">大多数情况下，可以像使用普通类型一样使用这些类型参数：我们使用类型参数的值来生成数组和元组，调用函数和操作，并将其分配给普通或可变变量。</span><span class="sxs-lookup"><span data-stu-id="1bffb-310">For the most part, these type parameters can then be used as though they were ordinary types: we use values of type parameters to make arrays and tuples, call functions and operations, and assign to ordinary or mutable variables.</span></span>

> [!NOTE]
> <span data-ttu-id="1bffb-311">间接依赖关系的最极端情况是 qubits，其中 Q # 程序无法直接依赖类型的结构 `Qubit` ，但**必须**将此类类型传递给其他操作和函数。</span><span class="sxs-lookup"><span data-stu-id="1bffb-311">The most extreme case of indirect dependence is that of qubits, where a Q# program cannot directly rely on the structure of the `Qubit` type, but **must** pass such types to other operations and functions.</span></span>

<span data-ttu-id="1bffb-312">返回到上面的示例，我们可以看到，我们需要 `Map` 具有类型参数，一个用于表示输入，另 `fn` 一个用于表示的输出 `fn` 。</span><span class="sxs-lookup"><span data-stu-id="1bffb-312">Returning to the example above, then, we can see that we need `Map` to have type parameters, one to represent the input to `fn` and one to represent the output from `fn`.</span></span>
<span data-ttu-id="1bffb-313">在 Q # 中，这是通过 `<>` 在其声明中的函数或操作名称后面添加尖括号（即，不 brakets $ \braket $！）来编写的， {} 并列出每个类型参数。</span><span class="sxs-lookup"><span data-stu-id="1bffb-313">In Q#, this is written by adding angle brackets (that's `<>`, not brakets $\braket{}$!) after the name of a function or operation in its declaration, and by listing each type parameter.</span></span>
<span data-ttu-id="1bffb-314">每个类型形参的名称必须以计时周期开始 `'` ，指示它是一个类型形参，而不是一个普通类型（也称为*具体*类型）。</span><span class="sxs-lookup"><span data-stu-id="1bffb-314">The name of each type parameter must start with a tick `'`, indicating that it is a type parameter and not a ordinary type (also known as a *concrete* type).</span></span>
<span data-ttu-id="1bffb-315">对于 `Map` ，我们编写：</span><span class="sxs-lookup"><span data-stu-id="1bffb-315">For `Map`, we thus write:</span></span>

```qsharp
function Map<'Input, 'Output>(fn : ('Input -> 'Output), values : 'Input[]) : 'Output[] {
    mutable mappedValues = new 'Output[Length(values)];
    for (idx in 0..Length(values) - 1) {
        set mappedValues w/= idx <- fn(values[idx]);
    }
    return mappedValues;
}
```

<span data-ttu-id="1bffb-316">请注意，的定义与 `Map<'Input, 'Output>` 我们之前编写的版本非常类似。</span><span class="sxs-lookup"><span data-stu-id="1bffb-316">Note that the definition of `Map<'Input, 'Output>` looks extremely similar to the versions we wrote out before.</span></span>
<span data-ttu-id="1bffb-317">唯一的区别是，我们已明确通知编译器 `Map` 不直接依赖于哪些内容 `'Input` `'Output` ，但也适用于任何两种类型，方法是通过从间接使用它们 `fn` 。</span><span class="sxs-lookup"><span data-stu-id="1bffb-317">The only difference is that we have explicitly informed the compiler that `Map` doesn't directly depend on what `'Input` and `'Output` are, but works for any two types by using them indirectly through `fn`.</span></span>
<span data-ttu-id="1bffb-318">`Map<'Input, 'Output>`通过这种方式定义后，可以像调用普通函数一样调用它：</span><span class="sxs-lookup"><span data-stu-id="1bffb-318">Once we have defined `Map<'Input, 'Output>` in this way, we can call it as though it was an ordinary function:</span></span>

```qsharp
// Represent Z₀ Z₁ X₂ Y₃ as a list of ints.
let ints = [3, 3, 1, 2];
// Here, we assume IntToPauli : Int -> Pauli
// looks up PauliI by 0, PauliX by 1, so forth.
let paulis = Map(IntToPauli, ints);
```

> [!TIP]
> <span data-ttu-id="1bffb-319">编写泛型函数和操作是一个位置，其中 "元组即用元组" 是一种非常有用的方法，用于考虑 Q # 函数和操作。</span><span class="sxs-lookup"><span data-stu-id="1bffb-319">Writing generic functions and operations is one place where "tuple-in tuple-out" is a very useful way to think about Q# functions and operations.</span></span>
> <span data-ttu-id="1bffb-320">由于每个函数只使用一个输入并返回一个输出，因此类型为的输入 `'T -> 'U` 与*任何*Q # 函数匹配。</span><span class="sxs-lookup"><span data-stu-id="1bffb-320">Since every function takes exactly one input and returns exactly one output, an input of type `'T -> 'U` matches *any* Q# function whatsoever.</span></span>
> <span data-ttu-id="1bffb-321">同样，可以将任何操作传递到类型的输入 `'T => 'U` 。</span><span class="sxs-lookup"><span data-stu-id="1bffb-321">Similarly, any operation can be passed to an input of type `'T => 'U`.</span></span>

<span data-ttu-id="1bffb-322">作为第二个示例，请考虑编写一个函数，该函数返回两个其他函数的组合：</span><span class="sxs-lookup"><span data-stu-id="1bffb-322">As a second example, consider the challenge of writing a function that returns the composition of two other functions:</span></span>

```qsharp
function ComposeImpl(outerFn : (B -> C), innerFn : (A -> B), input : A) : C {
    return outerFn(innerFn(input));
}

function Compose(outerFn : (B -> C), innerFn : (A -> B)) : (A -> C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="1bffb-323">在此，我们必须明确指定 `A` 、 `B` 和， `C` 从而严格限制新函数的实用工具 `Compose` 。</span><span class="sxs-lookup"><span data-stu-id="1bffb-323">Here, we must specify exactly what `A`, `B`, and `C` are, hence severely limiting the utility of our new `Compose` function.</span></span>
<span data-ttu-id="1bffb-324">毕竟， `Compose` 只依赖于 `A` 、和， `B` 并 `C` *通过* `innerFn` 和 `outerFn` 。</span><span class="sxs-lookup"><span data-stu-id="1bffb-324">After all, `Compose` only depends on `A`, `B`, and `C` *via* `innerFn` and `outerFn`.</span></span>
<span data-ttu-id="1bffb-325">作为替代方法，我们可以将类型参数添加到 `Compose` ，这表示它适用于*任何* `A` 、 `B` 和 `C` ，前提是这些参数与和所需的参数匹配 `innerFn` `outerFn` ：</span><span class="sxs-lookup"><span data-stu-id="1bffb-325">As an alternative, then, we can add type parameters to `Compose` that indicate that it works for *any* `A`, `B`, and `C`, so long as these parameters match those expected by `innerFn` and `outerFn`:</span></span>

```qsharp
function ComposeImpl<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B), input : 'A) : 'C {
    return outerFn(innerFn(input));
}

function Compose<'A, 'B, 'C>(outerFn : ('B -> 'C), innerFn : ('A -> 'B)) : ('A -> 'C) {
    return ComposeImpl(outerFn, innerFn, _);
}
```

<span data-ttu-id="1bffb-326">Q # 标准库提供了多种类型参数化操作和函数，使更高顺序控制流更易于表达。</span><span class="sxs-lookup"><span data-stu-id="1bffb-326">The Q# standard libraries provide a range of such type-parameterized operations and functions to make higher-order control flow easier to express.</span></span>
<span data-ttu-id="1bffb-327">" [Q # 标准库指南](xref:microsoft.quantum.libraries.standard.intro)" 中进一步讨论了这些问题。</span><span class="sxs-lookup"><span data-stu-id="1bffb-327">These are discussed further in the [Q# standard library guide](xref:microsoft.quantum.libraries.standard.intro).</span></span>


## <a name="callables-as-first-class-values"></a><span data-ttu-id="1bffb-328">Callables 作为第一类值</span><span class="sxs-lookup"><span data-stu-id="1bffb-328">Callables as First-Class Values</span></span>

<span data-ttu-id="1bffb-329">使用函数（而不是操作）对控制流和传统逻辑的推理的一项重要技巧是，使用 Q # 中的操作和函数作为*第一类*。</span><span class="sxs-lookup"><span data-stu-id="1bffb-329">One critical technique for reasoning about control flow and classical logic using functions rather than operations is to utilize that operations and functions in Q# are *first-class*.</span></span>
<span data-ttu-id="1bffb-330">也就是说，它们本身就是语言中的每个值。</span><span class="sxs-lookup"><span data-stu-id="1bffb-330">That is, they are each values in the language in their own right.</span></span>
<span data-ttu-id="1bffb-331">例如，下面是非常有效的 Q # 代码，如果没有间接的：</span><span class="sxs-lookup"><span data-stu-id="1bffb-331">For instance, the following is perfectly valid Q# code, if a little indirect:</span></span>

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

<span data-ttu-id="1bffb-332">上面的代码段中的变量的值 `ourH` 为运算，以便 <xref:microsoft.quantum.intrinsic.h> 我们可以像其他任何操作一样调用该值。</span><span class="sxs-lookup"><span data-stu-id="1bffb-332">The value of the variable `ourH` in the snippet above is then the operation <xref:microsoft.quantum.intrinsic.h>, such that we can call that value like any other operation.</span></span>
<span data-ttu-id="1bffb-333">这样，我们就可以编写执行操作的操作作为其输入的一部分，形成更高顺序的控制流概念。</span><span class="sxs-lookup"><span data-stu-id="1bffb-333">This allows us to write operations that take operations as a part of their input, forming higher-order control flow concepts.</span></span>
<span data-ttu-id="1bffb-334">例如，我们可以通过将其应用两次到相同的目标 qubit，来想像 "正方形" 的操作。</span><span class="sxs-lookup"><span data-stu-id="1bffb-334">For instance, we could imagine wanting to "square" an operation by applying it twice to the same target qubit.</span></span>

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

### <a name="returning-operations-from-a-function"></a><span data-ttu-id="1bffb-335">从函数返回操作</span><span class="sxs-lookup"><span data-stu-id="1bffb-335">Returning operations from a function</span></span>

<span data-ttu-id="1bffb-336">我们强调的是，我们还可以在输出过程中返回操作，以便将某些类型的传统条件逻辑隔离为传统函数，该函数将以操作的形式返回量程程序的说明。</span><span class="sxs-lookup"><span data-stu-id="1bffb-336">We emphasize that we can also return operations as a part of outputs, such that we can isolate some kinds of classical conditional logic as a classical function which returns a description of a quantum program in the form of an operation.</span></span>
<span data-ttu-id="1bffb-337">作为一个简单的示例，请考虑 teleportation 示例，在该示例中，接收两位传统消息的参与方需要使用该消息将其 qubit 解码为正确的 teleported 状态。</span><span class="sxs-lookup"><span data-stu-id="1bffb-337">As a simple example, consider the teleportation example, in which the party receiving a two-bit classical message needs to use the message to decode their qubit into the proper teleported state.</span></span>
<span data-ttu-id="1bffb-338">我们可以编写一个函数，该函数采用这两个传统位并返回正确的解码操作。</span><span class="sxs-lookup"><span data-stu-id="1bffb-338">We could write this in terms of a function that takes those two classical bits and returns the proper decoding operation.</span></span>

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

<span data-ttu-id="1bffb-339">此新函数确实是一个函数，在这种情况下，如果使用和的相同值调用该函数 `hereBit` `thereBit` ，则将始终返回相同的操作。</span><span class="sxs-lookup"><span data-stu-id="1bffb-339">This new function is indeed a function, in that if we call it with the same values of `hereBit` and `thereBit`, we will always get back the same operation.</span></span>
<span data-ttu-id="1bffb-340">因此，可以安全地在操作内部运行解码器，而无需考虑解码逻辑如何与不同操作专用化的定义交互。</span><span class="sxs-lookup"><span data-stu-id="1bffb-340">Thus, the decoder can be safely run inside operations without having to reason about how the decoding logic interacts with the definitions of the different operation specializations.</span></span>
<span data-ttu-id="1bffb-341">也就是说，我们已在函数内隔离了传统逻辑，从而保证编译器可以使用 impunity 重新排序函数调用，只要保留输入即可。</span><span class="sxs-lookup"><span data-stu-id="1bffb-341">That is, we have isolated the classical logic inside a function, guaranteeing to the compiler that the function call can be reordered with impunity so long as the input is preserved.</span></span>


## <a name="partial-application"></a><span data-ttu-id="1bffb-342">部分应用程序</span><span class="sxs-lookup"><span data-stu-id="1bffb-342">Partial Application</span></span>

<span data-ttu-id="1bffb-343">通过使用*部分应用程序*返回操作的函数，我们可以更多地执行此操作，在这种情况下，我们可以向函数或操作提供一个或多个输入部分，而无需实际调用它。</span><span class="sxs-lookup"><span data-stu-id="1bffb-343">We can do significantly more with functions that return operations by using *partial application*, in which we can provide one or more parts of the input to a function or operation without actually calling it.</span></span> <span data-ttu-id="1bffb-344">例如，若要调用 `ApplyTwice` 上面的示例，我们可以指示我们不想立即指定输入操作应应用到的 qubit：</span><span class="sxs-lookup"><span data-stu-id="1bffb-344">For example, recalling the `ApplyTwice` example above, we can indicate that we don't want to specify, right away, to which qubit the input operation should apply:</span></span>

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

<span data-ttu-id="1bffb-345">在这种情况下，局部变量 `twiceOp` 包含部分应用的操作，在该操作中 `ApplyTwice(op, _)` ，尚未指定的部分输入由指示 `_` 。</span><span class="sxs-lookup"><span data-stu-id="1bffb-345">In this case, the local variable `twiceOp` holds the partially applied operation `ApplyTwice(op, _)`, where parts of the input that have not yet been specified are indicated by `_`.</span></span>
<span data-ttu-id="1bffb-346">当我们 `twiceOp` 在下一行中实际调用时，我们会将输入的剩余部分的所有剩余部分作为初始操作的输入传递给部分应用的操作。</span><span class="sxs-lookup"><span data-stu-id="1bffb-346">When we actually call `twiceOp` in the next line, we pass as input to the partially applied operation all of the remaining parts of the input to the original operation.</span></span>
<span data-ttu-id="1bffb-347">因此，上面的代码段与直接调用相同，因此， `ApplyTwice(op, target)` 我们引入了新的局部变量，使我们能够在提供输入的某些部分时延迟调用。</span><span class="sxs-lookup"><span data-stu-id="1bffb-347">Thus, the above snippet is effectively identical to having called `ApplyTwice(op, target)` directly, save for that we have introduced a new local variable that allows us to delay the call while providing some parts of the input.</span></span>

<span data-ttu-id="1bffb-348">由于在提供了整个输入之前，不会实际调用已部分应用的操作，因此可以安全地部分应用操作，即使是在函数内也是如此。</span><span class="sxs-lookup"><span data-stu-id="1bffb-348">Since an operation that has been partially applied is not actually called until its entire input has been provided, we can safely partially apply operations even from within functions.</span></span>

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

<span data-ttu-id="1bffb-349">原则上，中的传统逻辑 `SquareOperation` 可能会更多地涉及到，但它仍与操作的其余部分隔离，因为编译器可以提供函数。</span><span class="sxs-lookup"><span data-stu-id="1bffb-349">In principle, the classical logic within `SquareOperation` could have been much more involved, but it is still isolated from the rest of an operation by the guarantees that the compiler can offer about functions.</span></span>
<span data-ttu-id="1bffb-350">此方法将在整个 Q # 标准库中使用，以便以一种可随时在量程程序中使用的方式表示传统控制流。</span><span class="sxs-lookup"><span data-stu-id="1bffb-350">This approach will be used throughout the Q# standard library for expressing classical control flow in a way that can be readily used within quantum programs.</span></span>


## <a name="recursion"></a><span data-ttu-id="1bffb-351">递归</span><span class="sxs-lookup"><span data-stu-id="1bffb-351">Recursion</span></span>

<span data-ttu-id="1bffb-352">Q # callables 允许直接或间接递归。</span><span class="sxs-lookup"><span data-stu-id="1bffb-352">Q# callables are allowed to be directly or indirectly recursive.</span></span>
<span data-ttu-id="1bffb-353">也就是说，操作或函数可能调用自身，或者它可能调用直接或间接调用可调用操作的另一个可调用的。</span><span class="sxs-lookup"><span data-stu-id="1bffb-353">That is, an operation or function may call itself, or it may call another callable that directly or indirectly calls the callable operation.</span></span>

<span data-ttu-id="1bffb-354">不过，有两个关于递归使用的重要说明：</span><span class="sxs-lookup"><span data-stu-id="1bffb-354">There are two important comments about the use of recursion, however:</span></span>

- <span data-ttu-id="1bffb-355">在操作中使用递归可能会干扰某些优化。</span><span class="sxs-lookup"><span data-stu-id="1bffb-355">The use of recursion in operations is likely to interfere with certain optimizations.</span></span>
  <span data-ttu-id="1bffb-356">这可能会对算法的执行时间产生重大影响。</span><span class="sxs-lookup"><span data-stu-id="1bffb-356">This may have a substantial impact on the execution time of the algorithm.</span></span>
- <span data-ttu-id="1bffb-357">在实际的量程设备上执行时，堆栈空间可能会受到限制，因此深度递归可能导致运行时错误。</span><span class="sxs-lookup"><span data-stu-id="1bffb-357">When executing on an actual quantum device, stack space may be limited, and so deep recursion may lead to a runtime error.</span></span>
  <span data-ttu-id="1bffb-358">特别是，Q # 编译器和运行时不标识和优化尾递归。</span><span class="sxs-lookup"><span data-stu-id="1bffb-358">In particular, the Q# compiler and runtime do not identify and optimize tail recursion.</span></span>

## <a name="next-steps"></a><span data-ttu-id="1bffb-359">后续步骤</span><span class="sxs-lookup"><span data-stu-id="1bffb-359">Next steps</span></span>

<span data-ttu-id="1bffb-360">了解 Q # 中的[变量](xref:microsoft.quantum.guide.variables)。</span><span class="sxs-lookup"><span data-stu-id="1bffb-360">Learn about [Variables](xref:microsoft.quantum.guide.variables) in Q#.</span></span>