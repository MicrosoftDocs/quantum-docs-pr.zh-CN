---
title: 量子跟踪模拟器 - Quantum 开发工具包
description: 了解如何使用 Microsoft 量子计算机跟踪模拟器来调试经典代码，并估计 Q# 程序的资源要求。
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 5d5efef037ff236bd040dfd88e94f7f3dd331aef
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868213"
---
# <a name="microsoft-quantum-development-kit-qdk-quantum-trace-simulator"></a>Microsoft Quantum 开发工具包 (QDK) 量子跟踪模拟器

QDK <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> 类运行量子程序，而无需实际模拟量子计算机的状态。 因此，量子跟踪模拟器能够运行使用数千个量子位的量子程序。  它适用于两个主要目的： 

* 调试属于量子程序的一部分的典型代码。 
* 估计在量子计算机上运行量子程序给定实例所需的资源。 事实上，[资源估算器](xref:microsoft.quantum.machines.resources-estimator)（提供更加有限的一组指标）是基于跟踪模拟器构建的。

## <a name="invoking-the-quantum-trace-simulator"></a>调用量子跟踪模拟器

可以使用量子跟踪模拟器来运行任何 Q# 操作。

与使用其他目标计算机一样，你首先创建 `QCTraceSimulator` 类的实例，然后将其作为操作的 `Run` 方法的第一个参数传递。

请注意，与 `QuantumSimulator` 类不同，`QCTraceSimulator` 类不实现 <xref:System.IDisposable> 接口，因此不需要将其放在 `using` 语句中。

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            QCTraceSimulator sim = new QCTraceSimulator();
            var res = MyQuantumProgram.Run(sim).Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

## <a name="providing-the-probability-of-measurement-outcomes"></a>提供测量结果的概率

因为量子跟踪模拟器不模拟实际的量子状态，所以它不能计算某个操作中的测量结果的概率。 

因此，如果某个操作包含测量，你必须使用 <xref:microsoft.quantum.diagnostics> 命名空间中的 <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> 操作显式提供这些概率。 以下示例对此进行了说明：

```qsharp
operation TeleportQubit(source : Qubit, target : Qubit) : Unit {
    using (qubit = Qubit()) {
        H(qubit);
        CNOT(qubit, target);
        CNOT(source, qubit);
        H(source);

        AssertMeasurementProbability([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertMeasurementProbability([PauliZ], [q], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(q) == One) { X(target); X(q); }
    }
}
```

当量子跟踪模拟器遇到 `AssertMeasurementProbability` 时，它将在 `source` 上记录该测量 `PauliZ`，而 `q` 应提供结果 `Zero`，其概率为 **0.5**。 当它稍后运行 `M` 操作时，它会找到结果概率的记录值，而 `M` 将返回 `Zero` 或 `One`，其概率为 **0.5**。 当相同的代码在跟踪量子状态的模拟器上运行时，该模拟器会检查 `AssertMeasurementProbability` 中提供的概率是否正确。

请注意，如果至少有一个测量操作未使用 `AssertMeasurementProbability` 进行批注，则模拟器会引发 [`UnconstrainedMeasurementException`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.unconstrainedmeasurementexception)。

## <a name="quantum-trace-simulator-tools"></a>量子跟踪模拟器工具

QDK 包括五个工具。你可以将这些工具与量子跟踪模拟器一起使用，以便检测程序中的 bug 以及进行量子程序资源估算： 

|工具 | 说明 |
|-----| -----|
|[不同输入检查器](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) |检查是否与共享量子位存在潜在冲突 |
|[失效的量子位使用检查器](xref:microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits)  |检查程序是否已将操作应用到已释放的量子位 |
|[基元操作计数器](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter)  | 计算在量子程序中调用的每个操作所使用的基元执行的数目  |
|[深度计数器](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)  |收集的计数表示在量子程序中调用的每个操作的深度的下限   |
|[宽度计数器](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)  |计算量子程序中每个操作所分配和借用的量子位数目 |

这些工具中的每一个均可通过以下方法启用：先在 `QCTraceSimulatorConfiguration` 中设置相应的标志，然后将配置传递给 `QCTraceSimulator` 声明。 若要了解如何使用这些工具中的每一个，请查看上一列表中的链接。 若要详细了解如何配置 `QCTraceSimulator`，请参阅 [QCTraceSimulatorConfiguration](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration)。

## <a name="qctracesimulator-methods"></a>QCTraceSimulator 方法

`QCTraceSimulator` 有多个内置方法，用于检索在量子操作期间跟踪的指标的值。 [QCTraceSimulator.GetMetric](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) 和 [QCTraceSimulator.ToCSV](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.tocsv) 方法的示例可在以下文章中找到：[基元操作计数器](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter)、[深度计数器](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)和[宽度计数器](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)。 有关所有可用方法的详细信息，请参阅 Q# API 参考中的 [QCTraceSimulator](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator)。  

## <a name="see-also"></a>另请参阅

- [量子资源估算器](xref:microsoft.quantum.machines.resources-estimator)
- [量子 Toffoli 模拟器](xref:microsoft.quantum.machines.toffoli-simulator)
- [量子全状态模拟器](xref:microsoft.quantum.machines.full-state-simulator) 