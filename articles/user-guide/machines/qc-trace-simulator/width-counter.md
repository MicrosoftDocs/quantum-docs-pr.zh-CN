---
title: 宽度计数器-量程开发工具包
description: 了解 Microsoft QDK width 计数器，该计数器使用量程跟踪模拟器来计算程序中由操作分配和借用的 qubits 的数量 Q# 。
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
no-loc:
- Q#
- $$v
ms.openlocfilehash: 701c36dd8c8b087a2728cd935aee0c2ffc4f59f9
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835938"
---
# <a name="quantum-trace-simulator-width-counter"></a>量程跟踪模拟器：宽度计数器

Width 计数器是量程开发工具包 [量程跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)的一部分。 您可以使用它来计算程序中每个操作所分配和借用的 qubits 的数目 Q# 。 一些基元操作可以分配额外的 qubits，例如，将受控 `X` 操作或受控 `T` 操作相乘。

## <a name="invoking-the-width-counter"></a>调用 width 计数器

若要运行具有 width 计数器的量程跟踪模拟器，您必须创建一个 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> 实例，将 `UseWidthCounter` 属性设置为 **true**，然后 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> 使用作为参数创建新的实例 `QCTraceSimulatorConfiguration` 。 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-width-counter-in-a-c-host-program"></a>在 c # 宿主程序中使用 width 计数器

本部分中的 c # 示例将根据 <xref:microsoft.quantum.intrinsic.x> 下面的示例代码，计算由执行乘法控制的操作所分配的额外 qubits 的数目 Q# ：

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

乘法控制 <xref:microsoft.quantum.intrinsic.x> 运算的作用是总共5个 qubits，分配两个 [辅助 qubits](xref:microsoft.quantum.glossary#ancilla)，且输入宽度为 **5**。 使用以下 c # 程序来验证计数：

```csharp 
var config = new QCTraceSimulatorConfiguration();
config.UseWidthCounter = true;
var sim = new QCTraceSimulator(config);
int totalNumberOfQubits = 5;
var res = ApplyMultiControlledX.Run(sim, totalNumberOfQubits).Result;

double allocatedQubits = 
    sim.GetMetric<Primitive.X, ApplyMultiControlledX>(
        WidthCounter.Metrics.ExtraWidth,
        functor: OperationFunctor.Controlled); 

double inputWidth =
    sim.GetMetric<Primitive.X, ApplyMultiControlledX>(
        WidthCounter.Metrics.InputWidth,
        functor: OperationFunctor.Controlled);
```

程序的第一个部分运行 `ApplyMultiControlledX` 操作。 第二部分使用 [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) 方法检索已分配的 qubits 的数目，以及操作收到的作为输入的 qubits 数 `Controlled X` 。 

最后，可以使用以下内容输出使用 CSV 格式的 width 计数器收集的所有统计信息：
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a>请参阅

- 量程开发工具包 [量程跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro) 概述。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API 参考。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API 参考。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.WidthCounter>API 参考。
