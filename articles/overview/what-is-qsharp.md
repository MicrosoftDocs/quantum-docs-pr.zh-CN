---
title: 什么是 Q#？
description: 了解如何使用 Microsoft 创建的编程语言 Q# 来开发量子计算机应用程序
author: natke
ms.author: nakersha
ms.date: 10/22/2019
ms.topic: article
uid: microsoft.quantum.overview.qsharp
ms.openlocfilehash: e04d72bafe390ff5c79af408db1d9400754b06ce
ms.sourcegitcommit: 27c9bf1aae923527aa5adeaee073cb27d35c0ca1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/05/2019
ms.locfileid: "74864281"
---
# <a name="what-is-q"></a><span data-ttu-id="a33f8-103">什么是 Q#？</span><span class="sxs-lookup"><span data-stu-id="a33f8-103">What is Q#?</span></span>

<span data-ttu-id="a33f8-104">Q# 是一种编程语言，具有量子计算特有的功能。</span><span class="sxs-lookup"><span data-stu-id="a33f8-104">Q# is a programming language with features that are special to quantum computing.</span></span>

<span data-ttu-id="a33f8-105">Q# 为量子程序员提供了一个框架，使他们能够专注于算法，而无需考虑技术细节，如门序列优化或量子计算机的物理实现。</span><span class="sxs-lookup"><span data-stu-id="a33f8-105">Q# provides quantum programmers a framework that allows you to focus on the algorithms without having to care about technical details like gate sequence optimization or the physical implementation of a quantum computer.</span></span>

<span data-ttu-id="a33f8-106">Q# 编程语言提供了一组直观的类型、运算和逻辑表达式来开发算法，因此使用者无需担心量子计算机的内部逻辑。</span><span class="sxs-lookup"><span data-stu-id="a33f8-106">The Q# programming language provides you with an intuitive set of types, operations, and logic expressions to develop algorithms without having to worry about the internal logic of the quantum computer.</span></span>

## <a name="code-algorithms"></a><span data-ttu-id="a33f8-107">代码算法</span><span class="sxs-lookup"><span data-stu-id="a33f8-107">Code algorithms</span></span>

<span data-ttu-id="a33f8-108">早期的量子计算时代，算法以图形（类似于经典计算中的线路图）方式表示。</span><span class="sxs-lookup"><span data-stu-id="a33f8-108">In the early days of quantum computing algorithms were visualized as diagrams similarly to circuit diagrams in classical computing.</span></span>  <span data-ttu-id="a33f8-109">虽然线路模型在量子计算研究方面一直有用，但 Microsoft 认为，开发者可以超越量子电路，使用 Q# 开发量子算法和应用程序。</span><span class="sxs-lookup"><span data-stu-id="a33f8-109">While the circuit model has been useful for many years in quantum computing research, here at Microsoft, we believe that developers can go beyond quantum circuits and develop quantum algorithms and applications using Q#.</span></span> <span data-ttu-id="a33f8-110">使用 Q# 语言时，可以直接利用我们在数十年的经典软件开发中学到的经验，并且它还为量子开发者提供了针对量子计算的高级语言功能。</span><span class="sxs-lookup"><span data-stu-id="a33f8-110">The Q# language was built to take advantage of what we’ve learned through decades of classical software development, and empower quantum developers with high-level language functionality targeted for quantum computing.</span></span>

## <a name="how-does-q-work"></a><span data-ttu-id="a33f8-111">Q# 的工作原理是什么？</span><span class="sxs-lookup"><span data-stu-id="a33f8-111">How does Q# work?</span></span>

<span data-ttu-id="a33f8-112">Q# 的基本构建基块之一是 `Qubit` 类型，它不能复制，也不能直接访问，就像真实的量子位。</span><span class="sxs-lookup"><span data-stu-id="a33f8-112">One of the fundamental building blocks of Q# is the `Qubit` type, which cannot be copied or directly accessed, just like a real qubit.</span></span> <span data-ttu-id="a33f8-113">相反，我们可以对其进行度量并将度量结果存储在 `Result` 变量中，这种 Q# 类型可以采用两个可能的值：`Zero` 和 `One`。</span><span class="sxs-lookup"><span data-stu-id="a33f8-113">Instead, we can measure it and store the outcome of the measurement in a `Result` variable, a Q# type that can take two possible values: `Zero` and `One`.</span></span> <span data-ttu-id="a33f8-114">此类构造可保证算法始终遵守量子物理学定律，并可在量子计算机或模拟器上正常运行。</span><span class="sxs-lookup"><span data-stu-id="a33f8-114">Constructs like this one guarantee that algorithms always respect the laws of quantum physics and can run correctly on quantum computers or simulators.</span></span>

<span data-ttu-id="a33f8-115">Q# 还包括经典逻辑功能（如条件和循环），这些功能又有些微不同，以确保遵循所有量子定律。</span><span class="sxs-lookup"><span data-stu-id="a33f8-115">Q# also includes classical logic features like conditionals and loops with some subtleties to make sure that all the quantum rules are being respected.</span></span> <span data-ttu-id="a33f8-116">例如，约束执行循环的方式，以确保不在可能只包含确定性经典子例程的函数中调用量子运算。</span><span class="sxs-lookup"><span data-stu-id="a33f8-116">For example, constraining the way loops are executed to ensure that quantum operations are not called within functions which may only contain deterministic classical subroutines.</span></span>

<span data-ttu-id="a33f8-117">Q# 程序通常与用 C# 或 Python 编写的主机程序配对使用，可以方便地整理经典代码和量子代码。</span><span class="sxs-lookup"><span data-stu-id="a33f8-117">Q# programs are often paired with a host program written in C# or Python, which can provide convenient organization of classical and quantum code.</span></span> <span data-ttu-id="a33f8-118">除了支持 C# 和 Python 之类的语言，QDK 还提供 IQ# Jupyter 内核，因此支持 Jupyter Notebook。</span><span class="sxs-lookup"><span data-stu-id="a33f8-118">In addition to supporting languages such as C# and Python, the QDK provides Jupyter Notebook support with the IQ# Jupyter kernel.</span></span>

## <a name="use-q-to-learn-quantum-computing"></a><span data-ttu-id="a33f8-119">使用 Q# 学习量子计算</span><span class="sxs-lookup"><span data-stu-id="a33f8-119">Use Q# to learn quantum computing</span></span>

<span data-ttu-id="a33f8-120">到目前为止，要学习量子计算，需要学习电路模型以理解量子门和度量有序序列形式的算法。</span><span class="sxs-lookup"><span data-stu-id="a33f8-120">Until now, to learn quantum computing you needed to learn the circuit model to understand the algorithms in the form of ordered sequences of quantum gates and measurements.</span></span> <span data-ttu-id="a33f8-121">使用 Q# 时，你也可以采用另一种方式：通过编写量子程序来学习量子计算。</span><span class="sxs-lookup"><span data-stu-id="a33f8-121">With Q# you can take another path: learn quantum computing by writing quantum programs.</span></span>

## <a name="use-q-to-design-quantum-algorithms"></a><span data-ttu-id="a33f8-122">使用 Q# 设计量子算法</span><span class="sxs-lookup"><span data-stu-id="a33f8-122">Use Q# to design quantum algorithms</span></span>

<span data-ttu-id="a33f8-123">Q# 提供了越来越多的库和用户定义类型，有助于实现各种工具并生成高级量子算法。</span><span class="sxs-lookup"><span data-stu-id="a33f8-123">Q# provides you with an increasing number of libraries and user-defined types that will help you to implement tools and build advanced quantum algorithms.</span></span> <span data-ttu-id="a33f8-124">例如，你需要纠缠双量子位 q1 和 q2。</span><span class="sxs-lookup"><span data-stu-id="a33f8-124">For example, you need to entangle two-qubits q1 and q2?</span></span> <span data-ttu-id="a33f8-125">可以使用已内置的运算 `PrepareEntangledState([q1], [q2])`，而不是单独应用必要的门来纠缠量子位。</span><span class="sxs-lookup"><span data-stu-id="a33f8-125">Instead of applying individually the necessary gates to get the qubits entangled you can use the already built-in operation `PrepareEntangledState([q1], [q2])`.</span></span>

## <a name="use-q-to-estimate-quantum-resources"></a><span data-ttu-id="a33f8-126">使用 Q# 估算量子资源</span><span class="sxs-lookup"><span data-stu-id="a33f8-126">Use Q# to estimate quantum resources</span></span>

<span data-ttu-id="a33f8-127">可以使用 Quantum 开发工具包 (QDK) 随附的全状态量子模拟器模拟 Q# 程序的执行。</span><span class="sxs-lookup"><span data-stu-id="a33f8-127">You can simulate the execution of your Q# program using the full state quantum simulator that is provided with the Quantum Development Kit (QDK).</span></span>  <span data-ttu-id="a33f8-128">QDK 还提供资源模拟器，让你了解那些因太大而无法在模拟器上运行的 Q# 程序的性能。</span><span class="sxs-lookup"><span data-stu-id="a33f8-128">The QDK also provides resource estimators that give you insights on the performance of Q# programs that are too large to be run on a simulator.</span></span>  <span data-ttu-id="a33f8-129">这对算法设计者来说具有很高的价值，因为他们可以调整其程序，让其使用较少的资源（运行较少数目的量子位来执行较少数目的操作）在早期的规模较小的量子硬件上运行。</span><span class="sxs-lookup"><span data-stu-id="a33f8-129">This is highly valuable for algorithm designers, because they can tune their programs to use fewer resources (e.g. fewer number of qubits running for fewer numbers of operations), to run on earlier smaller scale quantum hardware.</span></span>

## <a name="use-q-to-validate-hardware-performance"></a><span data-ttu-id="a33f8-130">使用 Q# 验证硬件性能</span><span class="sxs-lookup"><span data-stu-id="a33f8-130">Use Q# to validate hardware performance</span></span>

<span data-ttu-id="a33f8-131">Q# 的优点是，一个程序只需编写一次，然后即可在量子模拟器上进行调试性运行，以及在不同的量子计算机硬件上运行。</span><span class="sxs-lookup"><span data-stu-id="a33f8-131">The beauty of Q# is that a program can be written once and run on quantum simulators for debugging, and run on different quantum computer hardware.</span></span>  <span data-ttu-id="a33f8-132">随着量子计算机的发展和新的量子计算机的发布，可以运行以 Q# 编写的基准程序来验证硬件性能并对结果进行比较。</span><span class="sxs-lookup"><span data-stu-id="a33f8-132">Benchmark programs written in Q# can be run to validate hardware performance and compare results as quantum computers evolve and new quantum computers become available.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="a33f8-133">后续步骤</span><span class="sxs-lookup"><span data-stu-id="a33f8-133">Next steps</span></span>

* [<span data-ttu-id="a33f8-134">如何学习量子计算？</span><span class="sxs-lookup"><span data-stu-id="a33f8-134">How do I learn quantum computing?</span></span>](xref:microsoft.quantum.overview.learn)
* [<span data-ttu-id="a33f8-135">Microsoft Quantum 开发工具包入门</span><span class="sxs-lookup"><span data-stu-id="a33f8-135">Get started with the Microsoft Quantum Development Kit</span></span>](xref:microsoft.quantum.welcome)
