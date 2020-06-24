---
title: 失效的量子位使用检查器
description: '了解 Microsoft QDK 失效 Qubits Use 检查器，它会检查您的 Q # 代码中是否有可能无效的 Qubits。'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
ms.openlocfilehash: e2bbb12448e27f28db030a0084302fb24f46f26b
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274394"
---
# <a name="invalidated-qubits-use-checker"></a>Qubits Use 检查器失效

`Invalidated Qubits Use Checker`是量程计算机[TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)的一部分，旨在检测代码中的潜在 bug。 请考虑以下 Q # 代码部分，以说明检测到的问题 `Invalidated Qubits Use Checker` 。

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

当 `H` 应用于时， `q[0]` 它指向已释放的 qubit。 这可能会导致未定义的行为。 启用后 `Invalidated Qubits Use Checker` ， `InvalidatedQubitsUseCheckerException` 如果将操作应用于已发布的 qubit，则会引发异常。 有关更多详细信息，请参阅[InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException)上的 API 文档。

## <a name="using-the-invalidated-qubits-use-checker-in-your-c-program"></a>在 c # 程序中使用无效的 Qubits Use 检查器

下面是将量程计算机用于 `Trace
Simulator` 已启用的 c # 驱动程序代码的示例 `Invalidated Qubits Use Checker` ： 

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
            traceSimCfg.useInvalidatedQubitsUseChecker = true; // enables useInvalidatedQubitsUseChecker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

类 `QCTraceSimulatorConfiguration` 存储量程计算机跟踪模拟器的配置，并可作为构造函数的参数提供 `QCTraceSimulator` 。 如果 `useInvalidatedQubitsUseChecker` 设置为 true，则 `Invalidated Qubits Use Checker` 启用。 有关更多详细信息，请参阅[QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator)和[QCTRACESIMULATORCONFIGURATION](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration)上的 API 文档。

## <a name="see-also"></a>请参阅 ##

- 量程计算机[跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)概述。
