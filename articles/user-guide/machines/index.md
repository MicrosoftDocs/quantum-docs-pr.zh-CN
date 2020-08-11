---
title: 量子模拟器和 Q# 程序
description: 介绍可用作 Q# 程序的目标计算机的量子模拟器。
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 6/17/2020
ms.topic: article
uid: microsoft.quantum.machines
no-loc:
- Q#
- $$v
ms.openlocfilehash: 77401ca3642b89d708f338f852dc60bf7346b87b
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868298"
---
# <a name="quantum-simulators"></a>量子模拟器

量子模拟器是在经典计算机上运行并充当 Q# 程序的目标计算机的软件程序。借助这些软件程序，可以在预测量子位将如何对不同操作做出反应的环境中运行和测试量子程序。 本文介绍 Quantum 开发工具包 (QDK) 中包含哪些量子模拟器，以及将 Q# 程序传递到量子模拟器的不同方式，例如，可通过命令行传递，也可通过以经典语言编写的驱动程序代码传递。  



## <a name="the-quantum-development-kit-qdk-quantum-simulators"></a>Quantum 开发工具包 (QDK) 量子模拟器

量子模拟器负责为算法提供量子基元的实现。 其中包括 `H`、`CNOT` 和 `Measure` 等基元操作，以及量子位管理和跟踪。 QDK 包括不同类的量子模拟器（代表同一量子算法的不同执行模型）。 


每种类型的量子模拟器可以提供这些基元的不同实现。 例如，[全状态模拟器](xref:microsoft.quantum.machines.full-state-simulator)通过全面模拟[量子状态矢量](xref:microsoft.quantum.glossary#quantum-state)来运行量子算法，而[量子计算机跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)则根本不考虑实际的量子状态。 而是跟踪算法的量子门、量子位和其他资源使用情况。

### <a name="quantum-machine-classes"></a>量子计算机类

QDK 会在将来定义更多量子计算机类以支持其他类型的模拟，并支持在量子硬件上执行。 在改变基础计算机实现的同时允许算法保持不变，可以轻松地在模拟中测试和调试算法，然后在实际硬件上运行该算法，确信该算法没有发生更改。

QDK 包含多个量子计算机类，全都在 `Microsoft.Quantum.Simulation.Simulators` 命名空间中定义。

|模拟器 |类|说明|
|-----|------|---|
|[全状态模拟器](xref:microsoft.quantum.machines.full-state-simulator)| `QuantumSimulator` | 运行和调试量子算法，限制为大约 30 个量子位。 |
|[简单的资源估算器](xref:microsoft.quantum.machines.resources-estimator)| `ResourcesEstimator` | 对运行量子算法所需的资源进行顶级分析，支持数千个量子位。|
|[基于跟踪的资源估算器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)|  `QCTraceSimulator` |对算法的整个调用关系图的资源消耗量运行高级分析，支持数千个量子位。|
|[Toffoli 模拟器](xref:microsoft.quantum.machines.toffoli-simulator)| `ToffoliSimulator` |模拟仅限 `X` 和 `CNOT` 在内的量子算法和多重控制的 `X` 量子操作，支持数百万个量子位。 |

## <a name="invoking-the-quantum-simulator"></a>调用量子模拟器

在 [Q# 程序的运行方式](xref:microsoft.quantum.guide.host-programs)中，演示了三种将 Q# 代码传递到量子模拟器的方式： 

* 使用命令行
* 使用 Python 主机程序
* 使用 C# 主机程序

量子机是普通 .NET 类的实例，因此它们是通过调用其构造函数来创建的，就像任何 .NET 类一样。 具体操作方式取决于运行 Q# 程序的方式。

## <a name="next-steps"></a>后续步骤

* 若要详细了解如何在不同环境中调用 Q# 程序的目标计算机，请参阅 [Q# 程序的运行方式](xref:microsoft.quantum.guide.host-programs)。
