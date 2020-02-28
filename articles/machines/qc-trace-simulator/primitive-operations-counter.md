---
title: 基元操作计数器
description: 了解 Microsoft QDK 基元操作计数器，该计数器跟踪量程程序中操作所使用的原始执行数。
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
ms.openlocfilehash: 8bdb0aed370e72b58b23025f1685ad7ce1a77a43
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2020
ms.locfileid: "77905941"
---
# <a name="primitive-operations-counter"></a>基元操作计数器  

`Primitive Operations Counter` 是 "量程计算机[跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)" 的一部分。 它计算在量程程序中调用的每个操作所使用的原始执行数。 `Microsoft.Quantum.Intrinsic` 中的所有操作都以单个 qubit 旋转、T 入口、单个 qubit Clifford 入口、CNOT-CONTAINS 入口和测量为多 qubit Pauli 可观察量表示。 收集的统计信息在操作调用关系图的边缘上聚合。 现在，让我们计算实现 `CCNOT` 操作需要多少 `T` 入口。 

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    } 
}
```

## <a name="using-the-primitive-operations-counter-within-a-c-program"></a>在C#程序中使用基元操作计数器

若要检查 `CCNOT` 确实需要 7 `T` 入口，`ApplySampleWithCCNOT` 执行8个 `T` 入口，我们可以使用以下C#代码：

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.usePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

程序的第一个部分执行 `ApplySampleWithCCNOT`。 在第二部分中，我们使用方法 `QCTraceSimulator.GetMetric` 获取 `ApplySampleWithCCNOT`所执行的 T 入口数： 

```csharp
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

如果使用两个类型参数调用 `GetMetric`，它将返回与给定的调用图形边缘关联的度量值。 在我们的示例操作中 `Primitive.CCNOT` 在 `ApplySampleWithCCNOT` 中调用，因此调用关系图包含 `<Primitive.CCNOT, ApplySampleWithCCNOT>`的边缘。 

若要获取使用的 `CNOT` 入口数，可以添加以下行：
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

最后，若要输出按 CSV 格式的入口计数器收集的所有统计信息，我们可以使用以下内容：
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a>另请参阅 ##

- 量程计算机[跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)概述。
