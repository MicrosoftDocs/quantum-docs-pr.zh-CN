---
title: '操作和函数-Q # 技术 |Microsoft Docs'
description: '操作和函数-Q # 技术'
uid: microsoft.quantum.techniques.opsandfunctions
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 1fca20bb44cc42008f7d25d2fc71a39b962525c2
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820770"
---
# <a name="q-operations-and-functions"></a><span data-ttu-id="cdc20-103">Q # 操作和函数</span><span class="sxs-lookup"><span data-stu-id="cdc20-103">Q# Operations and Functions</span></span>

<span data-ttu-id="cdc20-104">Q # 程序由一个或多个*操作*组成，这些操作描述量程操作对量程数据的影响，以及允许修改传统数据的一个或多个*函数*。</span><span class="sxs-lookup"><span data-stu-id="cdc20-104">Q# programs consist of one or more *operations* that describe side effects quantum operations can have on quantum data, and one or more *functions* that allow modifications to classical data.</span></span> <span data-ttu-id="cdc20-105">与操作不同的是，函数用于描述纯粹的传统行为，在计算经典输出值以外，不会产生任何影响。</span><span class="sxs-lookup"><span data-stu-id="cdc20-105">In contrast to operations, functions are used to describe purely classical behavior and do not have any effects besides computing classical output values.</span></span>

<span data-ttu-id="cdc20-106">在 Q # 中定义的每个操作都可以调用任意数量的其他操作，包括由语言定义的内置内部操作。</span><span class="sxs-lookup"><span data-stu-id="cdc20-106">Each operation defined in Q# may then call any number of other operations, including the built-in intrinsic operations defined by the language.</span></span> <span data-ttu-id="cdc20-107">定义这些内部操作的特定方式取决于目标计算机。</span><span class="sxs-lookup"><span data-stu-id="cdc20-107">The particular way in which these intrinsic operations are defined depends on the target machine.</span></span> <span data-ttu-id="cdc20-108">在编译时，每个操作都表示为可提供给目标计算机的 .NET 类类型。</span><span class="sxs-lookup"><span data-stu-id="cdc20-108">When compiled, each operation is represented as a .NET class type that can be provided to target machines.</span></span>

## <a name="defining-new-operations"></a><span data-ttu-id="cdc20-109">定义新操作</span><span class="sxs-lookup"><span data-stu-id="cdc20-109">Defining New Operations</span></span>

<span data-ttu-id="cdc20-110">如上所述，用 Q # 编写的量程程序的最基本构建基块是一项操作，该*操作*可以从传统的 .net 应用程序（例如，使用模拟器）或在 Q # 内的其他操作中调用。</span><span class="sxs-lookup"><span data-stu-id="cdc20-110">As described above, the most basic building block of a quantum program written in Q# is an *operation*, which can either be called from classical .NET applications, e.g., using a simulator, or by other operations within Q#.</span></span>
<span data-ttu-id="cdc20-111">每个操作都使用一个输入，生成一个输出，并为一个或多个专用操作指定实现。</span><span class="sxs-lookup"><span data-stu-id="cdc20-111">Each operation takes an input, produces an output, and specifies the implementation for one or more operation specializations.</span></span>
<span data-ttu-id="cdc20-112">例如，以下操作仅定义默认的主体特殊化，并采用单个 qubit 作为输入，然后对该输入调用内置 `X` 操作：</span><span class="sxs-lookup"><span data-stu-id="cdc20-112">For instance, the following operation defines only a default body specialization and takes a single qubit as its input, then calls the built-in `X` operation on that input:</span></span>

```qsharp
operation BitFlip(target : Qubit) : Unit {
    X(target);
}
```

<span data-ttu-id="cdc20-113">关键字 `operation` 开始操作定义，后跟名称;此处，`BitFlip`。</span><span class="sxs-lookup"><span data-stu-id="cdc20-113">The keyword `operation` begins the operation definition, and is followed by the name; here, `BitFlip`.</span></span>
<span data-ttu-id="cdc20-114">接下来，输入的类型定义为 `Qubit`，以及用于引用新操作中输入的名称 `target`。</span><span class="sxs-lookup"><span data-stu-id="cdc20-114">Next, the type of the input is defined as `Qubit`, along with a name `target` for referring to the input within the new operation.</span></span>
<span data-ttu-id="cdc20-115">同样，`Unit` 定义操作的输出为空。</span><span class="sxs-lookup"><span data-stu-id="cdc20-115">Similarly, the `Unit` defines that the operation's output is empty.</span></span>
<span data-ttu-id="cdc20-116">这与 `void` C#和其他命令式语言类似，并且与其他功能语言中F# `unit` 等效。</span><span class="sxs-lookup"><span data-stu-id="cdc20-116">This is used similarly to `void` in C# and other imperative languages, and is equivalent to `unit` in F# and other functional languages.</span></span>

> [!NOTE]
> <span data-ttu-id="cdc20-117">我们将在下面更详细地探讨这一点，但 Q # 中的每个操作仅采用一个输入，并只返回一个输出。</span><span class="sxs-lookup"><span data-stu-id="cdc20-117">We will explore this in more detail below, but each operation in Q# takes exactly one input and returns exactly one output.</span></span>
> <span data-ttu-id="cdc20-118">然后使用*元组*表示多个输入和输出，并将多个值一起收集到单个值中。</span><span class="sxs-lookup"><span data-stu-id="cdc20-118">Multiple inputs and outputs are then represented using *tuples*, which collect multiple values together into a single value.</span></span>
> <span data-ttu-id="cdc20-119">非正式地说，Q # 是一种 "元组 out" 语言。</span><span class="sxs-lookup"><span data-stu-id="cdc20-119">Informally, we say that Q# is a "tuple-in tuple-out" language.</span></span>
> <span data-ttu-id="cdc20-120">按照此概念，`()` 应作为 `Unit`类型的 "空" 元组读取。</span><span class="sxs-lookup"><span data-stu-id="cdc20-120">Following this concept, `()` should then be read as the "empty" tuple, which has the type `Unit`.</span></span>

<span data-ttu-id="cdc20-121">在新操作中，如果只需显式指定默认正文专用化的实现，则可在声明中直接指定实现。</span><span class="sxs-lookup"><span data-stu-id="cdc20-121">Within the new operation, the implementation can be specified directly within the declaration if only the implementation of the default body specialization needs to be specified explicitly.</span></span> <span data-ttu-id="cdc20-122">此外，还可以定义一个或多个 `functor` 操作的实现，如下所述。</span><span class="sxs-lookup"><span data-stu-id="cdc20-122">Additionally, it is possible to define the implementations of, for example, one or more `functor` operations, as elaborated below.</span></span> <span data-ttu-id="cdc20-123">在上面的示例中，唯一的语句是调用内置的 Q # 操作 <xref:microsoft.quantum.intrinsic.x>。</span><span class="sxs-lookup"><span data-stu-id="cdc20-123">In the example above, the only statement is to call the built-in Q# operation <xref:microsoft.quantum.intrinsic.x>.</span></span>

<span data-ttu-id="cdc20-124">与 `Unit`相比，操作还会返回更有趣的类型。</span><span class="sxs-lookup"><span data-stu-id="cdc20-124">Operations can also return more interesting types than `Unit`.</span></span>
<span data-ttu-id="cdc20-125">例如，<xref:microsoft.quantum.intrinsic.m> 操作返回 `Result`类型的输出，表示已执行了度量值。</span><span class="sxs-lookup"><span data-stu-id="cdc20-125">For instance, the <xref:microsoft.quantum.intrinsic.m> operation returns an output of type `Result`, representing having performed a measurement.</span></span> <span data-ttu-id="cdc20-126">我们可以将操作的输出传递给另一个操作，也可以将其与 `let` 关键字一起使用来定义新变量。</span><span class="sxs-lookup"><span data-stu-id="cdc20-126">We can either pass the output from an operation to another operation, or can use it with the `let` keyword to define a new variable.</span></span>
<!-- Link to UID for superdense conceptual and example documentation. -->
<span data-ttu-id="cdc20-127">这允许表示在较低级别与量程操作交互的传统计算，如 superdense 编码：</span><span class="sxs-lookup"><span data-stu-id="cdc20-127">This allows for representing classical computation that interacts with quantum operations at a low level, such as in superdense coding:</span></span>

```qsharp
operation Superdense(here : Qubit, there : Qubit) : (Result, Result) {

    CNOT(there, here);
    H(there);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```
### <a name="functors-adjoint-and-controlled"></a><span data-ttu-id="cdc20-128">函子、adjoint 和受控</span><span class="sxs-lookup"><span data-stu-id="cdc20-128">Functors, adjoint and controlled</span></span>
<span data-ttu-id="cdc20-129">如果操作实现了单一转换，则可以定义操作在*adjointed*或*控制*时的行为方式。</span><span class="sxs-lookup"><span data-stu-id="cdc20-129">If an operation implements a unitary transformation, then it is possible to define how the operation acts when *adjointed* or *controlled*.</span></span> <span data-ttu-id="cdc20-130">操作的 adjoint 专用化指定了它在反向运行时的行为方式，而受控专用化指定了在应用于量程寄存器状态时操作的行为方式。</span><span class="sxs-lookup"><span data-stu-id="cdc20-130">An adjoint specialization of an operation specifies how it acts when run in reverse, while a controlled specialization specifies how an operation acts when applied conditioned on the state of a quantum register.</span></span>
<span data-ttu-id="cdc20-131">在以下示例中，可以将这些专用化的存在声明为操作签名的一部分： `is Adj + Ctl`。</span><span class="sxs-lookup"><span data-stu-id="cdc20-131">The existence of these specializations can be declared as part of the operation signature: `is Adj + Ctl` in the following example.</span></span> <span data-ttu-id="cdc20-132">然后，编译器将生成每个此类隐式声明的专用化的相应实现。</span><span class="sxs-lookup"><span data-stu-id="cdc20-132">The corresponding implementation for each such implicitly declared specialization is then generated by the compiler.</span></span> 

```qsharp
operation PrepareEntangledPair(here : Qubit, there : Qubit) : Unit
is Adj + Ctl { // implies the existence of an adjoint, a controlled, and a controlled adjoint specialization
    H(here);
    CNOT(here, there);
}
```

> [!NOTE]
> <span data-ttu-id="cdc20-133">Q # 中的许多操作表示单一入口。</span><span class="sxs-lookup"><span data-stu-id="cdc20-133">Many operations in Q# represent unitary gates.</span></span>
> <span data-ttu-id="cdc20-134">如果 $U $ 是操作 `U`所表示的单一入口，则 `Adjoint U` 表示单一入口 $U ^ \dagger $。</span><span class="sxs-lookup"><span data-stu-id="cdc20-134">If $U$ is the unitary gate represented by an operation `U`, then `Adjoint U` represents the unitary gate $U^\dagger$.</span></span>

<span data-ttu-id="cdc20-135">如果编译器无法生成实现，则可以显式指定实现。</span><span class="sxs-lookup"><span data-stu-id="cdc20-135">In the case where the implementation cannot be generated by the compiler, it can be explicitly specified.</span></span> <span data-ttu-id="cdc20-136">此类显式专用化声明可以包含合适的生成指令或用户定义的实现。</span><span class="sxs-lookup"><span data-stu-id="cdc20-136">Such explicit specialization declarations can consist of a suitable generation directive or a user defined implementation.</span></span> <span data-ttu-id="cdc20-137">例如，上面 `PrepareEntangledPair` 中的代码等效于以下代码，其中包含显式专用化声明：</span><span class="sxs-lookup"><span data-stu-id="cdc20-137">The code in `PrepareEntangledPair` above for example is equivalent to the code below containing explicit specialization declarations:</span></span> 

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
<span data-ttu-id="cdc20-138">关键字 `auto` 指示编译器应该确定如何生成专用化实现。</span><span class="sxs-lookup"><span data-stu-id="cdc20-138">The keyword `auto` indicates that the compiler should determine how to generate the specialization implementation.</span></span>
<span data-ttu-id="cdc20-139">如果编译器无法自动生成特定专用化的实现，或者如果可以提供更有效的实现，则也可以手动定义该实现。</span><span class="sxs-lookup"><span data-stu-id="cdc20-139">If the compiler cannot generate the implementation for a certain specialization automatically, or if a more efficient implementation can be given, then the implementation may also be manually defined.</span></span>

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
<span data-ttu-id="cdc20-140">在上面的示例中，`adjoint invert;` 指示将通过反 `controlled adjoint invert;` 体实现生成 adjoint 专用化，并通过反转受控专用化的给定实现来生成受控 adjoint 专用化。</span><span class="sxs-lookup"><span data-stu-id="cdc20-140">In the example above, `adjoint invert;` indicates that the adjoint specialization is to be generated by inverting the body implementation, and `controlled adjoint invert;` indicates that the controlled adjoint specialization is to be generated by inverting the given implementation of the controlled specialization.</span></span>

<span data-ttu-id="cdc20-141">我们将在[更高顺序控制流](xref:microsoft.quantum.concepts.control-flow)中看到更多的示例。</span><span class="sxs-lookup"><span data-stu-id="cdc20-141">We will see more examples of this in [Higher-Order Control Flow](xref:microsoft.quantum.concepts.control-flow).</span></span>

<span data-ttu-id="cdc20-142">若要调用操作的专用化，请使用 `Adjoint` 或 `Controlled` 关键字。</span><span class="sxs-lookup"><span data-stu-id="cdc20-142">To call a specialization of an operation, use the `Adjoint` or `Controlled` keywords.</span></span>
<span data-ttu-id="cdc20-143">例如，可以通过使用 `PrepareEntangledPair` 的 adjoint 将放大状态转换回 unentangled qubits 对，来编写更多的简洁地：</span><span class="sxs-lookup"><span data-stu-id="cdc20-143">For example, the superdense coding example above can be written more compactly by using the adjoint of `PrepareEntangledPair` to transform the entangled state back into an unentangled pair of qubits:</span></span>

```qsharp
operation Superdense(here : Qubit, there : Qubit) : (Result, Result) {
    Adjoint PrepareEntangledPair(there, here);

    let firstBit = M(there);
    let secondBit = M(here);

    return (firstBit, secondBit);
}
```

<span data-ttu-id="cdc20-144">设计用于函子的操作时，需要考虑一些重要的限制。</span><span class="sxs-lookup"><span data-stu-id="cdc20-144">There are a number of important limitations to consider when designing operations for use with functors.</span></span>
<span data-ttu-id="cdc20-145">大多数情况下，编译器不能自动生成使用任何其他操作的输出值的操作的专用化，因为在此类操作中，如何对语句重新排序以获得相同的效果。</span><span class="sxs-lookup"><span data-stu-id="cdc20-145">Most critically, specializations for an operation that uses the output value of any other operation cannot be auto-generated by the compiler, as it is ambiguous how to reorder the statements in such an operation to obtain the same effect.</span></span>


## <a name="defining-new-functions"></a><span data-ttu-id="cdc20-146">定义新函数</span><span class="sxs-lookup"><span data-stu-id="cdc20-146">Defining New Functions</span></span>

<span data-ttu-id="cdc20-147">Q # 还允许定义函数，这些*函数*与操作截然不同，因为不允许在计算输出值之前有任何影响。</span><span class="sxs-lookup"><span data-stu-id="cdc20-147">Q# also allows for defining *functions*, which are distinct from operations in that they are not allowed to have any effects beyond calculating an output value.</span></span>
<span data-ttu-id="cdc20-148">特别是，函数不能调用操作、对 qubits 执行操作、采样随机数，或依赖于输入值超出函数的状态。</span><span class="sxs-lookup"><span data-stu-id="cdc20-148">In particular, functions cannot call operations, act on qubits, sample random numbers, or otherwise depend on state beyond the input value to a function.</span></span>
<span data-ttu-id="cdc20-149">因此，Q # 函数是*纯*的，因为它们始终将相同的输入值映射到相同的输出值。</span><span class="sxs-lookup"><span data-stu-id="cdc20-149">As a consequence, Q# functions are *pure*, in that they always map the same input values to the same output values.</span></span>
<span data-ttu-id="cdc20-150">这样，在生成操作专用化时，Q # 编译器就可以安全地重新排序调用函数的方式和时间。</span><span class="sxs-lookup"><span data-stu-id="cdc20-150">This allows the Q# compiler to safely reorder how and when functions are called when generating operation specializations.</span></span>

<span data-ttu-id="cdc20-151">定义函数的工作方式与定义操作类似，但不能为函数定义 adjoint 或受控专用化。</span><span class="sxs-lookup"><span data-stu-id="cdc20-151">Defining a function works similarly to defining an operation, except that no adjoint or controlled specializations can be defined for a function.</span></span>
<span data-ttu-id="cdc20-152">对于实例：</span><span class="sxs-lookup"><span data-stu-id="cdc20-152">For instance:</span></span>

```qsharp
function Square(x : Double) : (Double) {
    return x * x;
}
```
<span data-ttu-id="cdc20-153">只要有可能，就可以根据函数（而不是操作）编写传统逻辑，以便可以更轻松地在操作中使用。</span><span class="sxs-lookup"><span data-stu-id="cdc20-153">Whenever it is possible to do so, it is helpful to write out classical logic in terms of functions rather than operations, so that it can be more readily used from within operations.</span></span>
<span data-ttu-id="cdc20-154">例如，如果我们将 `Square` 编写为一个操作，则编译器将无法确保使用相同的输入调用它会以一致的方式生成相同的输出。</span><span class="sxs-lookup"><span data-stu-id="cdc20-154">If we had written `Square` as an operation, for example, then the compiler would not have been able to guarantee that calling it with the same input would consistently produce the same outputs.</span></span>

<span data-ttu-id="cdc20-155">若要在函数和操作之间使用下划线，请考虑经典的问题：从 Q # 操作中采样随机数字：</span><span class="sxs-lookup"><span data-stu-id="cdc20-155">To underscore the difference between functions and operations, consider the problem of classically sampling a random number from within a Q# operation:</span></span>

```qsharp
operation U(target : Qubit) : Unit {

    let angle = RandomReal()
    Rz(angle, target)
}
```

<span data-ttu-id="cdc20-156">每次调用 `U` 时，它将对 `target`执行不同的操作。</span><span class="sxs-lookup"><span data-stu-id="cdc20-156">Each time that `U` is called, it will have a different action on `target`.</span></span>
<span data-ttu-id="cdc20-157">特别是，如果我们将 `adjoint auto` 特殊化声明添加到 `U`，则编译器无法保证 `U(target); Adjoint U(target);` 作为标识（即，非 op）。</span><span class="sxs-lookup"><span data-stu-id="cdc20-157">In particular, the compiler cannot guarantee that if we added an `adjoint auto` specialization declaration to `U`, then `U(target); Adjoint U(target);` acts as identity (that is, as a no-op).</span></span>
<span data-ttu-id="cdc20-158">这违反了我们在[向量和矩阵](xref:microsoft.quantum.concepts.vectors)中看到的 adjoint 定义，使在我们调用操作的操作中自动生成 adjoint 特殊化，<xref:microsoft.quantum.math.randomreal> 会破坏编译器提供的保证;<xref:microsoft.quantum.math.randomreal> 是不存在 adjoint 或受控版本的操作。</span><span class="sxs-lookup"><span data-stu-id="cdc20-158">This violates the definition of the adjoint that we saw in [Vectors and Matrices](xref:microsoft.quantum.concepts.vectors), such that allowing to auto-generate an adjoint specialization in an operation where we have called the operation <xref:microsoft.quantum.math.randomreal> would break the guarantees provided by the compiler; <xref:microsoft.quantum.math.randomreal> is an operation for which no adjoint or controlled version exists.</span></span>

<span data-ttu-id="cdc20-159">另一方面，允许 `Square` 等函数调用是安全的，因为编译器可以确保只需将输入保留到 `Square`，以便保持其输出稳定。</span><span class="sxs-lookup"><span data-stu-id="cdc20-159">On the other hand, allowing function calls such as `Square` is safe, in that the compiler can be assured that it only needs to preserve the input to `Square` in order to keep its output stable.</span></span>
<span data-ttu-id="cdc20-160">因此，将尽可能多的传统逻辑隔离到函数中，可以轻松地在其他函数和操作中重复使用该逻辑。</span><span class="sxs-lookup"><span data-stu-id="cdc20-160">Thus, isolating as much classical logic as possible into functions makes it easy to reuse that logic in other functions and operations alike.</span></span>

## <a name="control-flow"></a><span data-ttu-id="cdc20-161">控制流</span><span class="sxs-lookup"><span data-stu-id="cdc20-161">Control Flow</span></span>

<span data-ttu-id="cdc20-162">在操作或函数中，每个语句都按顺序执行，类似于最常见的命令性传统语言。</span><span class="sxs-lookup"><span data-stu-id="cdc20-162">Within an operation or function, each statement executes in order, similar to most common imperative classical languages.</span></span>
<span data-ttu-id="cdc20-163">不过，可以通过三种不同的方式来修改这种控制流：</span><span class="sxs-lookup"><span data-stu-id="cdc20-163">This flow of control can be modified, however, in three distinct ways:</span></span>

- <span data-ttu-id="cdc20-164">`if` 语句</span><span class="sxs-lookup"><span data-stu-id="cdc20-164">`if` Statements</span></span>
- <span data-ttu-id="cdc20-165">`for` 循环</span><span class="sxs-lookup"><span data-stu-id="cdc20-165">`for` Loops</span></span>
- <span data-ttu-id="cdc20-166">`repeat`-`until` 循环</span><span class="sxs-lookup"><span data-stu-id="cdc20-166">`repeat`-`until` Loops</span></span>

<span data-ttu-id="cdc20-167">我们将讨论这一话题，直到我们讨论了[重复到成功（ru）](xref:microsoft.quantum.techniques.qubits#measurements)的线路。</span><span class="sxs-lookup"><span data-stu-id="cdc20-167">We defer discussion of the latter until we discuss [Repeat Until Success (RUS)](xref:microsoft.quantum.techniques.qubits#measurements) circuits.</span></span>
<span data-ttu-id="cdc20-168">不过，`if` 和 `for` 控制流构造，请在大多数传统编程语言中进行熟悉。</span><span class="sxs-lookup"><span data-stu-id="cdc20-168">The `if` and `for` control flow constructs, however, proceed in a familiar sense to most classical programming languages.</span></span>
<span data-ttu-id="cdc20-169">具体而言，`if` 语句可以采用一个条件，后面可以跟一个或多个 `elif` 语句，并可能以 `else`结尾：</span><span class="sxs-lookup"><span data-stu-id="cdc20-169">In particular, an `if` statement can take a condition, may be followed by one or more `elif` statements, and may end with an `else`:</span></span>

```qsharp
if (pauli == PauliX) {
    X(qubit);
} elif (pauli == PauliY) {
    Y(qubit);
} elif (pauli == PauliZ) {
    Z(qubit);
} else {
    fail "Cannot use PauliI here.";
}
```

<span data-ttu-id="cdc20-170">同样，`for` 循环指示对一个整数范围或数组的元素进行迭代：</span><span class="sxs-lookup"><span data-stu-id="cdc20-170">Similarly, `for` loops indicate iteration over a range of integers or over the elements of an array:</span></span>

```qsharp
for (idxQubit in 0..nQubits - 1) {
    // Do something to idxQubit...
}
```

<span data-ttu-id="cdc20-171">重要的是，`for` 循环和 `if` 语句甚至可用于自动生成专用化的操作。</span><span class="sxs-lookup"><span data-stu-id="cdc20-171">Importantly, `for` loops and `if` statements can even be used in operations for which specializations are auto-generated.</span></span> <span data-ttu-id="cdc20-172">在这种情况下，`for` 循环的 adjoint 会反转方向，并 adjoint 每次迭代。</span><span class="sxs-lookup"><span data-stu-id="cdc20-172">In that case the adjoint of a `for` loop reverses the direction and takes the adjoint of each iteration.</span></span>
<span data-ttu-id="cdc20-173">这遵循了 "鞋和 socks" 原则：如果你想要撤消对 socks 和鞋的投入，则必须撤消鞋，然后撤消放置在 socks 上。</span><span class="sxs-lookup"><span data-stu-id="cdc20-173">This follows the "shoes-and-socks" principle: if you wish to undo putting on socks and then shoes, you must undo putting on shoes and then undo putting on socks.</span></span>
<span data-ttu-id="cdc20-174">在您仍戴鞋的同时，小猫的工作效率更小，并使您的 socks 保持不变！</span><span class="sxs-lookup"><span data-stu-id="cdc20-174">It works decidedly less well to try and take your socks off while you're still wearing your shoes!</span></span>

## <a name="operations-and-functions-as-first-class-values"></a><span data-ttu-id="cdc20-175">操作和函数作为第一类值</span><span class="sxs-lookup"><span data-stu-id="cdc20-175">Operations and Functions as First-Class Values</span></span>

<span data-ttu-id="cdc20-176">使用函数（而不是操作）对控制流和传统逻辑的推理的一项重要技巧是，使用 Q # 中的操作和函数作为*第一类*。</span><span class="sxs-lookup"><span data-stu-id="cdc20-176">One critical technique for reasoning about control flow and classical logic using functions rather than operations is to utilize that operations and functions in Q# are *first-class*.</span></span>
<span data-ttu-id="cdc20-177">也就是说，它们本身就是语言中的每个值。</span><span class="sxs-lookup"><span data-stu-id="cdc20-177">That is, they are each values in the language in their own right.</span></span>
<span data-ttu-id="cdc20-178">例如，下面是非常有效的 Q # 代码，如果没有间接的：</span><span class="sxs-lookup"><span data-stu-id="cdc20-178">For instance, the following is perfectly valid Q# code, if a little indirect:</span></span>

```qsharp
operation FirstClassExample(target : Qubit) : Unit {
    let ourH = H;
    ourH(target);
}
```

<span data-ttu-id="cdc20-179">上面的代码段中的变量 `ourH` 的值是 <xref:microsoft.quantum.intrinsic.h>操作，因此我们可以像调用任何其他操作一样调用该值。</span><span class="sxs-lookup"><span data-stu-id="cdc20-179">The value of the variable `ourH` in the snippet above is then the operation <xref:microsoft.quantum.intrinsic.h>, such that we can call that value like any other operation.</span></span>
<span data-ttu-id="cdc20-180">这样，我们就可以编写执行操作的操作作为其输入的一部分，形成更高顺序的控制流概念。</span><span class="sxs-lookup"><span data-stu-id="cdc20-180">This allows us to write operations that take operations as a part of their input, forming higher-order control flow concepts.</span></span>
<span data-ttu-id="cdc20-181">例如，我们可以通过将其应用两次到相同的目标 qubit，来想像 "正方形" 的操作。</span><span class="sxs-lookup"><span data-stu-id="cdc20-181">For instance, we could imagine wanting to "square" an operation by applying it twice to the same target qubit.</span></span>

```qsharp
operation ApplyTwice(op : (Qubit => Unit), target : Qubit) : Unit {
    op(target);
    op(target);
}
```

<span data-ttu-id="cdc20-182">在此示例中，类型 `(Qubit => Unit)` 中出现的 `=>` 箭头表示输入字段 `op` 是一个操作，该操作将 `Qubit` 类型作为其输入，并生成一个空元组作为其输出。</span><span class="sxs-lookup"><span data-stu-id="cdc20-182">In this example, the `=>` arrow that appears in the type `(Qubit => Unit)` denotes that the input field `op` is an operation which takes as its input the type `Qubit` and produces an empty tuple as its output.</span></span>
<span data-ttu-id="cdc20-183">此外，我们还指定该操作类型的特征，其中包含有关受支持的函子的信息。</span><span class="sxs-lookup"><span data-stu-id="cdc20-183">Additionally we specify the characteristics of that operation type, which contain the information about which functors are supported.</span></span>
<span data-ttu-id="cdc20-184">`(Qubit => Unit)` 类型的操作不支持 `Adjoint` 和 `Controlled` 函子。</span><span class="sxs-lookup"><span data-stu-id="cdc20-184">An operation of type `(Qubit => Unit)` supports neither the `Adjoint` nor the `Controlled` functor.</span></span> <span data-ttu-id="cdc20-185">如果要指示该类型的操作必须支持，例如 `Adjoint` 函子，则必须将其声明为 adjointable。</span><span class="sxs-lookup"><span data-stu-id="cdc20-185">If we want to indicate that an operation of that type has to support e.g. the `Adjoint` functor, we have to declare it as being adjointable.</span></span> <span data-ttu-id="cdc20-186">这是通过使用批注 `is Adj` 到类型来完成的。</span><span class="sxs-lookup"><span data-stu-id="cdc20-186">This is done by using the annotation `is Adj` to the type.</span></span> <span data-ttu-id="cdc20-187">同样，`(Qubit => Unit is Ctl)` 表示该类型的操作支持 `Controlled` 函子。</span><span class="sxs-lookup"><span data-stu-id="cdc20-187">Similarly, `(Qubit => Unit is Ctl)` denotes that an operation of that type supports the `Controlled` functor.</span></span> <span data-ttu-id="cdc20-188">我们将进一步探讨如何更常见地探讨 [Q #] 中的类型（x：）。</span><span class="sxs-lookup"><span data-stu-id="cdc20-188">We will explore this further when we discuss [types in Q#] (xref:microsoft.quantum.language.type-model) more generally.</span></span>

<span data-ttu-id="cdc20-189">现在，我们强调，我们还可以将操作作为输出的一部分返回，以便可以将某些类型的传统条件逻辑隔离为传统函数，这将以操作的形式返回量程程序的说明。</span><span class="sxs-lookup"><span data-stu-id="cdc20-189">For now, we emphasize that we can also return operations as a part of outputs, such that we can isolate some kinds of classical conditional logic as a classical function which returns a description of a quantum program in the form of an operation.</span></span>
<span data-ttu-id="cdc20-190">作为一个简单的示例，请考虑 teleportation 示例，在该示例中，接收两位传统消息的参与方需要使用该消息将其 qubit 解码为正确的 teleported 状态。</span><span class="sxs-lookup"><span data-stu-id="cdc20-190">As a simple example, consider the teleportation example, in which the party receiving a two-bit classical message needs to use the message to decode their qubit into the proper teleported state.</span></span>
<span data-ttu-id="cdc20-191">我们可以编写一个函数，该函数采用这两个传统位并返回正确的解码操作。</span><span class="sxs-lookup"><span data-stu-id="cdc20-191">We could write this in terms of a function that takes those two classical bits and returns the proper decoding operation.</span></span>

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

<span data-ttu-id="cdc20-192">此新函数确实是一个函数，在这种情况下，如果使用 `hereBit` 和 `thereBit`的相同值调用该函数，则将始终返回相同的操作。</span><span class="sxs-lookup"><span data-stu-id="cdc20-192">This new function is indeed a function, in that if we call it with the same values of `hereBit` and `thereBit`, we will always get back the same operation.</span></span>
<span data-ttu-id="cdc20-193">因此，可以安全地在操作内部运行解码器，而无需考虑解码逻辑如何与不同操作专用化的定义交互。</span><span class="sxs-lookup"><span data-stu-id="cdc20-193">Thus, the decoder can be safely run inside operations without having to reason about how the decoding logic interacts with the definitions of the different operation specializations.</span></span>
<span data-ttu-id="cdc20-194">也就是说，我们已在函数内隔离了传统逻辑，从而保证编译器可以使用 impunity 重新排序函数调用，只要保留输入即可。</span><span class="sxs-lookup"><span data-stu-id="cdc20-194">That is, we have isolated the classical logic inside a function, guaranteeing to the compiler that the function call can be reordered with impunity so long as the input is preserved.</span></span>

<span data-ttu-id="cdc20-195">我们还可以将函数视为第一类值，因为我们会在讨论[操作和函数类型](#operations-and-functions-as-first-class-values)时更详细地介绍这些值。</span><span class="sxs-lookup"><span data-stu-id="cdc20-195">We can also treat functions as first-class values, as we will see in more detail when we discuss [operations and function types](#operations-and-functions-as-first-class-values).</span></span>

## <a name="partially-applying-operations-and-functions"></a><span data-ttu-id="cdc20-196">部分应用操作和函数</span><span class="sxs-lookup"><span data-stu-id="cdc20-196">Partially Applying Operations and Functions</span></span>

<span data-ttu-id="cdc20-197">通过使用*部分应用程序*返回操作的函数，我们可以更多地执行此操作，在这种情况下，我们可以向函数或操作提供一个或多个输入部分，而无需实际调用它。</span><span class="sxs-lookup"><span data-stu-id="cdc20-197">We can do significantly more with functions that return operations by using *partial application*, in which we can provide one or more parts of the input to a function or operation without actually calling it.</span></span> <span data-ttu-id="cdc20-198">例如，如果调用上面的 `ApplyTwice` 示例，则可以指示我们不想立即指定输入操作应应用到的 qubit：</span><span class="sxs-lookup"><span data-stu-id="cdc20-198">For example, recalling the `ApplyTwice` example above, we can indicate that we don't want to specify, right away, to which qubit the input operation should apply:</span></span>

```qsharp
operation PartialApplicationExample(op : (Qubit => Unit), target : Qubit) : Unit {
    let twiceOp = ApplyTwice(op, _);
    twiceOp(target);
}
```

<span data-ttu-id="cdc20-199">在这种情况下，本地变量 `twiceOp` 包含部分应用的操作 `ApplyTwice(op, _)`，其中尚未指定的部分输入由 `_`指示。</span><span class="sxs-lookup"><span data-stu-id="cdc20-199">In this case, the local variable `twiceOp` holds the partially applied operation `ApplyTwice(op, _)`, where parts of the input that have not yet been specified are indicated by `_`.</span></span>
<span data-ttu-id="cdc20-200">当我们实际调用下一行中的 `twiceOp` 时，我们会将输入的剩余部分的所有剩余部分作为初始操作传递给部分应用的操作。</span><span class="sxs-lookup"><span data-stu-id="cdc20-200">When we actually call `twiceOp` in the next line, we pass as input to the partially applied operation all of the remaining parts of the input to the original operation.</span></span>
<span data-ttu-id="cdc20-201">因此，上面的代码段实际上等同于直接调用 `ApplyTwice(op, target)`，因此，我们引入了一个新的本地变量，使我们能够在提供输入的某些部分时延迟调用。</span><span class="sxs-lookup"><span data-stu-id="cdc20-201">Thus, the above snippet is effectively identical to having called `ApplyTwice(op, target)` directly, save for that we have introduced a new local variable that allows us to delay the call while providing some parts of the input.</span></span>

<span data-ttu-id="cdc20-202">由于在提供了整个输入之前，不会实际调用已部分应用的操作，因此可以安全地部分应用操作，即使是在函数内也是如此。</span><span class="sxs-lookup"><span data-stu-id="cdc20-202">Since an operation that has been partially applied is not actually called until its entire input has been provided, we can safely partially apply operations even from within functions.</span></span>

```qsharp
function SquareOperation(op : (Qubit => Unit)) : (Qubit => Unit) {
    return ApplyTwice(op, _);
}
```

<span data-ttu-id="cdc20-203">原则上，`SquareOperation` 中的传统逻辑可能会更多地涉及到，但它仍与操作的其余部分隔离，因为编译器可以提供函数。</span><span class="sxs-lookup"><span data-stu-id="cdc20-203">In principle, the classical logic within `SquareOperation` could have been much more involved, but it is still isolated from the rest of an operation by the guarantees that the compiler can offer about functions.</span></span>
<span data-ttu-id="cdc20-204">此方法将在整个 Q # 标准库中使用，以便以一种可随时在量程程序中使用的方式表示传统控制流。</span><span class="sxs-lookup"><span data-stu-id="cdc20-204">This approach will be used throughout the Q# standard library for expressing classical control flow in a way that can be readily used within quantum programs.</span></span>
