---
title: 量子开发技术
description: 了解 Q# 程序开发的基础知识，使用操作、函数、变量和量子位，并创建一个简单的量子程序。
keywords: 未咨询 SEO 专家的情况下，请不要添加或编辑关键字。
author: QuantumWriter
ms.author: MSFT-alias-person-or-DL
ms.date: 9/20/2019
ms.topic: article-type-from-white-list
uid: microsoft.quantum.techniques.intro
ms.openlocfilehash: e5b7fbde18afbc0333d89f70c5e4596848e30f4f
ms.sourcegitcommit: 9d1c045cf1a2c3e19030cb38dbc7496dbd24ab58
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2020
ms.locfileid: "77907709"
---
# <a name="quantum-development-techniques"></a><span data-ttu-id="103ba-104">量子开发技术</span><span class="sxs-lookup"><span data-stu-id="103ba-104">Quantum Development Techniques</span></span>

<span data-ttu-id="103ba-105">文档的此部分详细介绍了用于在 Q# 中创建量子程序的核心概念，以及如何通过经典应用程序与这些程序交互。</span><span class="sxs-lookup"><span data-stu-id="103ba-105">This section of our documentation details the core concepts used to create quantum programs in Q#, and to interact with those programs from classical applications.</span></span>
<span data-ttu-id="103ba-106">我们假设你对量子计算概念有一些  了解，如[量子计算概念](xref:microsoft.quantum.concepts.intro)中所述，但你不需要是量子计算方面的专家即可充分掌握这些部分的内容。</span><span class="sxs-lookup"><span data-stu-id="103ba-106">We assume *some* knowledge of quantum computing concepts, like those described in [Quantum computing concepts](xref:microsoft.quantum.concepts.intro), but you need not be an expert in quantum computing to get a lot from these sections.</span></span>

<span data-ttu-id="103ba-107">其内容如下所示。</span><span class="sxs-lookup"><span data-stu-id="103ba-107">Their contents are as follows.</span></span>

- <span data-ttu-id="103ba-108">[Q# 程序概述](xref:microsoft.quantum.techniques.file-structure)概述了 Q# 编程语言的用途和功能。</span><span class="sxs-lookup"><span data-stu-id="103ba-108">[Q# program overview](xref:microsoft.quantum.techniques.file-structure) provides an overview of the purpose and functionality of the Q# programming language.</span></span> 
    <span data-ttu-id="103ba-109">具体说来，它阐明了 Q#  不是一种仅用于模拟量子机制（虽然我们的完整状态模拟器理所当然地会提供此功能）的语言，</span><span class="sxs-lookup"><span data-stu-id="103ba-109">In particular, it clarifies how Q# is *not* a language for merely simulating quantum mechanics---though that functionality is of course provided by our full state simulator.</span></span> 
    <span data-ttu-id="103ba-110">而是一种针对未来设计的语言，其程序描述经典控制计算机如何  与量子位交互。</span><span class="sxs-lookup"><span data-stu-id="103ba-110">Rather, Q# was designed with an eye on the future, and its programs describe how a classical control computer *interacts* with qubits.</span></span> 

- <span data-ttu-id="103ba-111">[操作和函数](xref:microsoft.quantum.techniques.opsandfunctions)详述了 Q# 语言的两种可调用类型：一种是*操作*，其中包括在量子位和量子系统上进行的操作；另一种是*函数*，仅限于经典信息的处理。</span><span class="sxs-lookup"><span data-stu-id="103ba-111">[Operations and functions](xref:microsoft.quantum.techniques.opsandfunctions) details the two callable types of the Q# language: *operations*, which include action on qubits and quantum systems; and *functions*, which strictly work with classical information.</span></span> 
    <span data-ttu-id="103ba-112">如果经典信息和量子信息不能配合使用，则量子计算也就无从谈起。</span><span class="sxs-lookup"><span data-stu-id="103ba-112">Without both classical and quantum information working in tandem, quantum computing would remain out of reach.</span></span> 
    <span data-ttu-id="103ba-113">此部分介绍如何在 Q# 程序的控制流中定义和使用这两种可调用类型。</span><span class="sxs-lookup"><span data-stu-id="103ba-113">This section describes how to define and use these callables within the control flow of a Q# program.</span></span>

- <span data-ttu-id="103ba-114">[局部变量](xref:microsoft.quantum.techniques.local-variables)介绍变量在 Q# 程序中的角色以及如何有效地利用它们。</span><span class="sxs-lookup"><span data-stu-id="103ba-114">[Local variables](xref:microsoft.quantum.techniques.local-variables) describes the role of variables within Q# programs and how to leverage them effectively.</span></span> 
    <span data-ttu-id="103ba-115">具体说来，它介绍不可变/可变变量之间的差异以及如何分配/重新分配它们。</span><span class="sxs-lookup"><span data-stu-id="103ba-115">In particular, you will learn the difference between immutable/mutable variables and how to assign/re-assign them.</span></span>

- <span data-ttu-id="103ba-116">[使用量子位](xref:microsoft.quantum.techniques.qubits)介绍可用于处理单个量子位和量子位系统的 Q# 功能。</span><span class="sxs-lookup"><span data-stu-id="103ba-116">[Working with qubits](xref:microsoft.quantum.techniques.qubits) describes the features of Q# that you can use to address individual qubits and systems of qubits.</span></span> 
    <span data-ttu-id="103ba-117">具体说来，这需要进行分配，在其上执行操作，并最终进行度量。</span><span class="sxs-lookup"><span data-stu-id="103ba-117">Specifically, that entails their allocation, performing operations on them, and ultimately their measurement.</span></span> 
    <span data-ttu-id="103ba-118">另外还介绍一些有用的控制流技术。</span><span class="sxs-lookup"><span data-stu-id="103ba-118">Additionally, you will learn some useful control flow techniques.</span></span>

- <span data-ttu-id="103ba-119">在[汇总](xref:microsoft.quantum.techniques.puttingittogether)中，我们将利用上述部分的技术创建一个执行**量子隐形传送**的程序：使用两个经典位将一个量子位的完整状态“传送”到另一个量子位。</span><span class="sxs-lookup"><span data-stu-id="103ba-119">In [Putting it all together](xref:microsoft.quantum.techniques.puttingittogether), you will leverage the techniques from the sections above to create a program which performs **quantum teleportation**: using two classical bits to "teleport" the full state of one qubit onto another.</span></span>

- <span data-ttu-id="103ba-120">[深入探索](xref:microsoft.quantum.techniques.going-further)引入了高级技术，这些技术在你转向更复杂的量子编程时很有用。</span><span class="sxs-lookup"><span data-stu-id="103ba-120">[Going further](xref:microsoft.quantum.techniques.going-further) introduces advanced techniques that can prove helpful as you move toward more complex quantum programming.</span></span> 
    <span data-ttu-id="103ba-121">具体说来，我们将讨论如何使用 Q# 中的类型参数化  操作和函数来实现高阶控制流：不需了解其输入/输出的具体类型，并且可以借用  量子位。</span><span class="sxs-lookup"><span data-stu-id="103ba-121">In particular, we discuss the use of *type-parameterized* operations and functions in Q#, which enable higher-order control flow by remaining agnostic to the specific types of their input/output, as well as *borrowing* qubits.</span></span> 
    <span data-ttu-id="103ba-122">后者不同于基本的量子位分配，因为 Q# 操作可以使用“脏”量子位（不一定初始化为已知状态的量子位）来协助计算。</span><span class="sxs-lookup"><span data-stu-id="103ba-122">The latter differs from basic qubit allocation in that a Q# operation may use "dirty" qubits---qubits not necessarily initialized to a known state---to assist computations.</span></span>

- <span data-ttu-id="103ba-123">[测试和调试](xref:microsoft.quantum.techniques.testing-and-debugging)详述了一些用于确保代码正常运行的技术。</span><span class="sxs-lookup"><span data-stu-id="103ba-123">[Testing and debugging](xref:microsoft.quantum.techniques.testing-and-debugging) details some techniques for making sure your code is doing what it is supposed to do.</span></span> 
    <span data-ttu-id="103ba-124">由于量子信息通常不透明，因此调试量子程序可能需要专门的技术。</span><span class="sxs-lookup"><span data-stu-id="103ba-124">Due to the general opacity of quantum information, debugging a quantum program can require specialized techniques.</span></span> 
    <span data-ttu-id="103ba-125">幸运的是，Q# 支持程序员习惯使用的许多经典调试技术，以及特定于量子的调试技术。</span><span class="sxs-lookup"><span data-stu-id="103ba-125">Fortunately, Q# supports many of the classical debugging techniques programmers are used to, as well as those that are quantum-specific.</span></span> <span data-ttu-id="103ba-126">其中包括在 Q# 中创建/运行单元测试、在代码中嵌入对值和概率的断言  ，以及用于输出目标计算机状态的 `Dump` 函数。</span><span class="sxs-lookup"><span data-stu-id="103ba-126">These include creating/running unit tests in Q#, embedding *assertions* on values and probabilities in your code, and the `Dump` functions which output the state of target machine.</span></span> 
    <span data-ttu-id="103ba-127">后者可与完整状态模拟器一起使用，通过规避某些量子限制（例如，非克隆定理）来调试计算的某些部分。</span><span class="sxs-lookup"><span data-stu-id="103ba-127">The latter can be used alongside our full state simulator to debug certain parts of computations by skirting some quantum limitations (e.g. the no-cloning theorem).</span></span>


![量子](~/media/mobius_strip_preview.png)
