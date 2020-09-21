---
title: Q# 传授
description: 的基本概念 Q#
author: gillenhaalb
ms.author: a-gibec
ms.date: 02/28/2020
ms.topic: article
uid: microsoft.quantum.guide.basics
no-loc:
- Q#
- $$v
ms.openlocfilehash: 86f6538cf383f4e7c14255b38cfb1c141c8f991b
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835513"
---
# <a name="no-locq-basics"></a><span data-ttu-id="bcbf7-103">Q# 传授</span><span class="sxs-lookup"><span data-stu-id="bcbf7-103">Q# Basics</span></span>

<span data-ttu-id="bcbf7-104">本文简要介绍了的基本构建基块 Q# 。</span><span class="sxs-lookup"><span data-stu-id="bcbf7-104">This article presents a brief introduction to the basic building blocks of Q#.</span></span>

<span data-ttu-id="bcbf7-105">若要大致了解 Q# 作为量子开发工具包的基础组件的内容和位置，请参阅 [什么是 Q# ？](xref:microsoft.quantum.overview.q-sharp)。</span><span class="sxs-lookup"><span data-stu-id="bcbf7-105">For an overview of what Q# is and where it fits in as a fundamental component of the Quantum Development Kit, see [What is Q#?](xref:microsoft.quantum.overview.q-sharp).</span></span> 

## <a name="what-is-a-quantum-program"></a><span data-ttu-id="bcbf7-106">什么是量程计划？</span><span class="sxs-lookup"><span data-stu-id="bcbf7-106">What is a quantum program?</span></span>

<span data-ttu-id="bcbf7-107">从技术角度来看，量子计划是一组特定的传统子例程，它们在被调用时对量程系统执行特定操作。</span><span class="sxs-lookup"><span data-stu-id="bcbf7-107">From a technical perspective, a quantum program is a particular set of classical subroutines which, when called, perform certain operations on a quantum system.</span></span>
<span data-ttu-id="bcbf7-108">此视图的一个重要结果是， Q# 程序不直接对 qubits 建模，而是说明经典受控计算机如何与这些 qubits 进行交互。</span><span class="sxs-lookup"><span data-stu-id="bcbf7-108">An important consequence of that view is that a Q# program does not directly model qubits themselves, but rather describes how a classically controlled computer interacts with those qubits.</span></span>
<span data-ttu-id="bcbf7-109">按照设计，不 Q# 会直接定义量程机制的量程状态或其他属性。</span><span class="sxs-lookup"><span data-stu-id="bcbf7-109">By design, Q# does not define quantum states or other properties of quantum mechanics directly.</span></span>
<span data-ttu-id="bcbf7-110">例如，请考虑 "量程计算概念" 指南中讨论的状态 $ \ket{+} = \left ( \ket {0} + \ket {1} \right) /\sqrt {2} $。 [Quantum Computing Concepts](xref:microsoft.quantum.concepts.intro)</span><span class="sxs-lookup"><span data-stu-id="bcbf7-110">For instance, consider the state $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ discussed in the [Quantum Computing Concepts](xref:microsoft.quantum.concepts.intro) guide.</span></span>
<span data-ttu-id="bcbf7-111">若要在中准备此状态 Q# ，请从在 $ \ket $ 状态下初始化 qubits 的事实开始 {0} ，使用 $ \ket{+} = H\ket {0} $，其中 $H $ 是由该[ `H` 操作](xref:microsoft.quantum.intrinsic.h)实现的[Hadamard 转换](xref:microsoft.quantum.glossary#hadamard)。</span><span class="sxs-lookup"><span data-stu-id="bcbf7-111">To prepare this state in Q#, start with the facts that the qubits are initialized in the $\ket{0}$ state, and that $\ket{+} = H\ket{0}$, where $H$ is the [Hadamard transform](xref:microsoft.quantum.glossary#hadamard), implemented by the [`H` operation](xref:microsoft.quantum.intrinsic.h).</span></span> <span data-ttu-id="bcbf7-112">Q#用于初始化和转换 qubit 的基本代码如下所示：</span><span class="sxs-lookup"><span data-stu-id="bcbf7-112">The basic Q# code to initialize and transform a qubit, then, looks like this:</span></span>

```qsharp
using (qubit = Qubit()) {
    // At this point, the qubit is in the state |0⟩.
    H(qubit);
    // H is now applied, such that the qubit is in H|0⟩ = |+⟩, as desired.
}
```
<span data-ttu-id="bcbf7-113">有关初始化或 *分配*qubits 的详细信息，请参阅使用 [qubits](xref:microsoft.quantum.guide.qubits)。</span><span class="sxs-lookup"><span data-stu-id="bcbf7-113">For more information on initializing, or *allocating*, qubits, see [Working with qubits](xref:microsoft.quantum.guide.qubits).</span></span>

## <a name="quantum-states-in-no-locq"></a><span data-ttu-id="bcbf7-114">中的量程状态 Q#</span><span class="sxs-lookup"><span data-stu-id="bcbf7-114">Quantum states in Q#</span></span>

<span data-ttu-id="bcbf7-115">重要的是，上一程序不会显式引用中的状态， Q# 但会说明我们的程序如何 *转换* 状态。</span><span class="sxs-lookup"><span data-stu-id="bcbf7-115">Importantly, the previous program does not explicitly refer to the state within Q# but described how our program *transformed* the state.</span></span>
<span data-ttu-id="bcbf7-116">使用此方法时，您可以完全不确定量程状态在每台目标 *计算机上的* 状态，这可能会根据计算机的不同解释。</span><span class="sxs-lookup"><span data-stu-id="bcbf7-116">With this approach, you can be entirely agnostic about what a quantum state even *is* on each target machine, which might have different interpretations depending on the machine.</span></span> 

<span data-ttu-id="bcbf7-117">Q#程序无法 introspect 到 qubit 的状态。</span><span class="sxs-lookup"><span data-stu-id="bcbf7-117">A Q# program cannot introspect into the state of a qubit.</span></span>
<span data-ttu-id="bcbf7-118">相反，程序可以调用等操作 [`Measure`](xref:microsoft.quantum.intrinsic.measure) 来了解 qubit 中的信息，并调用操作（例如和） [`X`](xref:microsoft.quantum.intrinsic.x) [`H`](xref:microsoft.quantum.intrinsic.h) 来处理 qubit 的状态。</span><span class="sxs-lookup"><span data-stu-id="bcbf7-118">Instead, a program can call operations such as [`Measure`](xref:microsoft.quantum.intrinsic.measure) to learn information from a qubit, and call operations such as [`X`](xref:microsoft.quantum.intrinsic.x) and [`H`](xref:microsoft.quantum.intrinsic.h) to act on the state of a qubit.</span></span>
<span data-ttu-id="bcbf7-119">这些操作实际 *执行* 的操作仅由用于运行特定程序的目标计算机进行具体操作 Q# 。</span><span class="sxs-lookup"><span data-stu-id="bcbf7-119">What these operations actually *do* is only made concrete by the target machine used to run the particular Q# program.</span></span>
<span data-ttu-id="bcbf7-120">例如，如果在我们的 [全状态模拟器](xref:microsoft.quantum.machines.full-state-simulator)上运行程序，模拟器将对模拟的量程系统执行相应的数学运算。</span><span class="sxs-lookup"><span data-stu-id="bcbf7-120">For example, if running the program on our [full-state simulator](xref:microsoft.quantum.machines.full-state-simulator), the simulator performs the corresponding mathematical operations to the simulated quantum system.</span></span>
<span data-ttu-id="bcbf7-121">但在将来，如果目标计算机是真实的量程计算机，则在中调用此类操作会 Q# 指示量程计算机在*真实*的量程系统上执行相应的*实际*操作，例如，精确地计时激光脉冲) 。</span><span class="sxs-lookup"><span data-stu-id="bcbf7-121">But looking toward the future, when the target machine is a real quantum computer, calling such operations in Q# directs the quantum computer to perform the corresponding *real* operations on the *real* quantum system, for example, precisely timed laser pulses).</span></span>

<span data-ttu-id="bcbf7-122">Q#程序按照目标计算机的定义对这些操作进行 recombines，以创建新的更高级操作来表示量程计算。</span><span class="sxs-lookup"><span data-stu-id="bcbf7-122">A Q# program recombines these operations as defined by a target machine to create new, higher-level operations to express quantum computation.</span></span>
<span data-ttu-id="bcbf7-123">通过这种方式，可以 Q# 轻松地表达逻辑基础量程和混合量子–传统算法，同时也是对目标计算机或模拟器的结构的一般性。</span><span class="sxs-lookup"><span data-stu-id="bcbf7-123">In this way, Q# makes it easy to express the logic underlying quantum and hybrid quantum–classical algorithms, while also being general with respect to the structure of a target machine or simulator.</span></span>

## <a name="no-locq-operations-and-functions"></a><span data-ttu-id="bcbf7-124">Q# 操作和函数</span><span class="sxs-lookup"><span data-stu-id="bcbf7-124">Q# operations and functions</span></span>

<span data-ttu-id="bcbf7-125">具体而言， Q# 程序包含 *操作*、 *函数*和任何用户定义类型。</span><span class="sxs-lookup"><span data-stu-id="bcbf7-125">Concretely, a Q# program comprises *operations*, *functions*, and any user-defined types.</span></span> 

<span data-ttu-id="bcbf7-126">操作用于描述量程系统的转换，是最基本的程序构建块 Q# 。</span><span class="sxs-lookup"><span data-stu-id="bcbf7-126">Operations are used to describe the transformations of quantum systems and are the most fundamental building block of Q# programs.</span></span> <span data-ttu-id="bcbf7-127">在中定义的每个操作 Q# 都可以调用任意数量的其他操作。</span><span class="sxs-lookup"><span data-stu-id="bcbf7-127">Each operation defined in Q# may then call any number of other operations.</span></span>

<span data-ttu-id="bcbf7-128">与操作不同的是，函数用于描述纯 *确定性* 的传统行为，在计算传统值之外不会有任何影响。</span><span class="sxs-lookup"><span data-stu-id="bcbf7-128">In contrast to operations, functions are used to describe purely *deterministic* classical behavior and do not have any effects besides computing classical values.</span></span> <span data-ttu-id="bcbf7-129">例如，假设要在程序的末尾测量 qubits，并将测量结果添加到数组中。</span><span class="sxs-lookup"><span data-stu-id="bcbf7-129">For example, suppose you want to measure the qubits at the end of a program and add the measurement results to an array.</span></span>
<span data-ttu-id="bcbf7-130">在这种情况下， `Measure` 是一项 *操作* ，指示目标计算机对 (real 或模拟) qubits 执行测量。</span><span class="sxs-lookup"><span data-stu-id="bcbf7-130">In this case, `Measure` is an *operation* that instructs the target machine to perform a measurement on the (real or simulated) qubits.</span></span> <span data-ttu-id="bcbf7-131">同时， *函数* 会处理将返回结果添加到数组的传统过程。</span><span class="sxs-lookup"><span data-stu-id="bcbf7-131">At the same time, *functions* handle the classical process of adding the returned results to an array.</span></span>

<span data-ttu-id="bcbf7-132">操作和函数共同称为 *callables*。</span><span class="sxs-lookup"><span data-stu-id="bcbf7-132">Together, operations and functions are known as *callables*.</span></span> <span data-ttu-id="bcbf7-133">中介绍了其基础结构和行为，并详细介绍了[中 Q# 的操作和功能](xref:microsoft.quantum.guide.operationsfunctions)。</span><span class="sxs-lookup"><span data-stu-id="bcbf7-133">Their underlying structure and behavior are introduced and detailed in [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions).</span></span>


## <a name="no-locq-syntax-overview"></a><span data-ttu-id="bcbf7-134">Q# 语法概述</span><span class="sxs-lookup"><span data-stu-id="bcbf7-134">Q# syntax overview</span></span>

<span data-ttu-id="bcbf7-135">语言的语法描述形成语法正确的程序的符号的不同组合。</span><span class="sxs-lookup"><span data-stu-id="bcbf7-135">The syntax of a language describes the different combinations of symbols that form a syntactically correct program.</span></span>
<span data-ttu-id="bcbf7-136">在中 Q# ，语法元素分为三个不同的组：类型、表达式和语句。</span><span class="sxs-lookup"><span data-stu-id="bcbf7-136">In Q#, syntax elements are classified into three different groups: types, expressions, and statements.</span></span>

### <a name="types"></a><span data-ttu-id="bcbf7-137">类型</span><span class="sxs-lookup"><span data-stu-id="bcbf7-137">Types</span></span>
<span data-ttu-id="bcbf7-138">Q# 是一种强类型语言，因此，仔细使用类型有助于编译器在编译时提供有关程序的强大保证 Q# 。</span><span class="sxs-lookup"><span data-stu-id="bcbf7-138">Q# is a strongly-typed language, such that careful use of types can help the compiler provide strong guarantees about Q# programs at compile time.</span></span>
<span data-ttu-id="bcbf7-139">除了标准和特定于量程的内置基元类型（如、、 `Int` 和）之外， `Bool` 还为 `Qubit` `Result` Q# 用户定义的类型提供支持。</span><span class="sxs-lookup"><span data-stu-id="bcbf7-139">In addition to standard and quantum-specific built-in primitive types, for example, `Int`, `Bool`, `Qubit`, and `Result`, Q# provides support for user-defined types.</span></span>

<span data-ttu-id="bcbf7-140">有关所有基元类型、数组和元组类型的详细信息以及在文件中定义新类型的步骤的说明， Q# 请参阅[中 Q# 的类型](xref:microsoft.quantum.guide.types)。</span><span class="sxs-lookup"><span data-stu-id="bcbf7-140">For descriptions of all the primitive types, details for array and tuple types, and steps to define new types within a Q# file, see [Types in Q#](xref:microsoft.quantum.guide.types).</span></span>

### <a name="expressions"></a><span data-ttu-id="bcbf7-141">表达式</span><span class="sxs-lookup"><span data-stu-id="bcbf7-141">Expressions</span></span>
<span data-ttu-id="bcbf7-142">编程语言中的表达式是编程语言解释并计算为特定值的一个或多个常量、变量、运算符和函数的组合。</span><span class="sxs-lookup"><span data-stu-id="bcbf7-142">An expression in a programming language is a combination of one or more constants, variables, operators, and functions that the programming language interprets and evaluates to a specific value.</span></span>
<span data-ttu-id="bcbf7-143">大多数情况下，对于语言中的每个类型，该类型的表达式可以是 *文本* ，也可以是绑定到该类型的值的符号。</span><span class="sxs-lookup"><span data-stu-id="bcbf7-143">Most simply, for every type in a language, expressions of that type can be either *literals* or symbols bound to a value of that type.</span></span>
<span data-ttu-id="bcbf7-144">例如， `5` 是一个 `Int` 文字 (也是) 类型的表达式 `Int` ，如果符号 `count` 绑定到整数值 `5` ，则 `count` 也是整数表达式。</span><span class="sxs-lookup"><span data-stu-id="bcbf7-144">For example, `5` is an `Int` literal (thus also an expression of type `Int`), and if the symbol `count` is bound to the integer value `5`, then `count` is also an integer expression.</span></span>

<span data-ttu-id="bcbf7-145">此外，表达式还可以包含由特定运算符组合的其他表达式。</span><span class="sxs-lookup"><span data-stu-id="bcbf7-145">Additionally, an expression can consist of other expressions combined by certain operators.</span></span>
<span data-ttu-id="bcbf7-146">例如，另一个 `Int` 计算结果为的表达式 `5` 为 `2+3` 。</span><span class="sxs-lookup"><span data-stu-id="bcbf7-146">For example, another `Int` expression that evaluates to `5` is `2+3`.</span></span>

<span data-ttu-id="bcbf7-147">有关中的表达式和兼容运算符的详细信息 Q# ，请参阅[中 Q# 的类型表达式](xref:microsoft.quantum.guide.expressions)。</span><span class="sxs-lookup"><span data-stu-id="bcbf7-147">For more information about expressions and compatible operators in Q#, see [Type Expressions in Q#](xref:microsoft.quantum.guide.expressions).</span></span> 

### <a name="statements"></a><span data-ttu-id="bcbf7-148">语句</span><span class="sxs-lookup"><span data-stu-id="bcbf7-148">Statements</span></span> 
<span data-ttu-id="bcbf7-149">语句是命令式编程语言的语法单元，表示要执行的操作。语句与中的表达式相比，语句不会返回结果，而只是为其副作用而运行。</span><span class="sxs-lookup"><span data-stu-id="bcbf7-149">A statement is a syntactic unit of an imperative programming language that expresses some action to carry out. Statements contrast with expressions in that statements do not return results and are run solely for their side effects.</span></span> <span data-ttu-id="bcbf7-150">但表达式始终返回一个结果，并且通常不会有任何副作用。</span><span class="sxs-lookup"><span data-stu-id="bcbf7-150">Expressions, however, always return a result and often do not have any side effects.</span></span> <span data-ttu-id="bcbf7-151">简而言之， Q# 语句是在计算表达式时运行的。</span><span class="sxs-lookup"><span data-stu-id="bcbf7-151">In short, Q# statements are run, while expressions are evaluated.</span></span>

<span data-ttu-id="bcbf7-152">中语句的一个简单示例 Q# 是将符号赋给表达式：</span><span class="sxs-lookup"><span data-stu-id="bcbf7-152">A simple example of a statement in Q# is assigning a symbol to an expression:</span></span>
```qsharp
let count = 5;
```

<span data-ttu-id="bcbf7-153">更有趣的示例是 `for` 支持迭代并包含 *语句块*的语句。</span><span class="sxs-lookup"><span data-stu-id="bcbf7-153">A more interesting example is the `for` statement which supports iteration and includes a *statement block*.</span></span>
<span data-ttu-id="bcbf7-154">假设 `qubits` 符号绑定到) 的技术 (qubits 的寄存器 `Qubit[]` ，或类型的数组 `Qubit` 。</span><span class="sxs-lookup"><span data-stu-id="bcbf7-154">Suppose `qubits` is the symbol bound to a register of qubits (technically of type `Qubit[]`, or an array of `Qubit` types).</span></span> <span data-ttu-id="bcbf7-155">Then</span><span class="sxs-lookup"><span data-stu-id="bcbf7-155">Then</span></span>
```qsharp
for (qubit in qubits) {
    H(qubit);
}
```
<span data-ttu-id="bcbf7-156">是一个语句，它循环访问寄存器中的每个 qubit，并 `H` 对每个执行操作。</span><span class="sxs-lookup"><span data-stu-id="bcbf7-156">is a statement that iterates over each qubit in the register, performing the `H` operation on each one.</span></span> <span data-ttu-id="bcbf7-157">请注意，也 `H(qubit);` 是一条语句。</span><span class="sxs-lookup"><span data-stu-id="bcbf7-157">Note that `H(qubit);` is a statement in itself as well.</span></span>

<span data-ttu-id="bcbf7-158"> (类型，可以使用任何类型的调用表达式， `Unit` `Unit` 不会将任何信息作为语句返回) 。</span><span class="sxs-lookup"><span data-stu-id="bcbf7-158">You can use any call expression of type `Unit` (a `Unit` type does not return any information) as a statement.</span></span>
<span data-ttu-id="bcbf7-159">当对返回的 qubits 调用操作时，这种类型的表达式非常有用， `Unit` 因为语句的目的是修改隐式量程状态。</span><span class="sxs-lookup"><span data-stu-id="bcbf7-159">This type of expression is useful when calling operations on qubits that return `Unit` because the purpose of the statement is to modify the implicit quantum state.</span></span>
<span data-ttu-id="bcbf7-160">表达式计算语句需要终止分号。</span><span class="sxs-lookup"><span data-stu-id="bcbf7-160">Expression evaluation statements require a terminating semicolon.</span></span>

<span data-ttu-id="bcbf7-161">您可以使用语句来构建程序的几乎每个方面 Q# ，而不能有任何一页包含与它们相关的所有信息。</span><span class="sxs-lookup"><span data-stu-id="bcbf7-161">You use statements to build nearly every aspect of a Q# program, and no single page could encompass all the information relating to them.</span></span>
<span data-ttu-id="bcbf7-162">有关其词法结构和格式设置的详细信息，请参阅[ Q# 文件结构](xref:microsoft.quantum.guide.filestructure); 有关符号绑定分配和作用域的详细信息，请参阅[ Q# 中的变量](xref:microsoft.quantum.guide.variables); 对于控制流循环（例如 `for` ），请参阅[中 Q# 的控制流](xref:microsoft.quantum.guide.controlflow)。</span><span class="sxs-lookup"><span data-stu-id="bcbf7-162">For more information about their lexical structure and formatting, see [Q# File Structure](xref:microsoft.quantum.guide.filestructure); for symbol binding assignment and scope, see [Variables in Q#](xref:microsoft.quantum.guide.variables); and for control flow loops such as `for`, see [Control Flow in Q#](xref:microsoft.quantum.guide.controlflow).</span></span>

## <a name="next-steps"></a><span data-ttu-id="bcbf7-163">后续步骤</span><span class="sxs-lookup"><span data-stu-id="bcbf7-163">Next steps</span></span>

<span data-ttu-id="bcbf7-164">开始了解[中的 Q# 类型](xref:microsoft.quantum.guide.types)。</span><span class="sxs-lookup"><span data-stu-id="bcbf7-164">Start learning about [Types in Q#](xref:microsoft.quantum.guide.types).</span></span>

<span data-ttu-id="bcbf7-165">有关基础知识和动机的更多背景信息 Q# ，请参阅 [为什么需要这样做 Q# ？](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/)。</span><span class="sxs-lookup"><span data-stu-id="bcbf7-165">For more background about the foundations and motivation behind Q#, see [Why do we need Q#?](https://devblogs.microsoft.com/qsharp/why-do-we-need-q/).</span></span>
