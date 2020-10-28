---
title: 深度计数器-量程开发工具包
description: 了解 Microsoft QDK depth 计数器，该计数器使用量程跟踪模拟器收集程序中调用的每个操作的深度计数 Q# 。
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
no-loc:
- Q#
- $$v
ms.openlocfilehash: 89d8a2c9f2ecd5c5332215cd4307bcf4a6422036
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92692099"
---
# <a name="quantum-trace-simulator-depth-counter"></a>量程跟踪模拟器：深度计数器

深度计数器是量程开发工具包 [量程跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)的一部分。
您可以使用它来收集表示在量程程序中调用的每个操作的深度下限的计数。 

## <a name="depth-values"></a>深度值

默认情况下，除 **0** `T` 操作（深度为 **1** ）外，所有操作的深度均为0。 这意味着，在默认情况下，只 `T` 会计算操作深度 (通常需要) 。 深度计数器聚合并收集操作的 [调用关系图](https://en.wikipedia.org/wiki/Call_graph)的所有边缘上的统计信息。

所有 <xref:Microsoft.Quantum.Intrinsic> 操作都以单 qubit 循环、 <xref:Microsoft.Quantum.Intrinsic.T> 操作、qubit Clifford 操作、 <xref:Microsoft.Quantum.Intrinsic.CNOT> 操作和多 qubit Pauli 可观察量的度量来表示。 用户可以通过的字段设置每个基元操作的深度 `gateTimes` <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> 。

## <a name="invoking-the-depth-counter"></a>调用深度计数器

若要使用深度计数器运行量程跟踪模拟器，您必须创建一个 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> 实例，将其 `UseDepthCounter` 属性设置为 **true** ，然后 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> 使用作为参数创建新的实例 `QCTraceSimulatorConfiguration` 。 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDepthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-depth-counter-in-a-c-host-program"></a>在 c # 宿主程序中使用深度计数器

本部分中的 c # 示例将 `T` `CCNOT` 根据下面的示例代码计算操作的深度 Q# ：

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

若要检查 `CCNOT` 是否具有 `T` 深度 **5** 并 `ApplySampleWithCCNOT` 具有 `T` 深度 **6** ，请使用以下 c # 代码：

```csharp
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.UseDepthCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

程序的第一部分将运行 `ApplySampleWithCCNOT` 。 第二部分使用 [`GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) 方法检索 `T` 和的深度 `CCNOT` `ApplySampleWithCCNOT` 。 

最后，你可以使用以下方法输出以 CSV 格式的深度计数器收集的所有统计信息：
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a>另请参阅

- 量程开发工具包 [量程跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro) 概述。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API 参考。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API 参考。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.DepthCounter>API 参考。
