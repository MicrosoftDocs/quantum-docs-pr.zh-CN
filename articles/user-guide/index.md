---
title: Q# 用户指南
description: 用户指南的目的和内容概述
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4fae2949bdcab0c3735b40ef029d70bf7ea3fb9f
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869624"
---
# <a name="the-no-locq-user-guide"></a><span data-ttu-id="740b0-103">Q# 用户指南</span><span class="sxs-lookup"><span data-stu-id="740b0-103">The Q# User Guide</span></span>

<span data-ttu-id="740b0-104">欢迎查看 Q# 用户指南！</span><span class="sxs-lookup"><span data-stu-id="740b0-104">Welcome to the Q# User Guide!</span></span> 

<span data-ttu-id="740b0-105">本指南的各个主题详细介绍了 Q# 语言的核心概念，以及编写量子程序所需的各项信息。</span><span class="sxs-lookup"><span data-stu-id="740b0-105">In the different topics of this guide, we detail the core concepts of the Q# language and all the information you need to write quantum programs.</span></span>

## <a name="user-guide-contents"></a><span data-ttu-id="740b0-106">用户指南内容</span><span class="sxs-lookup"><span data-stu-id="740b0-106">User Guide Contents</span></span>

- <span data-ttu-id="740b0-107">[Q#基本信息](xref:microsoft.quantum.guide.basics)：简要概述了 Q# 编程语言的用途和功能。</span><span class="sxs-lookup"><span data-stu-id="740b0-107">[Q# Basics](xref:microsoft.quantum.guide.basics): An introductory overview of the purpose and functionality of the Q# programming language.</span></span> 

- <span data-ttu-id="740b0-108">[Q# 程序的运行方式](xref:microsoft.quantum.guide.host-programs)：描述了如何执行 Q# 程序，并简要介绍可用于调用该程序的各种方式：通过命令行、Q# Jupyter Notebooks，或者通过用 Python 或 .NET 语言编写的经典主机程序。</span><span class="sxs-lookup"><span data-stu-id="740b0-108">[Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs): describes how a Q# program is executed, and provides an overview of the various ways you can call the program: from the command line, in Q# Jupyter Notebooks, or from a classical host program written in Python or a .NET language.</span></span>

### <a name="no-locq-language"></a><span data-ttu-id="740b0-109">Q# 语言</span><span class="sxs-lookup"><span data-stu-id="740b0-109">Q# Language</span></span>

- <span data-ttu-id="740b0-110">[Q# 中的类型](xref:microsoft.quantum.guide.types)：列出了 Q# 类型模型，还描述了用于指定和使用这些类型的语法。</span><span class="sxs-lookup"><span data-stu-id="740b0-110">[Types in Q#](xref:microsoft.quantum.guide.types): Lays out the Q# type model and describes the syntax for specifying and working with types.</span></span>

- <span data-ttu-id="740b0-111">[类型表达式](xref:microsoft.quantum.guide.expressions)：详细说明了如何以 Q# 指定、引用、组合和操作各类型的值。</span><span class="sxs-lookup"><span data-stu-id="740b0-111">[Type Expressions](xref:microsoft.quantum.guide.expressions): Details how to specify, reference, combine, and operate on values of each type in Q#.</span></span> 

### <a name="using-no-locq"></a><span data-ttu-id="740b0-112">使用 Q#</span><span class="sxs-lookup"><span data-stu-id="740b0-112">Using Q#</span></span>

- <span data-ttu-id="740b0-113">[Q# 文件结构](xref:microsoft.quantum.guide.filestructure)：描述了 `*.qs` Q# 文件的结构和语法。</span><span class="sxs-lookup"><span data-stu-id="740b0-113">[Q# File Structure](xref:microsoft.quantum.guide.filestructure): Describes the structure and syntax of a `*.qs` Q# file.</span></span>

- <span data-ttu-id="740b0-114">[操作和函数](xref:microsoft.quantum.guide.operationsfunctions)：详细介绍了 Q# 语言的两种可调用类型，一种是“操作”，其中包含在量子位寄存器上进行的操作；另一种是“函数”，仅限于经典信息的处理。 </span><span class="sxs-lookup"><span data-stu-id="740b0-114">[Operations and Functions](xref:microsoft.quantum.guide.operationsfunctions): Details the two callable types of the Q# language: *operations*, which include action on qubit registers, and *functions*, which strictly work with classical information.</span></span> 
    <span data-ttu-id="740b0-115">你将在此处了解如何定义和调用它们，包括量子操作的伴随和受控版本。</span><span class="sxs-lookup"><span data-stu-id="740b0-115">Here you see how to define and call them, including the adjoint and controlled versions of quantum operations.</span></span>

- <span data-ttu-id="740b0-116">[变量](xref:microsoft.quantum.guide.variables)：介绍了变量在 Q# 程序中的角色及其有效使用方式。</span><span class="sxs-lookup"><span data-stu-id="740b0-116">[Variables](xref:microsoft.quantum.guide.variables): Describes the role of variables within Q# programs and how to leverage them effectively.</span></span> 
    <span data-ttu-id="740b0-117">例如，你能找到关于绑定范围的信息，还能了解到不可变和可变变量之间的区别，以及如何分配或重新分配它们。</span><span class="sxs-lookup"><span data-stu-id="740b0-117">For example, you can find information about binding scopes, as well as the difference between immutable and mutable variables and how to assign or re-assign them.</span></span>

- <span data-ttu-id="740b0-118">[使用量子位](xref:microsoft.quantum.guide.qubits)：描述用于处理单个量子位和量子位系统的 Q# 功能，具体而言，就是分配它们，对其执行操作，然后测量它们。</span><span class="sxs-lookup"><span data-stu-id="740b0-118">[Working with qubits](xref:microsoft.quantum.guide.qubits): Describes the features of Q# used to address individual qubits and systems of qubits, specifically, allocating them, performing operations on them, and measuring them.</span></span> 

- <span data-ttu-id="740b0-119">[控制流](xref:microsoft.quantum.guide.controlflow)：详细描述了 Q# 中提供的编程控制流模式，其中包含许多标准技术（如条件执行、for 循环、while 循环），以及量子特定的“重复直到成功”模式。</span><span class="sxs-lookup"><span data-stu-id="740b0-119">[Control Flow](xref:microsoft.quantum.guide.controlflow): Details the programming control flow patterns available in Q#, which includes many standard techniques (such as conditional execution, for loops, while loops) as well as the quantum-specific "Repeat-Until-Success" pattern.</span></span>

- <span data-ttu-id="740b0-120">[测试和调试](xref:microsoft.quantum.guide.testingdebugging)：详细介绍了一些用于确保代码正常运行的技术。</span><span class="sxs-lookup"><span data-stu-id="740b0-120">[Testing and debugging](xref:microsoft.quantum.guide.testingdebugging): Details some techniques for making sure your code is doing what it is supposed to do.</span></span> 
    <span data-ttu-id="740b0-121">由于量子信息通常不透明，因此调试量子程序可能需要专门的技术。</span><span class="sxs-lookup"><span data-stu-id="740b0-121">Due to the general opacity of quantum information, debugging a quantum program can require specialized techniques.</span></span> 
    <span data-ttu-id="740b0-122">幸运的是，Q# 支持程序员熟悉的许多经典调试技术，以及特定于量子的调试技术。</span><span class="sxs-lookup"><span data-stu-id="740b0-122">Fortunately, Q# supports many of the classical debugging techniques programmers are familiar with, as well as those that are quantum-specific.</span></span> <span data-ttu-id="740b0-123">其中包括以 Q# 创建和运行单元测试、在代码中嵌入对值和概率的断言，以及用于输出目标计算机状态的 `Dump` 函数。</span><span class="sxs-lookup"><span data-stu-id="740b0-123">These include creating and running unit tests in Q#, embedding *assertions* on values and probabilities in your code, and the `Dump` functions which output the states of target machines.</span></span> 
    <span data-ttu-id="740b0-124">后者可与全状态模拟器一起使用，通过规避某些量子限制（例如，[非克隆定理](xref:microsoft.quantum.concepts.pauli)）来调试计算的某些部分。</span><span class="sxs-lookup"><span data-stu-id="740b0-124">The latter can be used alongside our full-state simulator to debug certain parts of computations by skirting some quantum limitations, for example, the [no-cloning theorem](xref:microsoft.quantum.concepts.pauli).</span></span>

### <a name="quantum-simulators-and-resource-estimators"></a><span data-ttu-id="740b0-125">量子模拟器和资源估算器</span><span class="sxs-lookup"><span data-stu-id="740b0-125">Quantum Simulators and Resource Estimators</span></span>

- <span data-ttu-id="740b0-126">[量子模拟器和主机应用程序](xref:microsoft.quantum.machines)：概述了不同的可用模拟器，以及主机程序与目标计算机之间的常规执行模型。</span><span class="sxs-lookup"><span data-stu-id="740b0-126">[Quantum simulators and host applications](xref:microsoft.quantum.machines): An overview of the different simulators available, as well as the general execution model between host programs and target machines.</span></span>

- <span data-ttu-id="740b0-127">[全状态模拟器](xref:microsoft.quantum.machines.full-state-simulator)：模拟完整量子状态的目标计算机。</span><span class="sxs-lookup"><span data-stu-id="740b0-127">[Full state simulator](xref:microsoft.quantum.machines.full-state-simulator): The target machine which simulates the full quantum state.</span></span> <span data-ttu-id="740b0-128">适用于完全执行或调试规模更小的程序（不超过几十个量子位）</span><span class="sxs-lookup"><span data-stu-id="740b0-128">Useful for fully executing or debugging smaller-scale programs (less than a few dozen qubits)</span></span>

- <span data-ttu-id="740b0-129">[资源估算器](xref:microsoft.quantum.machines.resources-estimator)：估计在量子计算机上运行给定的 Q# 操作实例所需的资源。</span><span class="sxs-lookup"><span data-stu-id="740b0-129">[Resources estimator](xref:microsoft.quantum.machines.resources-estimator): Estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span>

- <span data-ttu-id="740b0-130">[跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)：在不实际模拟量子计算机状态的情况下执行量子程序，因此可执行使用数千个量子位的量子程序。</span><span class="sxs-lookup"><span data-stu-id="740b0-130">[Trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro): Executes a quantum program without actually simulating the state of a quantum computer, and therefore can execute quantum programs that use thousands of qubits.</span></span> <span data-ttu-id="740b0-131">适用于在量子程序中调试经典代码，以及预估所需的资源。</span><span class="sxs-lookup"><span data-stu-id="740b0-131">Useful for debugging classical code within a quantum program, as well as estimating resources required.</span></span>

- <span data-ttu-id="740b0-132">[Toffoli 模拟器](xref:microsoft.quantum.machines.toffoli-simulator)：一种特殊用途的量子模拟器，可处理数百万个量子位，但仅适用于具有一组有限的量子操作（X、CNOT 和多受控 X）的程序。</span><span class="sxs-lookup"><span data-stu-id="740b0-132">[Toffoli simulator](xref:microsoft.quantum.machines.toffoli-simulator): A special-purpose quantum simulator that can be used with millions of qubits, but only for programs with a restricted set of quantum operations - X, CNOT, and multi-controlled X.</span></span>

### <a name="quick-reference-pages"></a><span data-ttu-id="740b0-133">快速参考页面</span><span class="sxs-lookup"><span data-stu-id="740b0-133">Quick Reference Pages</span></span>

- <span data-ttu-id="740b0-134">[IQ# Magic 命令](xref:microsoft.quantum.guide.quickref.iqsharp)：Q# Jupyter 笔记本中 IQ# Magic 命令的快速参考页面。</span><span class="sxs-lookup"><span data-stu-id="740b0-134">[IQ# Magic Commands](xref:microsoft.quantum.guide.quickref.iqsharp): Quick reference page for IQ# magic commands within Q# Jupyter Notebooks.</span></span>
