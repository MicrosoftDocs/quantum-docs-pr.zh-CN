---
title: Distinct 输入检查器
description: '了解 Microsoft QDK Distinct 输入检查器，该检查器将检查您的 Q # 代码，以了解与共享 qubits 的潜在冲突。'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
ms.openlocfilehash: 11a0573242c8afb12f242aa3be5f9cff18290452
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274400"
---
# <a name="distinct-inputs-checker"></a>Distinct 输入检查器

`Distinct Inputs Checker`是 "量程计算机[跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)" 的一部分。 它专用于检测代码中的潜在 bug。 请考虑以下 Q # 代码部分，以说明此包检测到的问题：

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

当用户查看此程序时，他们会假设和调用的顺序并 `op1` `op2` 不重要，因为 `q1` 和在不同的 `q2` qubits 上下班的 qubits 和操作是不同的。 现在，我们来看一个示例，其中使用了此操作：

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

现在 `op1` 和 `op2` 都是使用部分应用程序获得的并共享 qubit。 当用户 `ApplyBoth` 在上面的示例中调用时，操作的结果将取决于 `op1` 和内部的顺序 `op2` `ApplyBoth` 。 这无疑是用户预期会发生的情况。 `Distinct Inputs Checker`会在启用并引发时检测到这种情况 `DistinctInputsCheckerException` 。 有关更多详细信息，请参阅[DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException)上的 API 文档。

## <a name="using-the-distinct-inputs-checker-in-your-c-program"></a>在 c # 程序中使用不同的输入检查器

下面是将量程计算机跟踪模拟器用于已启用的 c # 驱动程序代码的示例 `Distinct Inputs Checker` ：

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

类 `QCTraceSimulatorConfiguration` 存储量程计算机跟踪模拟器的配置，并可作为构造函数的参数提供 `QCTraceSimulator` 。 如果 `useDistinctInputsChecker` 设置为 true，则 `Distinct Inputs Checker` 启用。 有关更多详细信息，请参阅[QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator)和[QCTRACESIMULATORCONFIGURATION](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?)上的 API 文档。

## <a name="see-also"></a>请参阅

- 量程计算机[跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)概述。
