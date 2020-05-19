---
title: Q# 用户指南
description: 用户指南的目的和内容概述
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide
ms.openlocfilehash: f535aaedbe6ce181375d48f7023409ad8212c702
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430605"
---
# <a name="the-q-user-guide"></a>Q# 用户指南

欢迎查看 Q# 用户指南！ 

我们将在此处详细介绍 Q# 语言的核心概念，以及编写量子程序所需的各项信息。

## <a name="user-guide-contents"></a>用户指南内容

- [Q# 基本信息](xref:microsoft.quantum.guide.basics)：简要概述了 Q# 编程语言的用途和功能。 

### <a name="q-language"></a>Q# 语言

- [Q# 中的类型](xref:microsoft.quantum.guide.types)：列出了 Q# 类型模型，还描述了用于指定和使用这些类型的语法。

- [类型表达式](xref:microsoft.quantum.guide.expressions)：详细说明了如何在 Q# 中指定、引用、组合和操作各类型的值。 

### <a name="using-q"></a>使用 Q#

- [Q# 文件结构](xref:microsoft.quantum.guide.filestructure)：描述了 `*.qs` Q# 文件的结构和语法。

- [操作和函数](xref:microsoft.quantum.guide.operationsfunctions)：详细介绍了 Q# 语言的两种可调用类型，一种是“操作”，其中包含在量子位寄存器上进行的操作；另一种是“函数”，仅限于经典信息的处理 。 
    你将在此处了解如何定义和调用它们，包括量子操作的伴随和受控版本。

- [变量](xref:microsoft.quantum.guide.variables)：介绍了变量在 Q# 程序中的角色及其有效使用方式。 
    例如，你能找到关于绑定范围的信息，还能了解到不可变/可变变量之间的区别，以及如何分配/取消分配它们。

- [使用量子位](xref:microsoft.quantum.guide.qubits)：介绍用于处理单个量子位和量子位系统的 Q# 功能。 
    具体说来，这需要进行分配，在其上执行操作，并最终进行度量。 

- [控制流](xref:microsoft.quantum.guide.controlflow)：详细描述了 Q# 中提供的编程控制流模式，其中包含许多标准技术（条件执行、for 循环、while 循环等），以及量子特定的“重复直到成功”模式。

- [测试和调试](xref:microsoft.quantum.guide.testingdebugging)：详细介绍了一些用于确保代码正常运行的技术。 
    由于量子信息通常不透明，因此调试量子程序可能需要专门的技术。 
    幸运的是，Q# 支持程序员习惯使用的许多经典调试技术，以及特定于量子的调试技术。 其中包括在 Q# 中创建/运行单元测试、在代码中嵌入对值和概率的断言，以及用于输出目标计算机状态的 `Dump` 函数。 
    后者可与全状态模拟器一起使用，通过规避某些量子限制（例如，非克隆定理）来调试计算的某些部分。

### <a name="quantum-simulators-and-resource-estimators"></a>量子模拟器和资源估算器

- [量子模拟器和主机应用程序](xref:microsoft.quantum.machines)：概述了不同的可用模拟器，以及主机程序与目标计算机之间的常规执行模型。

- [全状态模拟器](xref:microsoft.quantum.machines.full-state-simulator)：模拟完整量子状态的目标计算机。 适用于完全执行或调试规模更小的程序（不超过几十个量子位）

- [资源估算器](xref:microsoft.quantum.machines.resources-estimator)：估计在量子计算机上运行给定的 Q# 操作实例所需的资源。

- [跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)：在不实际模拟量子计算机状态的情况下执行量子程序，因此可执行使用数千个量子位的量子程序。 适用于在量子程序中调试经典代码，以及预估所需的资源。

- [Toffoli 模拟器](xref:microsoft.quantum.machines.toffoli-simulator)：一种特殊用途的量子模拟器，可处理数百万个量子位，但仅适用于具有一组有限的量子操作（即 X、CNOT 和多受控 X）的程序。

### <a name="quick-reference-pages"></a>快速参考页面

- [IQ# Magic 命令](xref:microsoft.quantum.guide.quickref.iqsharp)：Q# Jupyter 笔记本中 IQ# Magic 命令的快速参考页面
