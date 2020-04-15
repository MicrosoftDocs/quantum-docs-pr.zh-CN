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
# <a name="quantum-development-techniques"></a>量子开发技术

文档的此部分详细介绍了用于在 Q# 中创建量子程序的核心概念，以及如何通过经典应用程序与这些程序交互。
我们假设你对量子计算概念有一些  了解，如[量子计算概念](xref:microsoft.quantum.concepts.intro)中所述，但你不需要是量子计算方面的专家即可充分掌握这些部分的内容。

其内容如下所示。

- [Q# 程序概述](xref:microsoft.quantum.techniques.file-structure)概述了 Q# 编程语言的用途和功能。 
    具体说来，它阐明了 Q#  不是一种仅用于模拟量子机制（虽然我们的完整状态模拟器理所当然地会提供此功能）的语言， 
    而是一种针对未来设计的语言，其程序描述经典控制计算机如何  与量子位交互。 

- [操作和函数](xref:microsoft.quantum.techniques.opsandfunctions)详述了 Q# 语言的两种可调用类型：一种是*操作*，其中包括在量子位和量子系统上进行的操作；另一种是*函数*，仅限于经典信息的处理。 
    如果经典信息和量子信息不能配合使用，则量子计算也就无从谈起。 
    此部分介绍如何在 Q# 程序的控制流中定义和使用这两种可调用类型。

- [局部变量](xref:microsoft.quantum.techniques.local-variables)介绍变量在 Q# 程序中的角色以及如何有效地利用它们。 
    具体说来，它介绍不可变/可变变量之间的差异以及如何分配/重新分配它们。

- [使用量子位](xref:microsoft.quantum.techniques.qubits)介绍可用于处理单个量子位和量子位系统的 Q# 功能。 
    具体说来，这需要进行分配，在其上执行操作，并最终进行度量。 
    另外还介绍一些有用的控制流技术。

- 在[汇总](xref:microsoft.quantum.techniques.puttingittogether)中，我们将利用上述部分的技术创建一个执行**量子隐形传送**的程序：使用两个经典位将一个量子位的完整状态“传送”到另一个量子位。

- [深入探索](xref:microsoft.quantum.techniques.going-further)引入了高级技术，这些技术在你转向更复杂的量子编程时很有用。 
    具体说来，我们将讨论如何使用 Q# 中的类型参数化  操作和函数来实现高阶控制流：不需了解其输入/输出的具体类型，并且可以借用  量子位。 
    后者不同于基本的量子位分配，因为 Q# 操作可以使用“脏”量子位（不一定初始化为已知状态的量子位）来协助计算。

- [测试和调试](xref:microsoft.quantum.techniques.testing-and-debugging)详述了一些用于确保代码正常运行的技术。 
    由于量子信息通常不透明，因此调试量子程序可能需要专门的技术。 
    幸运的是，Q# 支持程序员习惯使用的许多经典调试技术，以及特定于量子的调试技术。 其中包括在 Q# 中创建/运行单元测试、在代码中嵌入对值和概率的断言  ，以及用于输出目标计算机状态的 `Dump` 函数。 
    后者可与完整状态模拟器一起使用，通过规避某些量子限制（例如，非克隆定理）来调试计算的某些部分。


![量子](~/media/mobius_strip_preview.png)
