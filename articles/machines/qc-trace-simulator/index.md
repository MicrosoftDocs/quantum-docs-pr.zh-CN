---
title: 量子计算机跟踪模拟器 | Microsoft Docs
description: 量子计算机跟踪模拟器的概述
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.intro
ms.openlocfilehash: 929745a6da6034599e97d2f573190308fde6eb75
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820430"
---
# <a name="quantum-trace-simulator"></a>量子跟踪模拟器

Microsoft 量子计算机跟踪模拟器执行量子程序，而无需实际模拟量子计算机的状态。  出于此原因，跟踪模拟器可以执行使用数千个量子位的量子程序。  它适用于两个主要目的： 

* 调试属于量子程序的一部分的典型代码。 
* 估计在量子计算机上运行量子程序给定实例所需的资源。

必须执行度量时，跟踪模拟器依赖于用户提供的其他信息。 有关详细信息，请参阅[提供度量结果的概率](#providing-the-probability-of-measurement-outcomes)部分。 

## <a name="providing-the-probability-of-measurement-outcomes"></a>提供度量结果的概率

量子算法中出现两种类型的度量。 第一种类型起到辅助作用，用户通常从中了解结果的概率。 在这种情况下，用户可以编写 <xref:microsoft.quantum.intrinsic> 命名空间中的 <xref:microsoft.quantum.intrinsic.assertprob> 来表达此知识。 以下示例对此进行了说明：

```qsharp
operation TeleportQubit(source : Qubit, target : Qubit) : Unit {
    using (qubit = Qubit()) {
        H(qubit);
        CNOT(qubit, target);
        CNOT(source, qubit);
        H(source);

        AssertProb([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertProb([PauliZ], [q], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(q) == One) { X(target); X(q); }
    }
}
```

当跟踪模拟器执行 `AssertProb` 时，它将在 `source` 上记录测量 `PauliZ`，并且应向 `q` 提供 `Zero` 的结果，其概率为 0.5。 当模拟器稍后执行 `M` 时，它将找到结果概率的记录值，并且 `M` 将返回 `Zero` 或 `One`，其概率为 0.5。 在跟踪量子状态的模拟器上执行相同的代码时，此类模拟器将检查 `AssertProb` 中提供的概率是否正确。

## <a name="running-your-program-with-the-quantum-computer-trace-simulator"></a>使用量子计算机跟踪模拟器运行程序 

量子计算机跟踪模拟器可以被视为另一台目标计算机。 使用该模拟器的 C# 驱动程序与任何其他量子模拟器的 C# 驱动程序非常相似： 

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
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

请注意，如果至少有一个度量未使用 `AssertProb` 进行批注，则模拟器将从 `Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators` 命名空间引发 `UnconstrainedMeasurementException`。 请参阅有关 [UnconstrainedMeasurementException](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.UnconstrainedMeasurementException) 的 API 文档以了解更多详细信息。

除了运行量子程序之外，跟踪模拟器还附带了五个用于检测程序中的 bug 和执行量子程序资源估计的组件： 

* [不同输入检查器](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs)
* [失效的量子位使用检查器](xref:microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits)
* [基元操作计数器](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter)
* [线路深度计数器](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)
* [线路宽度计数器](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)

其中每个组件都可以通过在 `QCTraceSimulatorConfiguration` 中设置相应的标志来启用。 相应的引用文件中提供了有关使用其中每个组件的更多详细信息。 请参阅有关 [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) 的 API 文档以了解特定详细信息。

## <a name="see-also"></a>另请参阅
量子计算机[跟踪模拟器](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) C# 参考 

