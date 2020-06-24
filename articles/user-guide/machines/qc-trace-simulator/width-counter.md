---
title: Width 计数器
description: 了解 Microsoft QDK Width 计数器，该计数器计算量程程序中每个操作所分配和借用的 qubits 数量。
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: a76292222950310acc90dded02980e4a5b792e76
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274393"
---
# <a name="width-counter"></a>Width 计数器

`Width Counter`计算每个操作分配和借用的 qubits 的数目。
来自命名空间的所有操作 `Microsoft.Quantum.Intrinsic` 都以单个 qubit 旋转、T 入口、单个 Qubit Clifford 门、cnot-contains 入口和度量标准表示。 一些基元操作可以分配额外的 qubits。 例如，将控制的 `X` 入口或控制的 `T` 入口相乘。 让我们计算由多次控制的门的实现所分配的额外 qubits 数 `X` ：

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

## <a name="using-width-counter-within-a-c-program"></a>在 c # 程序中使用 Width 计数器

多次控制 `X` 对总计 5 qubits 的操作将分配2个辅助 qubits，其输入宽度将为5。 若要检查是否是这种情况，可以使用以下 c # 程序：

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

程序的第一部分执行 `ApplyMultiControlledX` 。 在第二部分中，我们使用方法 `QCTraceSimulator.GetMetric` 来获取分配的 qubits 数，以及受控接收的 qubits 数 `X` 。 

最后，若要以 CSV 格式输出 width 计数器收集的所有统计信息，我们可以使用以下内容：
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a>请参阅 ##

- 量程计算机[跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)概述。
