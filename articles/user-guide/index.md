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
# <a name="the-no-locq-user-guide"></a>Q# 用户指南

欢迎查看 Q# 用户指南！ 

在本指南的不同主题中，我们介绍了使用 Q# 开发量子程序的一些基础知识。

有关 Q# 量子程序语言的完整规范和文档，请参阅 [Q# 语言指南](xref:microsoft.quantum.qsharp.index)。 

## <a name="user-guide-contents"></a>用户指南内容

- [Q# 程序](xref:microsoft.quantum.guide.programs)：用 Q# 编写的量子程序的快速简介。 

- [Q# 程序的运行方式](xref:microsoft.quantum.guide.host-programs)：描述 Q# 程序的运行方式，并简要介绍可用于调用该程序的各种方式：通过命令行、Q# Jupyter Notebook，或者通过用 Python 或 .NET 语言编写的经典主机程序。

- [测试和调试](xref:microsoft.quantum.guide.testingdebugging)：详细介绍了一些用于确保代码正常运行的技术。 
    由于量子信息通常不透明，因此调试量子程序可能需要专门的技术。 
    幸运的是，Q# 支持程序员熟悉的许多经典调试技术，以及特定于量子的调试技术。 其中包括以 Q# 创建和运行单元测试、在代码中嵌入对值和概率的断言，以及用于输出目标计算机状态的 `Dump` 函数。 
    后者可与全状态模拟器一起使用，通过规避某些量子限制（例如，[非克隆定理](xref:microsoft.quantum.concepts.pauli)）来调试计算的某些部分。

### <a name="quantum-simulators-and-resource-estimators"></a>量子模拟器和资源估算器

- [量子模拟器和主机应用程序](xref:microsoft.quantum.machines)：概述了不同的可用模拟器，简要介绍了主机程序和目标计算机如何搭配使用来运行 Q# 程序。

- [全状态模拟器](xref:microsoft.quantum.machines.full-state-simulator)：模拟完整量子状态的目标计算机。 适用于完全运行或调试规模更小的程序（不超过几十个量子位）

- [资源估算器](xref:microsoft.quantum.machines.resources-estimator)：估计在量子计算机上运行给定的 Q# 操作实例所需的资源。

- [跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)：在不实际模拟量子计算机状态的情况下运行量子程序，因此可运行使用数千个量子位的量子程序。 适用于在量子程序中调试经典代码，以及预估所需的资源。

- [Toffoli 模拟器](xref:microsoft.quantum.machines.toffoli-simulator)：一种特殊用途的量子模拟器，可处理数百万个量子位，但仅适用于具有一组有限的量子操作（X、CNOT 和多受控 X）的程序。

### <a name="quick-reference-pages"></a>快速参考页面

- [IQ# Magic 命令](xref:microsoft.quantum.guide.quickref.iqsharp)：Q# Jupyter 笔记本中 IQ# Magic 命令的快速参考页面。
