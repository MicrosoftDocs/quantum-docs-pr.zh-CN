---
title: 深度计数器 |量程计算机跟踪模拟器 |Microsoft Docs
description: 量程计算机跟踪模拟器概述
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
ms.openlocfilehash: f5fcaa64e91290d377eeba597df2e307e187277c
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184893"
---
# <a name="depth-counter"></a>深度计数器

`Depth Counter` 是 "量程计算机[跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)" 的一部分。
它用于收集量程程序中调用的每个操作的深度计数。 <xref:microsoft.quantum.intrinsic> 中的所有操作都以单个 qubit 旋转、T 入口、单个 qubit Clifford 入口、CNOT-CONTAINS 入口和测量为多 qubit Pauli 可观察量表示。 用户可以通过 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>的 "`gateTimes`" 字段设置每个基元操作的深度。

默认情况下，除了深度为1的 T 门外，所有操作的深度为0。 这意味着，在默认情况下，只计算 T 操作的 T 深度（通常是必需的）。 收集的统计信息在操作调用关系图的所有边缘上聚合在一起。 

现在，我们来计算 <xref:microsoft.quantum.intrinsic.ccnot> 操作的 <xref:microsoft.quantum.intrinsic.t> 深度。 我们将使用以下 Q # 驱动程序代码： 

```qsharp
open Microsoft.Quantum.Primitive;
operation CCNOTDriver() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

## <a name="using-depth-counter-within-a-c-program"></a>在C#程序中使用深度计数器

若要检查 `CCNOT` 是否具有 `T` 深度5并且 `CCNOTDriver` 具有 `T` 深度6，我们可以使用C#以下代码：

```csharp 
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.useDepthCounter = true;
var sim = new QCTraceSimulator(config);
var res = CCNOTDriver.Run(sim).Result;

double tDepth = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<CCNOTDriver>(DepthCounter.Metrics.Depth);
```

程序的第一个部分执行 `CCNOTDriver`。 在第二部分中，我们使用方法 `QCTraceSimulator.GetMetric` 获取 `CCNOT` 和 `CCNOTDriver`的 `T` 深度： 

```csharp
double tDepth = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<CCNOTDriver>(DepthCounter.Metrics.Depth);
```

最后，若要输出按 CSV 格式 `Depth Counter` 收集的所有统计信息，可以使用以下内容：
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a>另请参阅 ##

- 量程计算机[跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)概述。
