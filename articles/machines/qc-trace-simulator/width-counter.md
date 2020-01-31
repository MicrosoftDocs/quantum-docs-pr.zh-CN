---
title: Width 计数器 |量程计算机跟踪模拟器 |Microsoft Docs
description: 量子计算机跟踪模拟器的概述
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: 9c3601e74eec17bd6b463e90f8f3085c959d6f95
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820362"
---
# <a name="width-counter"></a>Width 计数器

`Width Counter` 计算每个操作分配和借用的 qubits 的数目。
`Microsoft.Quantum.Intrinsic` 命名空间中的所有操作都以单个 qubit 旋转、T 入口、单个 qubit Clifford 门、CNOT-CONTAINS 关口和多 qubit Pauli 可观察量度量来表示。 一些基元操作可以分配额外的 qubits。 例如，将受控 `X` 入口或受控 `T` 入口。 让我们计算 qubits `X` 控制的分配的额外数：

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

## <a name="using-width-counter-within-a-c-program"></a>在C#程序中使用 Width 计数器

将受控 `X` 作用于总共5个 qubits 将分配2个辅助 qubits，其输入宽度将为5。 若要检查是否是这种情况，可以使用以下C#程序：

```csharp 
var config = new QCTraceSimulatorConfiguration();
config.useWidthCounter = true;
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

程序的第一个部分执行 `ApplyMultiControlledX`。 在第二部分中，我们使用方法 `QCTraceSimulator.GetMetric` 获取分配的 qubits 数，以及受控 `X` 接收为输入的 qubits 数。 

最后，若要以 CSV 格式输出 width 计数器收集的所有统计信息，我们可以使用以下内容：
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a>另请参阅 ##

- 量程计算机[跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)概述。
