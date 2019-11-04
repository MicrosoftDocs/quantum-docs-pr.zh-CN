---
title: Qubits use 检查器失效 |量程计算机跟踪模拟器 |Microsoft Docs
description: 量程计算机跟踪模拟器概述
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
ms.openlocfilehash: 7403381b995ab660aa5cbc5a52b1e12c5c9ce442
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184961"
---
# <a name="invalidated-qubits-use-checker"></a>Qubits Use 检查器失效

`Invalidated Qubits Use Checker` 是量程计算机[TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)的一部分，旨在检测代码中的潜在 bug。 请考虑以下 Q # 代码部分，以说明 `Invalidated Qubits Use Checker`检测到的问题。

```qsharp
operation UseReleasedQubitTest () : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

将 `H` 应用到时 `q[0]` 它指向已释放的 qubit。 这可能会导致未定义的行为。 启用 `Invalidated Qubits Use Checker` 时，如果将操作应用于已发布的 qubit，则将引发异常 `InvalidatedQubitsUseCheckerException`。 有关更多详细信息，请参阅[InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException)上的 API 文档。

## <a name="using-the-invalidated-qubits-use-checker-in-your-c-program"></a>在C#程序中使用无效的 Qubits Use 检查器

下面是在启用了 `Invalidated Qubits Use Checker` C#的情况下使用量程计算机 `Trace
Simulator` 的驱动程序代码示例： 

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

类 `QCTraceSimulatorConfiguration` 存储量程计算机跟踪模拟器的配置，并可作为 `QCTraceSimulator` 构造函数的参数提供。 如果 `useInvalidatedQubitsUseChecker` 设置为 true，则 `Invalidated Qubits Use Checker` 处于启用状态。 有关更多详细信息，请参阅[QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator)和[QCTRACESIMULATORCONFIGURATION](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration)上的 API 文档。

## <a name="see-also"></a>另请参阅 ##

- 量程计算机[跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)概述。
