---
title: Q# 用户指南
description: 用户指南的目的和内容概述
author: gillenhaalb
ms.author: a-gibec
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide
no-loc:
- Q#
- $$v
ms.openlocfilehash: 979e468cc743bd9125eaba0b71f794977c914447
ms.sourcegitcommit: b930bb59a1ba8f41d2edc9ed98197109aa8c7f1b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231751"
---
# <a name="the-no-locq-user-guide"></a><span data-ttu-id="b7f77-103">Q# 用户指南</span><span class="sxs-lookup"><span data-stu-id="b7f77-103">The Q# User Guide</span></span>

<span data-ttu-id="b7f77-104">欢迎查看 Q# 用户指南！</span><span class="sxs-lookup"><span data-stu-id="b7f77-104">Welcome to the Q# User Guide!</span></span> 

<span data-ttu-id="b7f77-105">在本指南的不同主题中，我们介绍了使用 Q# 开发量子程序的一些基础知识。</span><span class="sxs-lookup"><span data-stu-id="b7f77-105">In the different topics of this guide, we introduce some of the basics for developing quantum programs using Q#.</span></span>

<span data-ttu-id="b7f77-106">有关 Q# 量子程序语言的完整规范和文档，请参阅 [Q# 语言指南](xref:microsoft.quantum.qsharp.index)。</span><span class="sxs-lookup"><span data-stu-id="b7f77-106">We refer to the [Q# language guide](xref:microsoft.quantum.qsharp.index) for a full specification and documentation of the Q# quantum programming language.</span></span> 

## <a name="user-guide-contents"></a><span data-ttu-id="b7f77-107">用户指南内容</span><span class="sxs-lookup"><span data-stu-id="b7f77-107">User Guide Contents</span></span>

- <span data-ttu-id="b7f77-108">[Q# 程序](xref:microsoft.quantum.guide.programs)：用 Q# 编写的量子程序的快速简介。</span><span class="sxs-lookup"><span data-stu-id="b7f77-108">[Q# programs](xref:microsoft.quantum.guide.programs): An quick introduction to quantum programs in Q#.</span></span> 

- <span data-ttu-id="b7f77-109">[Q# 程序的运行方式](xref:microsoft.quantum.guide.host-programs)：描述 Q# 程序的运行方式，并简要介绍可用于调用该程序的各种方式：通过命令行、Q# Jupyter Notebook，或者通过用 Python 或 .NET 语言编写的经典主机程序。</span><span class="sxs-lookup"><span data-stu-id="b7f77-109">[Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs): describes how a Q# program is run, and provides an overview of the various ways you can call the program: from the command line, in Q# Jupyter Notebooks, or from a classical host program written in Python or a .NET language.</span></span>

- <span data-ttu-id="b7f77-110">[测试和调试](xref:microsoft.quantum.guide.testingdebugging)：详细介绍了一些用于确保代码正常运行的技术。</span><span class="sxs-lookup"><span data-stu-id="b7f77-110">[Testing and debugging](xref:microsoft.quantum.guide.testingdebugging): Details some techniques for making sure your code is doing what it is supposed to do.</span></span> 
    <span data-ttu-id="b7f77-111">由于量子信息通常不透明，因此调试量子程序可能需要专门的技术。</span><span class="sxs-lookup"><span data-stu-id="b7f77-111">Due to the general opacity of quantum information, debugging a quantum program can require specialized techniques.</span></span> 
    <span data-ttu-id="b7f77-112">幸运的是，Q# 支持程序员熟悉的许多经典调试技术，以及特定于量子的调试技术。</span><span class="sxs-lookup"><span data-stu-id="b7f77-112">Fortunately, Q# supports many of the classical debugging techniques programmers are familiar with, as well as those that are quantum-specific.</span></span> <span data-ttu-id="b7f77-113">其中包括以 Q# 创建和运行单元测试、在代码中嵌入对值和概率的断言，以及用于输出目标计算机状态的 `Dump` 函数。</span><span class="sxs-lookup"><span data-stu-id="b7f77-113">These include creating and running unit tests in Q#, embedding *assertions* on values and probabilities in your code, and the `Dump` functions which output the states of target machines.</span></span> 
    <span data-ttu-id="b7f77-114">后者可与全状态模拟器一起使用，通过规避某些量子限制（例如，[非克隆定理](xref:microsoft.quantum.concepts.pauli)）来调试计算的某些部分。</span><span class="sxs-lookup"><span data-stu-id="b7f77-114">The latter can be used alongside our full-state simulator to debug certain parts of computations by skirting some quantum limitations, for example, the [no-cloning theorem](xref:microsoft.quantum.concepts.pauli).</span></span>

### <a name="quantum-simulators-and-resource-estimators"></a><span data-ttu-id="b7f77-115">量子模拟器和资源估算器</span><span class="sxs-lookup"><span data-stu-id="b7f77-115">Quantum Simulators and Resource Estimators</span></span>

- <span data-ttu-id="b7f77-116">[量子模拟器和主机应用程序](xref:microsoft.quantum.machines)：概述了不同的可用模拟器，简要介绍了主机程序和目标计算机如何搭配使用来运行 Q# 程序。</span><span class="sxs-lookup"><span data-stu-id="b7f77-116">[Quantum simulators and host applications](xref:microsoft.quantum.machines): An overview of the different simulators available, as well of how host programs and target machines work together to run Q# programs.</span></span>

- <span data-ttu-id="b7f77-117">[全状态模拟器](xref:microsoft.quantum.machines.full-state-simulator)：模拟完整量子状态的目标计算机。</span><span class="sxs-lookup"><span data-stu-id="b7f77-117">[Full state simulator](xref:microsoft.quantum.machines.full-state-simulator): The target machine which simulates the full quantum state.</span></span> <span data-ttu-id="b7f77-118">适用于完全运行或调试规模更小的程序（不超过几十个量子位）</span><span class="sxs-lookup"><span data-stu-id="b7f77-118">Useful for fully running or debugging smaller-scale programs (less than a few dozen qubits)</span></span>

- <span data-ttu-id="b7f77-119">[资源估算器](xref:microsoft.quantum.machines.resources-estimator)：估计在量子计算机上运行给定的 Q# 操作实例所需的资源。</span><span class="sxs-lookup"><span data-stu-id="b7f77-119">[Resources estimator](xref:microsoft.quantum.machines.resources-estimator): Estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span>

- <span data-ttu-id="b7f77-120">[跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)：在不实际模拟量子计算机状态的情况下运行量子程序，因此可运行使用数千个量子位的量子程序。</span><span class="sxs-lookup"><span data-stu-id="b7f77-120">[Trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro): Runs a quantum program without actually simulating the state of a quantum computer, and therefore can run quantum programs that use thousands of qubits.</span></span> <span data-ttu-id="b7f77-121">适用于在量子程序中调试经典代码，以及预估所需的资源。</span><span class="sxs-lookup"><span data-stu-id="b7f77-121">Useful for debugging classical code within a quantum program, as well as estimating resources required.</span></span>

- <span data-ttu-id="b7f77-122">[Toffoli 模拟器](xref:microsoft.quantum.machines.toffoli-simulator)：一种特殊用途的量子模拟器，可处理数百万个量子位，但仅适用于具有一组有限的量子操作（X、CNOT 和多受控 X）的程序。</span><span class="sxs-lookup"><span data-stu-id="b7f77-122">[Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator): A special-purpose quantum simulator that can be used with millions of qubits, but only for programs with a restricted set of quantum operations - X, CNOT, and multi-controlled X.</span></span>

### <a name="quick-reference-pages"></a><span data-ttu-id="b7f77-123">快速参考页面</span><span class="sxs-lookup"><span data-stu-id="b7f77-123">Quick Reference Pages</span></span>

- <span data-ttu-id="b7f77-124">[IQ# Magic 命令](xref:microsoft.quantum.guide.quickref.iqsharp)：Q# Jupyter 笔记本中 IQ# Magic 命令的快速参考页面。</span><span class="sxs-lookup"><span data-stu-id="b7f77-124">[IQ# Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp): Quick reference page for IQ# magic commands within Q# Jupyter Notebooks.</span></span>
