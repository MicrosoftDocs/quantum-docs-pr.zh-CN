---
title: Distinct 输入检查器 |量程计算机跟踪模拟器 |Microsoft Docs
description: 量子计算机跟踪模拟器的概述
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
ms.openlocfilehash: 3c21a54f5da83bf1ea0792e79cc773be5fba71e8
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820957"
---
# <a name="distinct-inputs-checker"></a>Distinct 输入检查器

`Distinct Inputs Checker` 是 "量程计算机[跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)" 的一部分。 它专用于检测代码中的潜在 bug。 请考虑以下 Q # 代码部分，以说明此包检测到的问题：

```qsharp
operation ApplyBoth(
    q1 : Qubit,
    q2 : Qubit,
    op1 : (Qubit => Unit),
    op2 : (Qubit => Unit))
: Unit {
    op1(q1);
    op2(q2);
}
```

当用户查看此程序时，它们假设调用 `op1` 和 `op2` 的顺序并不重要，因为 `q1` 和 `q2` 是不同的 qubits 和操作在不同的 qubits 路程上操作。 现在，我们来看一个示例，其中使用了此操作：

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

现在 `op1` 和 `op2` 均使用部分应用程序获取，并共享 qubit。 当用户在上面的示例中调用 `ApplyBoth` 时，操作的结果将取决于 `ApplyBoth`内 `op1` 和 `op2` 的顺序。 这无疑是用户预期会发生的情况。 `Distinct Inputs Checker` 将在启用后检测到此类情况，并将引发 `DistinctInputsCheckerException`。 有关更多详细信息，请参阅[DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException)上的 API 文档。

## <a name="using-the-distinct-inputs-checker-in-your-c-program"></a>在C#程序中使用不同的输入检查器

下面是在启用 `Distinct Inputs Checker` 的C#情况下使用量程计算机跟踪模拟器的驱动程序代码示例：

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
            var traceSimCfg = new QCTraceSimulatorConfiguration();
            traceSimCfg.useDistinctInputsChecker = true; //enables distinct inputs checker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

类 `QCTraceSimulatorConfiguration` 存储量程计算机跟踪模拟器的配置，并可作为 `QCTraceSimulator` 构造函数的参数提供。 如果 `useDistinctInputsChecker` 设置为 true，则 `Distinct Inputs Checker` 处于启用状态。 有关更多详细信息，请参阅[QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator)和[QCTRACESIMULATORCONFIGURATION](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?)上的 API 文档。

## <a name="see-also"></a>另请参阅

- 量程计算机[跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)概述。
