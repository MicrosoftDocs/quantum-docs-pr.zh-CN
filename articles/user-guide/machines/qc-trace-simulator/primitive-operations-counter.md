---
title: 基元操作计数器-量程开发工具包
description: 了解 Microsoft QDK 基元操作计数器，该计数器使用量程跟踪模拟器跟踪程序中操作所使用的基元进程 Q# 。
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
no-loc:
- Q#
- $$v
ms.openlocfilehash: 8ee9ce25e680112e2f3c68d82ae9267c1b0fb355
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835972"
---
# <a name="quantum-trace-simulator-primitive-operations-counter"></a>量程跟踪模拟器：基元操作计数器

基元操作计数器是量程开发工具包 [量程跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)的一部分。 它计算在量程程序中调用的每个操作所使用的基元进程的数目。 

所有 <xref:microsoft.quantum.intrinsic> 操作都以单 qubit 循环、T 操作、Qubit Clifford 操作、cnot-contains 操作和多 Qubit Pauli 可观察量的度量来表示。 基元操作计数器聚合并收集操作的 [调用关系图](https://en.wikipedia.org/wiki/Call_graph)边缘的统计信息。

## <a name="invoking-the-primitive-operation-counter"></a>调用基元操作计数器

若要使用基元操作计数器运行量程跟踪模拟器，您必须创建一个 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> 实例，将属性设置 `UsePrimitiveOperationsCounter` 为 **true**，然后 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> 使用作为参数创建新的实例 `QCTraceSimulatorConfiguration` 。

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UsePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-primitive-operation-counter-in-a-c-host-program"></a>在 c # 宿主程序中使用基元操作计数器

本部分中的 c # 示例将根据 <xref:microsoft.quantum.intrinsic.t> <xref:microsoft.quantum.intrinsic.ccnot> 下面的示例代码，计算实现该操作所需的操作数 Q# ：

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

若要检查是否 `CCNOT` 需要七个 `T` 操作并 `ApplySampleWithCCNOT` 运行8个 `T` 操作，请使用以下 c # 代码：

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.UsePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

程序的第一部分将运行 `ApplySampleWithCCNOT` 。 第二部分使用 [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) 方法检索运行的操作的数目 `T` `ApplySampleWithCCNOT` ： 

`GetMetric`使用两个类型参数调用时，它将返回与给定的调用图形边缘关联的度量值。 在前面的示例中，程序在 `Primitive.CCNOT` 中调用操作 `ApplySampleWithCCNOT` ，因此调用关系图包含边缘 `<Primitive.CCNOT, ApplySampleWithCCNOT>` 。 

若要检索使用的 `CNOT` 操作数，请添加以下行：
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

最后，你可以使用以下方法输出使用 CSV 格式的基元操作计数器收集的所有统计信息：
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a>请参阅

- 量程开发工具包 [量程跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro) 概述。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API 参考。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API 参考。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.PrimitiveOperationsGroupsNames>API 参考。