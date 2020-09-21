---
title: 无效的 qubits use 检测器-量程开发工具包
description: 了解 Microsoft QDK 失效 qubits use 检查器，它使用量程跟踪模拟器检查您 Q# 的代码是否存在潜在的无效 qubits。
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
no-loc:
- Q#
- $$v
ms.openlocfilehash: 18371b3798d0eaa12d4e7107f58f44379594619f
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2020
ms.locfileid: "90835989"
---
# <a name="quantum-trace-simulator-invalidated-qubits-use-checker"></a>量程跟踪模拟器： qubits use 检查器失效

无效的 qubits use 检查器是量程开发工具包 [量程跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)的组成部分。 您可以使用它来检测由无效 qubits 导致的代码中的潜在 bug。 

## <a name="invalid-qubits"></a>无效的 qubits

请考虑下面这段 Q# 代码，说明无效 qubits use 检测器检测到的问题：

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

将 `H` 操作应用到时 `q[0]` ，它会指向已释放的 qubit，这可能会导致未定义的行为。 当启用了无效的 Qubits Use 检查器时， `InvalidatedQubitsUseCheckerException` 如果程序将操作应用于已发布的 qubit，则会引发异常。 有关详细信息，请参阅 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException>。

## <a name="invoking-the-invalidated-qubits-use-checker"></a>调用无效的 qubits use 检查器

若要运行具有无效 qubits use 检查器的量程跟踪模拟器，您必须创建一个 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> 实例，将 `UseInvalidatedQubitsUseChecker` 属性设置为 **true**，然后 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> 使用作为参数创建新的实例 `QCTraceSimulatorConfiguration` 。 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseInvalidatedQubitsUseChecker = true;
var sim = new QCTraceSimulator(config);
```


## <a name="using-the-invalidated-qubits-use-checker-in-a-c-host-program"></a>在 c # 宿主程序中使用无效的 qubits use 检查器

下面是一个 c # 宿主程序的示例，该程序使用已启用无效 qubits use 检查器的量程跟踪模拟器： 

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
            traceSimCfg.UseInvalidatedQubitsUseChecker = true; // enables UseInvalidatedQubitsUseChecker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

## <a name="see-also"></a>请参阅

- 量程开发工具包 [量程跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro) 概述。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API 参考。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API 参考。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException>API 参考。