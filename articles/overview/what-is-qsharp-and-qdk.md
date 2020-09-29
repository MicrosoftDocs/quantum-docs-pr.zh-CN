---
title: 什么是 Q# 编程语言和 QDK？
description: 了解 Microsoft Quantum 开发工具包、Q# 编程语言以及量子程序的创建方式。
author: bradben
ms.author: v-benbra
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.q-sharp
no-loc:
- Q#
- $$v
ms.openlocfilehash: 21adfcc1c5321d87665adb39a3c838bbda0b8861
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2020
ms.locfileid: "90834561"
---
# <a name="what-are-the-no-locq-programming-language-and-qdk"></a><span data-ttu-id="411c4-103">什么是 Q# 编程语言和 QDK？</span><span class="sxs-lookup"><span data-stu-id="411c4-103">What are the Q# programming language and QDK?</span></span>

<span data-ttu-id="411c4-104">Q# 是用于开发和运行量子算法的 Microsoft 开放源代码编程语言。</span><span class="sxs-lookup"><span data-stu-id="411c4-104">Q# is Microsoft’s open-source programming language for developing and running quantum algorithms.</span></span> <span data-ttu-id="411c4-105">它是 Quantum 开发工具包 (QDK) 的一部分，其中包括 [Q#Q# 库](xref:microsoft.quantum.libraries)、[量子模拟器](xref:microsoft.quantum.machines)、[其他编程环境的扩展](xref:microsoft.quantum.install)和 [API 文档](xref:microsoft.quantum.apiref-intro)。</span><span class="sxs-lookup"><span data-stu-id="411c4-105">It’s part of the Quantum Development Kit (QDK), which includes [Q# libraries](xref:microsoft.quantum.libraries), [quantum simulators](xref:microsoft.quantum.machines), [extensions for other programming environments](xref:microsoft.quantum.install), and [API documentation](xref:microsoft.quantum.apiref-intro).</span></span> <span data-ttu-id="411c4-106">除了标准 Q# 库，QDK 还包括化学库、机器学习库和数字库。</span><span class="sxs-lookup"><span data-stu-id="411c4-106">In addition to the Standard Q# library, the QDK includes Chemistry, Machine Learning, and Numeric libraries.</span></span>

<span data-ttu-id="411c4-107">作为一种编程语言，Q# 从 Python、C# 和 F# 中汲取了熟悉的元素，并支持使用循环、if/then 语句和常用数据类型编写程序的基本过程模型。</span><span class="sxs-lookup"><span data-stu-id="411c4-107">As a programming language, Q# draws familiar elements from Python, C#, and F# and supports a basic procedural model for writing programs with loops, if/then statements, and common data types.</span></span> <span data-ttu-id="411c4-108">它还介绍了新的特定于量子的数据结构和操作。</span><span class="sxs-lookup"><span data-stu-id="411c4-108">It also introduces new quantum-specific data structures and operations.</span></span>

## <a name="what-can-i-do-with-the-qdk"></a><span data-ttu-id="411c4-109">QDK 有什么作用？</span><span class="sxs-lookup"><span data-stu-id="411c4-109">What can I do with the QDK?</span></span>

<span data-ttu-id="411c4-110">QDK 是功能完善的 Q# 开发工具包，可与常用工具和语言结合使用来开发可在各种环境中运行的量子应用程序。</span><span class="sxs-lookup"><span data-stu-id="411c4-110">The QDK is a full-featured development kit for Q# that you can use with common tools and languages to develop quantum applications that you can run in various environments.</span></span> <span data-ttu-id="411c4-111">Q# 程序可通过 Jupyter 笔记本以控制台应用程序的形式运行，也可使用 Python 或 .NET 主机程序运行。</span><span class="sxs-lookup"><span data-stu-id="411c4-111">Q# programs can run as a console application, through Jupyter Notebooks, or use a Python or .NET host program.</span></span>

### <a name="develop-in-common-tools-and-environments"></a><span data-ttu-id="411c4-112">在常用工具和环境中进行开发</span><span class="sxs-lookup"><span data-stu-id="411c4-112">Develop in common tools and environments</span></span>

<span data-ttu-id="411c4-113">将量子开发与 [Visual Studio、Visual Studio Code](xref:microsoft.quantum.install.standalone) 和 [Jupyter Notebook](xref:microsoft.quantum.install.jupyter) 集成。</span><span class="sxs-lookup"><span data-stu-id="411c4-113">Integrate your quantum development with [Visual Studio, Visual Studio Code](xref:microsoft.quantum.install.standalone), and [Jupyter Notebooks](xref:microsoft.quantum.install.jupyter).</span></span> <span data-ttu-id="411c4-114">使用内置的 API 将程序与 [Python](xref:microsoft.quantum.install.python) 和 [.NET](xref:microsoft.quantum.install.cs) 主机语言配对。</span><span class="sxs-lookup"><span data-stu-id="411c4-114">Use the built-in APIs for pairing your programs with [Python](xref:microsoft.quantum.install.python) and [.NET](xref:microsoft.quantum.install.cs) host languages.</span></span>

### <a name="try-quantum-operations-and-domain-specific-libraries"></a><span data-ttu-id="411c4-115">尝试使用量子操作和特定领域的库</span><span class="sxs-lookup"><span data-stu-id="411c4-115">Try quantum operations and domain-specific libraries</span></span>

<span data-ttu-id="411c4-116">编写和测试量子算法，以探索量子叠加、纠缠和其他量子操作。</span><span class="sxs-lookup"><span data-stu-id="411c4-116">Write and test quantum algorithms to explore superposition, entanglement, and other quantum operations.</span></span> <span data-ttu-id="411c4-117">通过 Q# 库，可运行复杂的量子操作，而不必设计低级别的操作序列。</span><span class="sxs-lookup"><span data-stu-id="411c4-117">The Q# libraries enable you to run complex quantum operations without having to design low-level operation sequences.</span></span>

### <a name="run-programs-in-simulators"></a><span data-ttu-id="411c4-118">在模拟器中运行程序</span><span class="sxs-lookup"><span data-stu-id="411c4-118">Run programs in simulators</span></span>

<span data-ttu-id="411c4-119">在完整状态的量子模拟器、有限范围的 Toffoli 模拟器上运行量子程序，或在各种资源估算器中测试 Q# 代码。</span><span class="sxs-lookup"><span data-stu-id="411c4-119">Run your quantum programs on a full-state quantum simulator, a limited-scope Toffoli simulator, or test your Q# code in different resource estimators.</span></span> 

## <a name="where-can-i-learn-more"></a><span data-ttu-id="411c4-120">可以从何处了解详细信息？</span><span class="sxs-lookup"><span data-stu-id="411c4-120">Where can I learn more?</span></span>

|||
| ---- | ---- |
| <span data-ttu-id="411c4-121">**我对量子计算不熟悉**</span><span class="sxs-lookup"><span data-stu-id="411c4-121">**I'm new to quantum computing**</span></span> | <span data-ttu-id="411c4-122">回顾[关键概念](xref:microsoft.quantum.overview.understanding)中的量子物理学和量子计算的一些基础知识。</span><span class="sxs-lookup"><span data-stu-id="411c4-122">Review some basics of quantum physics and quantum computing in [Key Concepts](xref:microsoft.quantum.overview.understanding).</span></span>|
| <span data-ttu-id="411c4-123">**我想更深入地了解 Q# 语言**</span><span class="sxs-lookup"><span data-stu-id="411c4-123">**I want to dive deeper into the Q# language**</span></span> | <span data-ttu-id="411c4-124">请在 [Q# 用户指南](xref:microsoft.quantum.guide)中了解类型、表达式、变量和量子程序结构。</span><span class="sxs-lookup"><span data-stu-id="411c4-124">Explore types, expressions, variables, and quantum program structure in the [Q# User Guide](xref:microsoft.quantum.guide).</span></span>|
| <span data-ttu-id="411c4-125">**我只想开始编写量子程序**</span><span class="sxs-lookup"><span data-stu-id="411c4-125">**I just want to start writing quantum programs**</span></span> | <span data-ttu-id="411c4-126">请参阅[快速入门](xref:microsoft.quantum.install)了解如何设置 Q# 环境并开始编写量子程序。</span><span class="sxs-lookup"><span data-stu-id="411c4-126">Set up your Q# environment and start writing quantum programs in [QuickStarts](xref:microsoft.quantum.install).</span></span>|

## <a name="how-does-no-locq-work"></a><span data-ttu-id="411c4-127">Q# 是如何工作的？</span><span class="sxs-lookup"><span data-stu-id="411c4-127">How does Q# work?</span></span>

<span data-ttu-id="411c4-128">Q# 程序可编译为独立的应用程序，也可由使用 Python 或 .NET 语言编写的主机程序调用。</span><span class="sxs-lookup"><span data-stu-id="411c4-128">A Q# program can compile into a standalone application or be called by a host program that is written either in Python or a .NET language.</span></span>

<span data-ttu-id="411c4-129">编译并运行该程序时，它将创建量子模拟器的实例，并向其传递 Q# 代码。</span><span class="sxs-lookup"><span data-stu-id="411c4-129">When you compile and run the program, it creates an instance of the quantum simulator and passes the Q# code to it.</span></span> <span data-ttu-id="411c4-130">该模拟器使用 Q# 代码创建量子比特（量子粒子的模拟）并应用转换来修改其状态。</span><span class="sxs-lookup"><span data-stu-id="411c4-130">The simulator uses the Q# code to create qubits (simulations of quantum particles) and apply transformations to modify their state.</span></span> <span data-ttu-id="411c4-131">然后将模拟器中的量子操作结果返回到程序。</span><span class="sxs-lookup"><span data-stu-id="411c4-131">The results of the quantum operations in the simulator are then returned to the program.</span></span>  

<span data-ttu-id="411c4-132">在模拟器中隔离 Q# 代码可确保算法遵循量子物理学定律，还确保这些算法可在量子计算机上正确运行。</span><span class="sxs-lookup"><span data-stu-id="411c4-132">Isolating the Q# code in the simulator ensures that the algorithms follow the laws of quantum physics and can run correctly on quantum computers.</span></span>

![Qsharp 代码流](~/media/qsharp-code-flow.png)

## <a name="how-do-i-use-the-qdk"></a><span data-ttu-id="411c4-134">如何使用 QDK？</span><span class="sxs-lookup"><span data-stu-id="411c4-134">How do I use the QDK?</span></span>

<span data-ttu-id="411c4-135">编写和运行 Q# 程序所需的一切（包括 Q# 编译器、Q#库和量子模拟器）都可以在本地计算机上安装和运行。</span><span class="sxs-lookup"><span data-stu-id="411c4-135">Everything you need to write and run Q# programs, including the Q# compiler, the Q# libraries, and the quantum simulators, can be installed and run from your local computer.</span></span> <span data-ttu-id="411c4-136">最终，你将能够在实际的量子计算机上远程运行 Q# 程序，但在此之前，可借助 QDK 随附的量子模拟器提供准确而可靠的结果。</span><span class="sxs-lookup"><span data-stu-id="411c4-136">Eventually you will be able to run your Q# programs remotely on an actual quantum computer, but until then the quantum simulators provided with the QDK provide accurate and reliable results.</span></span>

- <span data-ttu-id="411c4-137">要实现入门，最快的方式是开发 [Q# 应用程序](xref:microsoft.quantum.install.standalone)。</span><span class="sxs-lookup"><span data-stu-id="411c4-137">Developing [Q# applications](xref:microsoft.quantum.install.standalone) is the quickest way to get started.</span></span>

- <span data-ttu-id="411c4-138">[运行使用 IQ# 的独立 Jupyter Notebooks](xref:microsoft.quantum.install.jupyter)，这是用于编译、模拟和可视化 Q# 程序的 Jupyter 扩展。</span><span class="sxs-lookup"><span data-stu-id="411c4-138">Run standalone [Jupyter Notebooks with IQ#](xref:microsoft.quantum.install.jupyter), a Jupyter extension for compiling, simulating, and visualizing Q# programs.</span></span>

- <span data-ttu-id="411c4-139">如果你熟悉 [Python](xref:microsoft.quantum.install.python)，则可以将其用作主机编程平台来入门。</span><span class="sxs-lookup"><span data-stu-id="411c4-139">If you are familiar with [Python](xref:microsoft.quantum.install.python), you can use it as a host programming platform to get started.</span></span> <span data-ttu-id="411c4-140">Python 不仅深受开发人员喜爱，而且也深受科学家、研究人员和教师的喜爱。</span><span class="sxs-lookup"><span data-stu-id="411c4-140">Python enjoys widespread use not only among developers, but also scientists, researchers and teachers.</span></span>

- <span data-ttu-id="411c4-141">如果你可以熟练使用 [C#、F# 或 VB.NET](xref:microsoft.quantum.install.cs)且熟悉 Visual Studio 开发环境，则只需在 Visual Studio 中添加一些扩展，即可为 Q# 做好准备。</span><span class="sxs-lookup"><span data-stu-id="411c4-141">If you already have experience with [C#, F#, or VB.NET](xref:microsoft.quantum.install.cs) and are familiar with the Visual Studio development environment, there are just a few extensions you need to add to Visual Studio to prepare it for Q#.</span></span>  

## <a name="summary"></a><span data-ttu-id="411c4-142">总结</span><span class="sxs-lookup"><span data-stu-id="411c4-142">Summary</span></span>

<span data-ttu-id="411c4-143">Q# 是用于开发量子程序的开放源代码编程语言。</span><span class="sxs-lookup"><span data-stu-id="411c4-143">Q# is an open-source programming language for developing quantum programs.</span></span> <span data-ttu-id="411c4-144">它具有可用于创建复杂量子操作的库，以及可精确运行和测试程序的量子模拟器。</span><span class="sxs-lookup"><span data-stu-id="411c4-144">It has libraries that let you create complex quantum operations, and quantum simulators to accurately run and test your programs.</span></span> <span data-ttu-id="411c4-145">Q# 程序可以作为独立应用运行，也可以通过 Python 或 .NET 主机程序进行调用，并且可以从本地计算机进行编写、运行和测试。</span><span class="sxs-lookup"><span data-stu-id="411c4-145">Q# programs can run as standalone apps or be called from a Python or .NET host program, and can be written, run, and tested from your local computer.</span></span>

## <a name="next-steps"></a><span data-ttu-id="411c4-146">后续步骤</span><span class="sxs-lookup"><span data-stu-id="411c4-146">Next Steps</span></span>

[<span data-ttu-id="411c4-147">用于量子计算的线性代数</span><span class="sxs-lookup"><span data-stu-id="411c4-147">Linear algebra for quantum computing</span></span>](xref:microsoft.quantum.overview.algebra)
