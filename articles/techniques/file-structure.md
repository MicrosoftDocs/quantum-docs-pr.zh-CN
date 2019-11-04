---
title: 量程开发技巧简介 |Microsoft Docs
description: 量程开发技巧简介
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 702d23293a1c340ddd3d7032d0e05294345469b2
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442562"
---
# <a name="q-program-overview"></a><span data-ttu-id="c453f-103">Q # 计划概述</span><span class="sxs-lookup"><span data-stu-id="c453f-103">Q# program overview</span></span>

<span data-ttu-id="c453f-104">Q # 是一种可扩展的多模式域特定编程语言，用于量程计算。</span><span class="sxs-lookup"><span data-stu-id="c453f-104">Q# is a scalable, multi-paradigm, domain-specific programming language for quantum computing.</span></span> <span data-ttu-id="c453f-105">Q # 是一种量程编程语言，因为它可用于描述在量程计算机上执行指令的方式。</span><span class="sxs-lookup"><span data-stu-id="c453f-105">Q# is a quantum programming language in that it can be used to describe how instructions are executed on quantum machines.</span></span> <span data-ttu-id="c453f-106">可从模拟器到实际的量程硬件的目标计算机。</span><span class="sxs-lookup"><span data-stu-id="c453f-106">The machines that can be targeted range from simulators to actual quantum hardware.</span></span> <span data-ttu-id="c453f-107">Q # 是可缩放的：它可用于编写简单的演示程序，如在几个 qubits 上运行的传送，但也支持编写大量复杂的程序，例如模拟复杂的分子，这些程序需要使用数百万的 qubits 大型计算机。</span><span class="sxs-lookup"><span data-stu-id="c453f-107">Q# is scalable: it can be used to write simple demonstration programs like teleport that run on a few qubits, but also supports writing large, sophisticated programs such as simulations of complex molecules that will require large machines with millions of qubits.</span></span> <span data-ttu-id="c453f-108">即使大型物理计算机仍在将来，Q # 也能让程序员立即对复杂的量程算法进行编程。</span><span class="sxs-lookup"><span data-stu-id="c453f-108">Even though large physical machines are still in the future, Q# allows a programmer to program complex quantum algorithms now.</span></span> <span data-ttu-id="c453f-109">此外，Q # 支持各种任务，如调试、分析、资源估算，以及以可缩放方式进行的特定用途模拟。</span><span class="sxs-lookup"><span data-stu-id="c453f-109">What is more, Q# supports various tasks such as debugging, profiling, resource estimation, and certain special-purpose simulations in a scalable way.</span></span> 

<span data-ttu-id="c453f-110">从技术角度看，可以将量程程序视为一组特定的传统函数，在调用这些函数时，会生成量程线路作为其副作用。</span><span class="sxs-lookup"><span data-stu-id="c453f-110">From a technical perspective, a quantum program can be seen as a particular set of classical functions which, when called, generate quantum circuits as their side effects.</span></span> <span data-ttu-id="c453f-111">此视图的一个重要结果是，以 Q # 编写的程序不会直接对 qubits 建模，而是介绍传统的控制计算机如何与这些 qubits 交互。</span><span class="sxs-lookup"><span data-stu-id="c453f-111">An important consequence of that view is that a program written in Q# does not directly model qubits themselves, but rather describes how a classical control computer interacts with those qubits.</span></span>
<span data-ttu-id="c453f-112">按照设计，Q # 不会直接定义量程机制的量程状态或其他属性，而是通过语言中定义的各种子例程的操作间接定义。</span><span class="sxs-lookup"><span data-stu-id="c453f-112">By design, Q# thus does not define quantum states or other properties of quantum mechanics directly, but rather does so indirectly through the action of the various subroutines defined in the language.</span></span>
<span data-ttu-id="c453f-113">例如，请考虑[量程计算概念](xref:microsoft.quantum.concepts.intro)指南中讨论的状态 $ \ket{+} = \left （\ket{0} + \ket{1}\right）/\sqrt{2}$。</span><span class="sxs-lookup"><span data-stu-id="c453f-113">For instance, consider the state $\ket{+} = \left(\ket{0} + \ket{1}\right) / \sqrt{2}$ discussed in the [Quantum Computing Concepts](xref:microsoft.quantum.concepts.intro) guide.</span></span>
<span data-ttu-id="c453f-114">若要在 Q # 中准备此状态，我们将使用在 $ \ket{0}$ 状态下初始化 qubits 的事实，并使用 $ \ket{+} = H\ket{0}$，其中 $H $ 是 Hadamard 转换：</span><span class="sxs-lookup"><span data-stu-id="c453f-114">To prepare this state in Q#, we use the facts that the qubits are initialized in the $\ket{0}$ state, and that $\ket{+} = H\ket{0}$, where $H$ is the Hadamard transform:</span></span>

```qsharp
using (qubit = Qubit()) {
    // At this point, qubit is in the state |0〉.
    H(qubit);
    // We've now applied H, such that our qubit is in H|0〉 = |+〉, as we wanted.
}
```
## <a name="q-tranformations-of-quantum-states"></a><span data-ttu-id="c453f-115">Q # 状态的转换</span><span class="sxs-lookup"><span data-stu-id="c453f-115">Q# tranformations of quantum states</span></span>

<span data-ttu-id="c453f-116">重要的是，在编写上述程序时，我们未显式引用 Q # 中的状态，而是说明了该状态是由程序*转换*的。</span><span class="sxs-lookup"><span data-stu-id="c453f-116">Importantly, in writing the above program, we did not explicitly refer to the state within Q#, but rather described how the state was *transformed* by our program.</span></span>
<span data-ttu-id="c453f-117">因此，与图形着色器程序将转换说明累积到每个顶点的方式类似，Q # 中的量程计划将转换为量程状态。</span><span class="sxs-lookup"><span data-stu-id="c453f-117">Thus, similar to how a graphics shader program accumulates a description of transformations to each vertex, a quantum program in Q# accumulates transformations to quantum states.</span></span>
<span data-ttu-id="c453f-118">这使我们完全不知道量程状态在每台目标计算机*上的*状态，这可能会根据计算机的不同解释。</span><span class="sxs-lookup"><span data-stu-id="c453f-118">This allows us to be entirely agnostic about what a quantum state even *is* on each target machine, which might have different interpretations depending on the machine.</span></span> 

<span data-ttu-id="c453f-119">从 Q # 程序的角度来看，qubit 是对目标计算机内部结构的完全不透明引用。</span><span class="sxs-lookup"><span data-stu-id="c453f-119">From the perspective of a Q# program, a qubit is an entirely opaque reference to the internal structure of a target machine.</span></span>
<span data-ttu-id="c453f-120">Q # 程序无法 introspect qubit 的状态、其在目标计算机上的表示形式，甚至与该程序提供的任何其他 qubit 相同 qubit。</span><span class="sxs-lookup"><span data-stu-id="c453f-120">A Q# program has no ability to introspect into the state of a qubit, its representation on a target machine, or even whether it is the same qubit as any other qubit available to the program.</span></span>
<span data-ttu-id="c453f-121">相反，程序可以调用 `Measure` 等操作来了解 qubit 中的信息，并调用操作（例如 `X` 和 `H`）来操作 qubit 的状态。</span><span class="sxs-lookup"><span data-stu-id="c453f-121">Rather, a program can call operations such as `Measure` to learn information from a qubit, and call operations such as `X` and `H` to act on the state of a qubit.</span></span>
<span data-ttu-id="c453f-122">这些操作在语言中没有内部定义，只是用于运行特定 Q # 程序的目标计算机。</span><span class="sxs-lookup"><span data-stu-id="c453f-122">These operations have no intrinsic definition within the language, and are made concrete only by the target machine used to run a particular Q# program.</span></span>
<span data-ttu-id="c453f-123">Q # 计划 recombines 目标计算机定义的操作，以创建新的更高级操作来表示量程计算。</span><span class="sxs-lookup"><span data-stu-id="c453f-123">A Q# program recombines these operations as defined by a target machine to create new, higher-level operations to express quantum computation.</span></span>
<span data-ttu-id="c453f-124">通过这种方式，使用 Q # 可以轻松地表达逻辑基础量程和混合量子-传统算法，同时也是对目标计算机或模拟器的结构的一般性。</span><span class="sxs-lookup"><span data-stu-id="c453f-124">In this way, Q# makes it easy to express the logic underlying quantum and hybrid quantum-classical algorithms, while also being general with respect to the structure of a target machine or simulator.</span></span>

## <a name="q-operations-and-functions"></a><span data-ttu-id="c453f-125">Q # 操作和函数</span><span class="sxs-lookup"><span data-stu-id="c453f-125">Q# operations and functions</span></span>

<span data-ttu-id="c453f-126">具体而言，Q # 程序由一个或多个*操作*、一个或多个*函数*和用户定义的类型组成。</span><span class="sxs-lookup"><span data-stu-id="c453f-126">Concretely, a Q# program is comprised of one or more *operations*, one or more *functions*, and user defined types.</span></span> <span data-ttu-id="c453f-127">操作用于描述量程计算机状态的转换，是 Q # 程序的最基本构建基块。</span><span class="sxs-lookup"><span data-stu-id="c453f-127">Operations are used to describe the transformations of the state of a quantum machine and are the most basic building block of Q# programs.</span></span> <span data-ttu-id="c453f-128">在 Q # 中定义的每个操作都可以调用任意数量的其他操作，包括由目标计算机实现的内置*内部*操作。</span><span class="sxs-lookup"><span data-stu-id="c453f-128">Each operation defined in Q# may then call any number of other operations, including the built-in *intrinsic* operations implemented by a target machine.</span></span>
<span data-ttu-id="c453f-129">在编译时，每个操作都表示为可提供给目标计算机的 .NET 类类型。</span><span class="sxs-lookup"><span data-stu-id="c453f-129">When compiled, each operation is represented as a .NET class type that can be provided to target machines.</span></span>

<span data-ttu-id="c453f-130">与操作不同的是，函数用于描述纯粹的传统行为，在计算经典输出值以外，不会产生任何影响。</span><span class="sxs-lookup"><span data-stu-id="c453f-130">In contrast to operations, functions are used to describe purely classical behavior and do not have any effects besides computing classical output values.</span></span> <span data-ttu-id="c453f-131">Q # 是一种强类型语言，附带一组内置的基元类型以及对用户定义类型的支持。</span><span class="sxs-lookup"><span data-stu-id="c453f-131">Q# is a strongly typed language and comes with a set of built-in primitive types as well as support for user defined types.</span></span> 

<span data-ttu-id="c453f-132">在本指南的其余部分，我们将了解如何使用不同的语言概念和构造，帮助我们通过操作、函数和类型的基本构建块来定义复杂的量程程序。</span><span class="sxs-lookup"><span data-stu-id="c453f-132">Throughout the rest of this guide, we will see how to use different language concepts and constructs to help us define complex quantum programs through the basic building blocks of operations, functions, and types.</span></span> 

## <a name="structure-of-q-source-files"></a><span data-ttu-id="c453f-133">Q # 源文件的结构</span><span class="sxs-lookup"><span data-stu-id="c453f-133">Structure of Q# Source Files</span></span>

<span data-ttu-id="c453f-134">Q # 源文件至少包含一个*命名空间声明*，该声明指定 .net 命名空间，该命名空间将包含源文件中的定义。</span><span class="sxs-lookup"><span data-stu-id="c453f-134">Minimally, a Q# source file consists of a *namespace declaration*, which specifies a .NET namespace which will contain the definitions in the source file.</span></span>
<span data-ttu-id="c453f-135">可以使用 `open` 语句包含其他 Q # 源文件和库中的定义。</span><span class="sxs-lookup"><span data-stu-id="c453f-135">Definitions from other Q# source files and libraries can be included using the `open` statement.</span></span>
<span data-ttu-id="c453f-136">例如，大多数定义基本入口的操作都在 <xref:microsoft.quantum.intrinsic> 命名空间中定义。</span><span class="sxs-lookup"><span data-stu-id="c453f-136">For instance, most of the operations defining fundamental gates are defined in the <xref:microsoft.quantum.intrinsic> namespace.</span></span>
<span data-ttu-id="c453f-137">为了使其可供我们的代码使用，只需在每个文件的顶部 `open` 该命名空间即可：</span><span class="sxs-lookup"><span data-stu-id="c453f-137">To make this available to our code, we simply `open` that namespace at the top of each file:</span></span>

```qsharp
namespace Example {
    open Microsoft.Quantum.Intrinsic;

    // ...
}
```

<span data-ttu-id="c453f-138">在命名空间中，每个 Q # 源文件可以定义*操作*、*函数*和*用户定义类型*的任意组合。</span><span class="sxs-lookup"><span data-stu-id="c453f-138">Within a namespace, each Q# source file can define any combination of *operations*, *functions*, and *user-defined types*.</span></span>
<span data-ttu-id="c453f-139">本部分的其余部分将依次介绍每个，并提供一些示例，说明如何在实践中使用它们来做出有用的量程计划。</span><span class="sxs-lookup"><span data-stu-id="c453f-139">In the rest of this section, we will describe each in turn and provide examples of how they can be used in practice to make useful quantum programs.</span></span>
