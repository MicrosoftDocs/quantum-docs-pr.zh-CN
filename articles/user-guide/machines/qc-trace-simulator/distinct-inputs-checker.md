---
title: 不同输入检查器-量程开发工具包
description: '了解 Microsoft QDK distinct 输入检查器，该检查器使用量程跟踪模拟器检查您的 Q # 代码中是否存在与共享 qubits 的潜在冲突。'
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
ms.openlocfilehash: 49a1ccc5f37acfeaa1ee08bd974be45a40a76f93
ms.sourcegitcommit: cdf67362d7b157254e6fe5c63a1c5551183fc589
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/21/2020
ms.locfileid: "86871138"
---
# <a name="quantum-trace-simulator-distinct-inputs-checker"></a>量程跟踪模拟器：不同的输入检查器

Distinct 输入检查器是量程开发工具包[量程跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)的一部分。 您可以使用它来检测因与共享 qubits 冲突而导致的代码中的潜在 bug。 

## <a name="conflicts-with-shared-qubits"></a>与共享的 qubits 冲突

请考虑以下 Q # 代码部分来说明不同输入检查器检测到的问题：

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

当你查看此程序时，你可以假定其调用的顺序 `op1` 并不 `op2` 重要，因为和在不同的 `q1` `q2` qubits 上下班的 qubits 和操作是不同的。 

现在，请看下面的示例：

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

请注意， `op1` 和 `op2` 均使用部分应用程序获取，并共享 qubit。 `ApplyBoth`在此示例中调用时，操作的结果取决于 `op1` 预期发生的顺序和 `op2` 内部 `ApplyBoth` 。 启用 distinct 输入检查器时，它会检测到这种情况并引发 `DistinctInputsCheckerException` 。 有关详细信息，请参阅 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException> Q # API 库中的。

## <a name="invoking-the-distinct-inputs-checker"></a>调用 distinct 输入检查器

若要使用不同的输入检查器运行量程跟踪模拟器，您必须创建一个 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> 实例，将 `UseDistinctInputsChecker` 属性设置为**true**，然后 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> 使用作为参数创建新的实例 `QCTraceSimulatorConfiguration` 。 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDistinctInputsChecker = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-distinct-inputs-checker-in-a-c-host-program"></a>在 c # 宿主程序中使用不同的输入检查器

下面是在启用了 distinct 输入检查器的情况下使用量程跟踪模拟器的 c # 宿主程序的示例：

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
            traceSimCfg.UseDistinctInputsChecker = true; //enables distinct inputs checker
            QCTraceSimulator sim = new QCTraceSimulator(traceSimCfg);
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

## <a name="see-also"></a>另请参阅

- 量程开发工具包[量程跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)概述。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API 参考。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API 参考。
- <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException>API 参考。
