---
title: 什么是 Q# 和 QDK？
description: 了解 Q#，这是 Microsoft 创建的一种用来开发量子计算机应用程序的编程语言，并且是 Microsoft Quantum 开发工具包的关键组件
author: natke
ms.author: nakersha
ms.date: 10/22/2019
ms.topic: article
uid: microsoft.quantum.overview.qsharp
ms.openlocfilehash: a4bf21887e34ac85f75e5e0b9a033138464fd09d
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906995"
---
# <a name="what-are-q-and-the-qdk"></a><span data-ttu-id="20974-103">什么是 Q# 和 QDK？</span><span class="sxs-lookup"><span data-stu-id="20974-103">What are Q# and the QDK?</span></span>

<span data-ttu-id="20974-104">Q# 是一种编程语言，具有专门设计用于量子计算的功能。</span><span class="sxs-lookup"><span data-stu-id="20974-104">Q# is a programming language with features specifically designed for use with quantum computing.</span></span>
<span data-ttu-id="20974-105">作为 Microsoft Quantum 开发工具包 (QDK) 的关键组件，它为量子程序员提供了一个框架，使他们能够专注于算法，而无需担心技术细节，如门序列优化或量子计算机的物理实现。</span><span class="sxs-lookup"><span data-stu-id="20974-105">As a key component of Microsoft's Quantum Development Kit (QDK), it provides quantum programmers a framework that allows you to focus on the algorithms without having to worry about technical details like gate sequence optimization or the physical implementation of a quantum computer.</span></span>

<span data-ttu-id="20974-106">QDK 包含各种工具，这些工具为开发人员提供开始编写量子程序所需的一切。</span><span class="sxs-lookup"><span data-stu-id="20974-106">The QDK comprises a wide range of tools which give developers everything they need to start writing quantum programs.</span></span>
<span data-ttu-id="20974-107">除了 Q# 语言，QDK 还包括：</span><span class="sxs-lookup"><span data-stu-id="20974-107">Alongside the Q# language, the QDK includes:</span></span>
* <span data-ttu-id="20974-108">*Q# 库*，它使开发人员可以立即成功上手并创建现实世界的量子应用程序</span><span class="sxs-lookup"><span data-stu-id="20974-108">the *Q# libraries*, which allow developers to hit the ground running and create real-world quantum applications today</span></span>
* <span data-ttu-id="20974-109">可运行 Q# 程序的各种*目标计算机*。</span><span class="sxs-lookup"><span data-stu-id="20974-109">various *target machines* on which Q# programs can be run.</span></span> <span data-ttu-id="20974-110">其中包括适用于较大量子程序的资源估算器和模拟器，以及作为无干扰量子计算机运行的全状态量子模拟器。</span><span class="sxs-lookup"><span data-stu-id="20974-110">These include resource estimators and simulators for larger quantum programs, as well as a full-state quantum simulator, which behaves as a noise-free quantum computer.</span></span> <span data-ttu-id="20974-111">后者非常适用于改进构想、调试程序和了解量子物理学，但仅对量子位相对较少的程序有效。</span><span class="sxs-lookup"><span data-stu-id="20974-111">The latter is very useful for tinkering with ideas, debugging programs, and learning about quantum physics, but only efficient for programs with relatively few qubits.</span></span> <span data-ttu-id="20974-112">我们非常期待将来可以使量子计算硬件用作目标计算机。</span><span class="sxs-lookup"><span data-stu-id="20974-112">We're very much looking forward to making quantum computing hardware available as target machines in the future.</span></span>
* <span data-ttu-id="20974-113">*工具*，用于使得使用 Q# 尽可能顺畅，如 Visual Studio 和 VS Code 的扩展，以及用于 Python 和 Jupyter Notebook 的包。</span><span class="sxs-lookup"><span data-stu-id="20974-113">*tools* for making work with Q# as seamless as possible, such as extensions for Visual Studio and VS Code, and packages for use with Python and Jupyter Notebooks.</span></span>
* <span data-ttu-id="20974-114">*API 文档*，用于将 Q# 与经典宿主语言（例如 Python 和 C#）配对</span><span class="sxs-lookup"><span data-stu-id="20974-114">*API documentation* for pairing Q# with classical host languages such as Python and C#</span></span>

<span data-ttu-id="20974-115">使用 Microsoft Quantum 开发工具包开发的应用程序通常由两个部分组成：</span><span class="sxs-lookup"><span data-stu-id="20974-115">Applications developed with Microsoft's Quantum Development Kit typically consist of two parts:</span></span>
1. <span data-ttu-id="20974-116">使用 Q# 量子编程语言实现并由经典宿主程序调用的一个或多个量子算法。</span><span class="sxs-lookup"><span data-stu-id="20974-116">One or more quantum algorithms, implemented using the Q# quantum programming language, and invoked by the classical host program.</span></span> <span data-ttu-id="20974-117">其中包括</span><span class="sxs-lookup"><span data-stu-id="20974-117">These consist of</span></span> 
    - <span data-ttu-id="20974-118">Q# 操作：包含量子操作的子例程；以及</span><span class="sxs-lookup"><span data-stu-id="20974-118">Q# operations: subroutines containing quantum operations, and</span></span> 
    - <span data-ttu-id="20974-119">Q# 函数：在量子算法内使用的经典子例程。</span><span class="sxs-lookup"><span data-stu-id="20974-119">Q# functions: classical subroutines used within the quantum algorithm.</span></span>
2. <span data-ttu-id="20974-120">充当主入口点的经典程序（使用 Python 或 C# 等编程语言实现）将在需要执行量子算法时调用 Q# 运算。</span><span class="sxs-lookup"><span data-stu-id="20974-120">A classical program, implemented in a classical programming language like Python or C#, that serves as the main entry point and will invoke Q# operations when it wants to execute a quantum algorithm.</span></span>

## <a name="write-quantum-programs-not-quantum-circuits"></a><span data-ttu-id="20974-121">编写量子程序，而不是量子线路</span><span class="sxs-lookup"><span data-stu-id="20974-121">Write quantum programs, not quantum circuits</span></span>

<span data-ttu-id="20974-122">早期的量子计算时代，算法以图形（类似于经典计算中的线路图）方式表示。</span><span class="sxs-lookup"><span data-stu-id="20974-122">In the early days of quantum computing algorithms were visualized as diagrams similarly to circuit diagrams in classical computing.</span></span>
<span data-ttu-id="20974-123">虽然线路模型在量子计算研究方面一直有用，但 Microsoft 认为，开发者可以超越量子电路，使用 Q# 开发量子算法和应用程序。</span><span class="sxs-lookup"><span data-stu-id="20974-123">While the circuit model has been useful for many years in quantum computing research, here at Microsoft, we believe that developers can go beyond quantum circuits and develop quantum algorithms and applications using Q#.</span></span>
<span data-ttu-id="20974-124">使用 Q# 语言时，可以直接利用我们在数十年的经典软件开发中学到的经验，并且它还为量子开发者提供了针对量子计算的高级语言功能。</span><span class="sxs-lookup"><span data-stu-id="20974-124">The Q# language was built to take advantage of what we’ve learned through decades of classical software development, and empower quantum developers with high-level language functionality targeted for quantum computing.</span></span>

## <a name="how-does-q-work"></a><span data-ttu-id="20974-125">Q# 的工作原理是什么？</span><span class="sxs-lookup"><span data-stu-id="20974-125">How does Q# work?</span></span>

<span data-ttu-id="20974-126">Q# 编程语言提供了一组直观的类型、运算和逻辑表达式来开发算法，因此使用者无需担心量子计算机的内部逻辑。</span><span class="sxs-lookup"><span data-stu-id="20974-126">The Q# programming language provides you with an intuitive set of types, operations, and logic expressions to develop algorithms without having to worry about the internal logic of the quantum computer.</span></span>

<span data-ttu-id="20974-127">Q# 的基本构建基块之一是 `Qubit` 类型，它不能复制，也不能直接访问，就像真实的量子位。</span><span class="sxs-lookup"><span data-stu-id="20974-127">One of the fundamental building blocks of Q# is the `Qubit` type, which cannot be copied or directly accessed, just like a real qubit.</span></span>
<span data-ttu-id="20974-128">相反，我们可以对其进行度量并将度量结果存储在 `Result` 变量中，这种 Q# 类型可以采用两个可能的值：`Zero` 和 `One`。</span><span class="sxs-lookup"><span data-stu-id="20974-128">Instead, we can measure it and store the outcome of the measurement in a `Result` variable, a Q# type that can take two possible values: `Zero` and `One`.</span></span>
<span data-ttu-id="20974-129">此类构造可保证算法始终遵守量子物理学定律，并可在量子计算机或模拟器上正常运行。</span><span class="sxs-lookup"><span data-stu-id="20974-129">Constructs like this one guarantee that algorithms always respect the laws of quantum physics and can run correctly on quantum computers or simulators.</span></span>

<span data-ttu-id="20974-130">Q# 还包括经典逻辑功能（如条件和循环），这些功能又有些微不同，以确保遵循所有量子定律。</span><span class="sxs-lookup"><span data-stu-id="20974-130">Q# also includes classical logic features like conditionals and loops with some subtleties to make sure that all the quantum rules are being respected.</span></span>
<span data-ttu-id="20974-131">例如，约束执行循环的方式，以确保不在可能只包含确定性经典子例程的函数中调用量子运算。</span><span class="sxs-lookup"><span data-stu-id="20974-131">For example, constraining the way loops are executed to ensure that quantum operations are not called within functions which may only contain deterministic classical subroutines.</span></span>

<span data-ttu-id="20974-132">Q# 程序通常与用 C# 或 Python 编写的主机程序配对使用，可以方便地整理经典代码和量子代码。</span><span class="sxs-lookup"><span data-stu-id="20974-132">Q# programs are often paired with a host program written in C# or Python, which can provide convenient organization of classical and quantum code.</span></span>
<span data-ttu-id="20974-133">除了支持 C# 和 Python 之类的语言，QDK 还提供 IQ# Jupyter 内核，因此支持 Jupyter Notebook。</span><span class="sxs-lookup"><span data-stu-id="20974-133">In addition to supporting languages such as C# and Python, the QDK provides Jupyter Notebook support with the IQ# Jupyter kernel.</span></span>

## <a name="what-can-i-use-q-for"></a><span data-ttu-id="20974-134">Q# 有哪些用途？</span><span class="sxs-lookup"><span data-stu-id="20974-134">What can I use Q# for?</span></span>

### <a name="use-q-to-learn-quantum-computing"></a><span data-ttu-id="20974-135">使用 Q# 学习量子计算</span><span class="sxs-lookup"><span data-stu-id="20974-135">Use Q# to learn quantum computing</span></span>

<span data-ttu-id="20974-136">到目前为止，要学习量子计算，需要学习电路模型以理解量子门和度量有序序列形式的算法。</span><span class="sxs-lookup"><span data-stu-id="20974-136">Until now, to learn quantum computing you needed to learn the circuit model to understand the algorithms in the form of ordered sequences of quantum gates and measurements.</span></span> <span data-ttu-id="20974-137">使用 Q# 时，你也可以采用另一种方式：通过编写量子程序来学习量子计算。</span><span class="sxs-lookup"><span data-stu-id="20974-137">With Q# you can take another path: learn quantum computing by writing quantum programs.</span></span>

### <a name="use-q-to-design-quantum-algorithms"></a><span data-ttu-id="20974-138">使用 Q# 设计量子算法</span><span class="sxs-lookup"><span data-stu-id="20974-138">Use Q# to design quantum algorithms</span></span>

<span data-ttu-id="20974-139">Q# 提供了越来越多的库和用户定义类型，有助于实现各种工具并生成高级量子算法。</span><span class="sxs-lookup"><span data-stu-id="20974-139">Q# provides you with an increasing number of libraries and user-defined types that will help you to implement tools and build advanced quantum algorithms.</span></span> <span data-ttu-id="20974-140">例如，你需要纠缠双量子位 q1 和 q2。</span><span class="sxs-lookup"><span data-stu-id="20974-140">For example, you need to entangle two-qubits q1 and q2?</span></span> <span data-ttu-id="20974-141">可以使用已内置的运算 `PrepareEntangledState([q1], [q2])`，而不是单独应用必要的门来纠缠量子位。</span><span class="sxs-lookup"><span data-stu-id="20974-141">Instead of applying individually the necessary gates to get the qubits entangled you can use the already built-in operation `PrepareEntangledState([q1], [q2])`.</span></span>

### <a name="use-q-to-estimate-quantum-resources"></a><span data-ttu-id="20974-142">使用 Q# 估算量子资源</span><span class="sxs-lookup"><span data-stu-id="20974-142">Use Q# to estimate quantum resources</span></span>

<span data-ttu-id="20974-143">可以使用 Quantum 开发工具包 (QDK) 随附的全状态量子模拟器模拟 Q# 程序的执行。</span><span class="sxs-lookup"><span data-stu-id="20974-143">You can simulate the execution of your Q# program using the full state quantum simulator that is provided with the Quantum Development Kit (QDK).</span></span>  <span data-ttu-id="20974-144">QDK 还提供资源模拟器，让你了解那些因太大而无法在模拟器上运行的 Q# 程序的性能。</span><span class="sxs-lookup"><span data-stu-id="20974-144">The QDK also provides resource estimators that give you insights on the performance of Q# programs that are too large to be run on a simulator.</span></span>  <span data-ttu-id="20974-145">这对算法设计者来说具有很高的价值，因为他们可以调整其程序，让其使用较少的资源（运行较少数目的量子位来执行较少数目的操作）在早期的规模较小的量子硬件上运行。</span><span class="sxs-lookup"><span data-stu-id="20974-145">This is highly valuable for algorithm designers, because they can tune their programs to use fewer resources (e.g. fewer number of qubits running for fewer numbers of operations), to run on earlier smaller scale quantum hardware.</span></span>

### <a name="use-q-to-validate-hardware-performance"></a><span data-ttu-id="20974-146">使用 Q# 验证硬件性能</span><span class="sxs-lookup"><span data-stu-id="20974-146">Use Q# to validate hardware performance</span></span>

<span data-ttu-id="20974-147">Q# 的优点是，一个程序只需编写一次，然后即可在量子模拟器上进行调试性运行，以及在不同的量子计算机硬件上运行。</span><span class="sxs-lookup"><span data-stu-id="20974-147">The beauty of Q# is that a program can be written once and run on quantum simulators for debugging, and run on different quantum computer hardware.</span></span>  <span data-ttu-id="20974-148">随着量子计算机的发展和新的量子计算机的发布，可以运行以 Q# 编写的基准程序来验证硬件性能并对结果进行比较。</span><span class="sxs-lookup"><span data-stu-id="20974-148">Benchmark programs written in Q# can be run to validate hardware performance and compare results as quantum computers evolve and new quantum computers become available.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="20974-149">后续步骤</span><span class="sxs-lookup"><span data-stu-id="20974-149">Next steps</span></span>

* [<span data-ttu-id="20974-150">如何了解量子计算？</span><span class="sxs-lookup"><span data-stu-id="20974-150">How do I learn about quantum computing?</span></span>](xref:microsoft.quantum.overview.learn)
* [<span data-ttu-id="20974-151">Microsoft Quantum 开发工具包入门</span><span class="sxs-lookup"><span data-stu-id="20974-151">Get started with the Microsoft Quantum Development Kit</span></span>](xref:microsoft.quantum.welcome)
