---
title: 'Q # 基础知识'
description: Q 的基本概念#
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 02/28/2020
ms.topic: article
uid: microsoft.quantum.guide.basics
ms.openlocfilehash: fd0ea47f00b1456ec460808ef7d451c8427677cd
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431149"
---
# <a name="q-basics"></a><span data-ttu-id="e88be-103">Q # 基础知识</span><span class="sxs-lookup"><span data-stu-id="e88be-103">Q# Basics</span></span>

<span data-ttu-id="e88be-104">在本部分中，我们将简要介绍 Q # 的基本构建基块。</span><span class="sxs-lookup"><span data-stu-id="e88be-104">In this section we present a brief introduction to the basic building blocks of Q#.</span></span>

<span data-ttu-id="e88be-105">若要快速了解 Q # 的作用，以及它作为量程开发工具包的基础组件在哪里，可以查看[问 #？](xref:microsoft.quantum.overview.q-sharp)。</span><span class="sxs-lookup"><span data-stu-id="e88be-105">For a quick overview of what Q# is and where it fits in as a fundamental component of the Quantum Development Kit, you can check out [What is Q#?](xref:microsoft.quantum.overview.q-sharp).</span></span> 

## <a name="what-is-a-quantum-program"></a><span data-ttu-id="e88be-106">什么是量程计划？</span><span class="sxs-lookup"><span data-stu-id="e88be-106">What is a quantum program?</span></span>

<span data-ttu-id="e88be-107">从技术角度看，可以将量程程序视为一组特定的传统子例程，在调用该程序时，会在量程系统上执行特定操作。</span><span class="sxs-lookup"><span data-stu-id="e88be-107">From a technical perspective, a quantum program can be seen as a particular set of classical subroutines which, when called, perform certain operations on a quantum system.</span></span>
<span data-ttu-id="e88be-108">此视图的一个重要结果是，以 Q # 编写的程序不会直接对 qubits 建模，而是介绍传统的控制计算机如何与这些 qubits 交互。</span><span class="sxs-lookup"><span data-stu-id="e88be-108">An important consequence of that view is that a program written in Q# does not directly model qubits themselves, but rather describes how a classical control computer interacts with those qubits.</span></span>
<span data-ttu-id="e88be-109">按照设计，Q # 不会直接定义量子机制的量程状态或其他属性。</span><span class="sxs-lookup"><span data-stu-id="e88be-109">By design, Q# thus does not define quantum states or other properties of quantum mechanics directly.</span></span>
<span data-ttu-id="e88be-110">例如，考虑 {0} {1} {2} [量程计算概念](xref:microsoft.quantum.concepts.intro)指南中讨论的状态 $ \ket{+} = \left （\ket + \ket \right）/\sqrt $。</span><span class="sxs-lookup"><span data-stu-id="e88be-110">For instance, consider the state $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ discussed in the [Quantum Computing Concepts](xref:microsoft.quantum.concepts.intro) guide.</span></span>
<span data-ttu-id="e88be-111">若要在 Q # 中准备此状态，我们将使用在 $ \ket $ 状态下初始化 qubits 的事实 {0} ，并使用 $ \ket{+} = H\ket {0} $，其中 $H $ 是由 [ `H` operation] （] （Hadamard：）实现的 x 转换：</span><span class="sxs-lookup"><span data-stu-id="e88be-111">To prepare this state in Q#, we use the facts that the qubits are initialized in the $\ket{0}$ state, and that $\ket{+} = H\ket{0}$, where $H$ is the Hadamard transform, implemented by the [`H` operation](](xref:microsoft.quantum.intrinsic.h):</span></span>

```qsharp
using (qubit = Qubit()) {
    // At this point, qubit is in the state |0⟩.
    H(qubit);
    // We've now applied H, such that our qubit is in H|0⟩ = |+⟩, as we wanted.
}
```

## <a name="quantum-states-in-q"></a><span data-ttu-id="e88be-112">问答中的量程状态#</span><span class="sxs-lookup"><span data-stu-id="e88be-112">Quantum states in Q#</span></span>

<span data-ttu-id="e88be-113">重要的是，在编写上述程序时，我们未显式引用 Q # 中的状态，而是说明了该状态是由程序*转换*的。</span><span class="sxs-lookup"><span data-stu-id="e88be-113">Importantly, in writing the above program, we did not explicitly refer to the state within Q#, but rather described how the state was *transformed* by our program.</span></span>
<span data-ttu-id="e88be-114">这使我们完全不知道量程状态在每台目标计算机*上的*状态，这可能会根据计算机的不同解释。</span><span class="sxs-lookup"><span data-stu-id="e88be-114">This allows us to be entirely agnostic about what a quantum state even *is* on each target machine, which might have different interpretations depending on the machine.</span></span> 

<span data-ttu-id="e88be-115">Q # 程序无法 introspect 到 qubit 的状态。</span><span class="sxs-lookup"><span data-stu-id="e88be-115">A Q# program has no ability to introspect into the state of a qubit.</span></span>
<span data-ttu-id="e88be-116">相反，程序可以调用等操作 [`Measure`](xref:microsoft.quantum.intrinsic.measure) 来了解 qubit 中的信息，并调用操作（例如和） [`X`](xref:microsoft.quantum.intrinsic.x) [`H`](xref:microsoft.quantum.intrinsic.h) 来处理 qubit 的状态。</span><span class="sxs-lookup"><span data-stu-id="e88be-116">Rather, a program can call operations such as [`Measure`](xref:microsoft.quantum.intrinsic.measure) to learn information from a qubit, and call operations such as [`X`](xref:microsoft.quantum.intrinsic.x) and [`H`](xref:microsoft.quantum.intrinsic.h) to act on the state of a qubit.</span></span>
<span data-ttu-id="e88be-117">这些操作实际*执行*的操作仅由我们用于运行特定 Q # 程序的目标计算机进行具体操作。</span><span class="sxs-lookup"><span data-stu-id="e88be-117">What these operations actually *do* is only made concrete by the target machine we use to run the particular Q# program.</span></span>
<span data-ttu-id="e88be-118">例如，如果在我们的[全状态模拟器](xref:microsoft.quantum.machines.full-state-simulator)上运行程序，模拟器将对模拟的量程系统执行相应的数学运算。</span><span class="sxs-lookup"><span data-stu-id="e88be-118">For example, if running the program on our [full-state simulator](xref:microsoft.quantum.machines.full-state-simulator), the simulator will perform the corresponding mathematical operations to the simulated quantum system.</span></span>
<span data-ttu-id="e88be-119">但在将来，如果目标计算机是一台真实的量程计算机，则在 Q # 中调用此类操作将指示量程计算机在*实际*的量程系统上执行相应的*实际*操作（例如，精确地计时激光脉冲）。</span><span class="sxs-lookup"><span data-stu-id="e88be-119">But looking toward the future, when the target machine is a real quantum computer, calling such operations in Q# will direct the quantum computer to perform the corresponding *real* operations on the *real* quantum system (e.g. precisely timed laser pulses).</span></span>

<span data-ttu-id="e88be-120">Q # 计划 recombines 目标计算机定义的操作，以创建新的更高级操作来表示量程计算。</span><span class="sxs-lookup"><span data-stu-id="e88be-120">A Q# program recombines these operations as defined by a target machine to create new, higher-level operations to express quantum computation.</span></span>
<span data-ttu-id="e88be-121">通过这种方式，使用 Q # 可以轻松地表达逻辑底层的量程和混合量子–传统算法，同时对目标计算机或模拟器的结构也很普遍。</span><span class="sxs-lookup"><span data-stu-id="e88be-121">In this way, Q# makes it easy to express the logic underlying quantum and hybrid quantum–classical algorithms, while also being general with respect to the structure of a target machine or simulator.</span></span>

## <a name="q-operations-and-functions"></a><span data-ttu-id="e88be-122">Q # 操作和函数</span><span class="sxs-lookup"><span data-stu-id="e88be-122">Q# operations and functions</span></span>

<span data-ttu-id="e88be-123">具体而言，Q # 程序由*操作*、*函数*和任何用户定义的类型组成。</span><span class="sxs-lookup"><span data-stu-id="e88be-123">Concretely, a Q# program is comprised of *operations*, *functions*, and any user-defined types.</span></span> 

<span data-ttu-id="e88be-124">操作用于描述量程系统的转换，是最基本的 Q # 程序构建基块。</span><span class="sxs-lookup"><span data-stu-id="e88be-124">Operations are used to describe the transformations of quantum systems and are the most basic building block of Q# programs.</span></span> <span data-ttu-id="e88be-125">在 Q # 中定义的每个操作都可以调用任意数量的其他操作。</span><span class="sxs-lookup"><span data-stu-id="e88be-125">Each operation defined in Q# may then call any number of other operations.</span></span>

<span data-ttu-id="e88be-126">与操作不同的是，函数用于描述纯*确定性*的传统行为，在计算传统值之外不会有任何影响。</span><span class="sxs-lookup"><span data-stu-id="e88be-126">In contrast to operations, functions are used to describe purely *deterministic* classical behavior and do not have any effects besides computing classical values.</span></span> <span data-ttu-id="e88be-127">例如，假设我们想要在程序的末尾测量 qubits，并将测量结果添加到数组中。</span><span class="sxs-lookup"><span data-stu-id="e88be-127">For example, suppose we would like to measure our qubits at the end of a program, and add the measurement results to an array.</span></span>
<span data-ttu-id="e88be-128">在这种情况下， `Measure` *操作*会指示目标计算机对（real 或模拟） qubits 执行度量，将返回结果添加到数组的传统过程将由*函数*进行处理。</span><span class="sxs-lookup"><span data-stu-id="e88be-128">In this case `Measure` is an *operation* which instructs the target machine to perform a measurement on the (real or simulated) qubits, and the classical process of adding the returned results to an array will be handled by *functions*.</span></span>

<span data-ttu-id="e88be-129">同时，操作和函数称为*callables*，它们的基础结构和行为是在 "Q #" 页的 "[操作和函数" 中](xref:microsoft.quantum.guide.operationsfunctions)引入的。</span><span class="sxs-lookup"><span data-stu-id="e88be-129">Together, operations and functions are referred to as *callables*, and their underlying structure and behavior is introduced on the [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions) page.</span></span>


## <a name="q-syntax-overview"></a><span data-ttu-id="e88be-130">Q # 语法概述</span><span class="sxs-lookup"><span data-stu-id="e88be-130">Q# syntax overview</span></span>

<span data-ttu-id="e88be-131">语言的语法描述形成语法正确的程序的符号的不同组合。</span><span class="sxs-lookup"><span data-stu-id="e88be-131">The syntax of a language describes the different combinations of symbols that form a syntactically correct program.</span></span>
<span data-ttu-id="e88be-132">在 Q # 中，我们可以将其语法的元素分类为三个不同的组：类型、表达式和语句。</span><span class="sxs-lookup"><span data-stu-id="e88be-132">In Q# we can classify the elements of its syntax in three different groups: types, expressions and statements.</span></span>

### <a name="types"></a><span data-ttu-id="e88be-133">类型</span><span class="sxs-lookup"><span data-stu-id="e88be-133">Types</span></span>
<span data-ttu-id="e88be-134">Q # 是一种强类型语言，因此，仔细使用类型有助于编译器在编译时提供有关 Q # 程序的强大保证。</span><span class="sxs-lookup"><span data-stu-id="e88be-134">Q# is a strongly-typed language, such that careful use of types can help the compiler provide strong guarantees about Q# programs at compile time.</span></span>
<span data-ttu-id="e88be-135">除了标准和特定于量程的内置基元类型（如、、 `Int` `Bool` `Qubit` 和 `Result` ），Q # 还提供对用户定义类型的支持。</span><span class="sxs-lookup"><span data-stu-id="e88be-135">In addition to standard and quantum-specific built-in primitive types (e.g. `Int`, `Bool`, `Qubit`, and `Result`), Q# provides support for user-defined types.</span></span>
<span data-ttu-id="e88be-136">所有 Q # 的各种基元类型都在 " [q #](xref:microsoft.quantum.guide.types) " 页上的 "类型" 中进行了介绍，以及有关数组和元组类型的详细信息，以及如何在 Q # 文件中定义新类型。</span><span class="sxs-lookup"><span data-stu-id="e88be-136">All of Q#'s various primitive types are described on the [Types in Q#](xref:microsoft.quantum.guide.types) page, along with details on array and tuple types, as well as how to define new types within a Q# file.</span></span>

### <a name="expressions"></a><span data-ttu-id="e88be-137">表达式</span><span class="sxs-lookup"><span data-stu-id="e88be-137">Expressions</span></span>
<span data-ttu-id="e88be-138">编程语言中的表达式是编程语言解释并计算为特定值的一个或多个常量、变量、运算符和函数的组合。</span><span class="sxs-lookup"><span data-stu-id="e88be-138">An expression in a programming language is a combination of one or more constants, variables, operators, and functions that the programming language interprets and evaluates to a specific value.</span></span>
<span data-ttu-id="e88be-139">大多数情况下，对于语言中的每个类型，该类型的表达式可以是*文本*，也可以是绑定到该类型的值的符号。</span><span class="sxs-lookup"><span data-stu-id="e88be-139">Most simply, for every type in a language, expressions of that type can be either *literals* or symbols bound to a value of that type.</span></span>
<span data-ttu-id="e88be-140">例如， `5` 是一个 `Int` 文本（也是类型为的表达式 `Int` ），如果符号 `count` 绑定到整数值 `5` ，则 `count` 也是整数表达式。</span><span class="sxs-lookup"><span data-stu-id="e88be-140">For example, `5` is an `Int` literal (thus also an expression of type `Int`), and if the symbol `count` is bound to the integer value `5`, then `count` is also an integer expression.</span></span>

<span data-ttu-id="e88be-141">此外，表达式还可以包含与特定运算符组合在一起的其他表达式。</span><span class="sxs-lookup"><span data-stu-id="e88be-141">Additionally, an expression can consist of other expressions combined with certain operators.</span></span>
<span data-ttu-id="e88be-142">因此，计算结果为的表达式的另一个示例 `Int` `5` 是 `2+3` 。</span><span class="sxs-lookup"><span data-stu-id="e88be-142">Hence another example of an `Int` expression which evaluates to `5` is `2+3`.</span></span>

<span data-ttu-id="e88be-143">可以使用 Q # 中的类型表达式以及可用于形成它们的兼容运算符，详细介绍了 "Q #" 页中的[类型表达式](xref:microsoft.quantum.guide.expressions)。</span><span class="sxs-lookup"><span data-stu-id="e88be-143">The possible expressions of types in Q#, as well as the compatible operators that can be used to form them, are detailed on the [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions) page.</span></span> 

### <a name="statements"></a><span data-ttu-id="e88be-144">语句</span><span class="sxs-lookup"><span data-stu-id="e88be-144">Statements</span></span> 
<span data-ttu-id="e88be-145">语句是命令式编程语言的语法单元，表示要执行的操作。语句与中的表达式相比，语句不会返回结果，而是只为其副作用而执行，而表达式始终返回结果，并且通常根本没有副作用。</span><span class="sxs-lookup"><span data-stu-id="e88be-145">A statement is a syntactic unit of an imperative programming language that expresses some action to be carried out. Statements contrast with expressions in that statements do not return results and are executed solely for their side effects, while expressions always return a result and often do not have side effects at all.</span></span>
<span data-ttu-id="e88be-146">这种区别经常以措辞来观察：计算表达式，而执行语句。</span><span class="sxs-lookup"><span data-stu-id="e88be-146">This distinction is frequently observed in wording: an expression is evaluated, whereas a statement is executed.</span></span>

<span data-ttu-id="e88be-147">Q # 中的语句的一个非常基本的示例是为表达式赋值：</span><span class="sxs-lookup"><span data-stu-id="e88be-147">A very basic example of a statement in Q# is assigning a symbol to an expression:</span></span>
```qsharp
let count = 5;
```

<span data-ttu-id="e88be-148">更有趣的例子是 `for` 支持迭代的语句，并包含*语句块*。</span><span class="sxs-lookup"><span data-stu-id="e88be-148">A slightly more interesting example is the `for` statement which supports iteration and includes a *statement block*.</span></span>
<span data-ttu-id="e88be-149">假设 `qubits` 符号绑定到 qubits 的寄存器（技术上的类型 `Qubit[]` ，即类型的数组 `Qubit` ）。</span><span class="sxs-lookup"><span data-stu-id="e88be-149">Suppose `qubits` is the symbol bound to a register of qubits (technically of type `Qubit[]`, i.e. an array of `Qubit` types).</span></span> <span data-ttu-id="e88be-150">Then</span><span class="sxs-lookup"><span data-stu-id="e88be-150">Then</span></span>
```qsharp
for (qubit in qubits) {
    H(qubit);
}
```
<span data-ttu-id="e88be-151">是一个语句，它循环访问寄存器中的每个 qubit，并 `H` 对每个执行操作。</span><span class="sxs-lookup"><span data-stu-id="e88be-151">is a statement which iterates over each qubit in the register, performing the `H` operation on each.</span></span> <span data-ttu-id="e88be-152">请注意，也 `H(qubit);` 是一条语句。</span><span class="sxs-lookup"><span data-stu-id="e88be-152">Note that `H(qubit);` is a statement in itself as well.</span></span>

<span data-ttu-id="e88be-153">事实上，任何类型的调用表达式 `Unit` （不返回任何信息的 callables）都可以用作语句。</span><span class="sxs-lookup"><span data-stu-id="e88be-153">In fact, any call expression of type `Unit` (those callables that do not return any information) may be used as a statement.</span></span>
<span data-ttu-id="e88be-154">这主要是在对返回的 qubits 调用操作时使用的， `Unit` 因为语句的目的是修改隐式量程状态。</span><span class="sxs-lookup"><span data-stu-id="e88be-154">This is primarily of use when calling operations on qubits that return `Unit` because the purpose of the statement is to modify the implicit quantum state.</span></span>
<span data-ttu-id="e88be-155">表达式计算语句需要终止分号。</span><span class="sxs-lookup"><span data-stu-id="e88be-155">Expression evaluation statements require a terminating semicolon.</span></span>

<span data-ttu-id="e88be-156">问答 # 程序的几乎每个方面都是使用语句构建的，因此，任何一个页面都不能包含与它们相关的所有信息。</span><span class="sxs-lookup"><span data-stu-id="e88be-156">Nearly every aspect of a Q# program is built using statements, so no single page could encompass all the information relating to them.</span></span>
<span data-ttu-id="e88be-157">但是，其词法结构和格式在 q [# 文件结构](xref:microsoft.quantum.guide.filestructure)页、符号绑定分配和[q # 中的变量](xref:microsoft.quantum.guide.variables)的范围和控制流循环（如 `for` [q # 中的控制流）中](xref:microsoft.quantum.guide.controlflow)进行了介绍。</span><span class="sxs-lookup"><span data-stu-id="e88be-157">However, their lexical structure and formatting is described on the [Q# File Structure](xref:microsoft.quantum.guide.filestructure) page, symbol binding assignment and scope at [Variables in Q#](xref:microsoft.quantum.guide.variables), and control flow loops such as `for` at [Control Flow in Q#](xref:microsoft.quantum.guide.controlflow).</span></span>


## <a name="whats-next"></a><span data-ttu-id="e88be-158">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e88be-158">What's next?</span></span>
<span data-ttu-id="e88be-159">在本指南的其余部分，我们将向您展示如何使用 Q # 通过操作、函数和类型的基本构建块来构建复杂的量程程序。</span><span class="sxs-lookup"><span data-stu-id="e88be-159">Throughout the rest of this guide, we will show you how to use Q# to construct complex quantum programs through the basic building blocks of operations, functions, and types.</span></span>

<span data-ttu-id="e88be-160">若要开始，可以开始了解[Q # 中的类型](xref:microsoft.quantum.guide.types)。</span><span class="sxs-lookup"><span data-stu-id="e88be-160">To get started, you can start learning about [Types in Q#](xref:microsoft.quantum.guide.types).</span></span>

<span data-ttu-id="e88be-161">如果有兴趣了解有关 Q # 背后的基础和动机的详细信息，请查看[我们为什么需要 q #？](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/)。</span><span class="sxs-lookup"><span data-stu-id="e88be-161">If you are interested in learning more about the foundations and motivation behind Q#, check out [Why do we need Q#?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).</span></span>
