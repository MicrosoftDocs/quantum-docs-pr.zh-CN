---
title: Qubits use 检查器失效 |量程计算机跟踪模拟器 |Microsoft Docs
description: 量子计算机跟踪模拟器的概述
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits
ms.openlocfilehash: 093937346488725eacb69ef7da6affde764ec5c1
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820872"
---
# <a name="invalidated-qubits-use-checker"></a><span data-ttu-id="27c3c-103">Qubits Use 检查器失效</span><span class="sxs-lookup"><span data-stu-id="27c3c-103">Invalidated Qubits Use Checker</span></span>

<span data-ttu-id="27c3c-104">`Invalidated Qubits Use Checker` 是量程计算机[TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)的一部分，旨在检测代码中的潜在 bug。</span><span class="sxs-lookup"><span data-stu-id="27c3c-104">The `Invalidated Qubits Use Checker` is a part of the quantum computer [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) designed for detecting potential bugs in the code.</span></span> <span data-ttu-id="27c3c-105">请考虑以下 Q # 代码部分，以说明 `Invalidated Qubits Use Checker`检测到的问题。</span><span class="sxs-lookup"><span data-stu-id="27c3c-105">Consider the following piece of Q# code to illustrate the issues detected by the `Invalidated Qubits Use Checker`.</span></span>

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

<span data-ttu-id="27c3c-106">将 `H` 应用到时 `q[0]` 它指向已释放的 qubit。</span><span class="sxs-lookup"><span data-stu-id="27c3c-106">When `H` is applied to `q[0]` it points to an already released qubit.</span></span> <span data-ttu-id="27c3c-107">这可能会导致未定义的行为。</span><span class="sxs-lookup"><span data-stu-id="27c3c-107">This can cause undefined behavior.</span></span> <span data-ttu-id="27c3c-108">启用 `Invalidated Qubits Use Checker` 时，如果将操作应用于已发布的 qubit，则将引发异常 `InvalidatedQubitsUseCheckerException`。</span><span class="sxs-lookup"><span data-stu-id="27c3c-108">When the `Invalidated Qubits Use Checker` is enabled, the exception `InvalidatedQubitsUseCheckerException` will be thrown if an operation is applied to an already released qubit.</span></span> <span data-ttu-id="27c3c-109">有关更多详细信息，请参阅[InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException)上的 API 文档。</span><span class="sxs-lookup"><span data-stu-id="27c3c-109">See the API documentation on [InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException) for more details.</span></span>

## <a name="using-the-invalidated-qubits-use-checker-in-your-c-program"></a><span data-ttu-id="27c3c-110">在C#程序中使用无效的 Qubits Use 检查器</span><span class="sxs-lookup"><span data-stu-id="27c3c-110">Using the Invalidated Qubits Use Checker in your C# Program</span></span>

<span data-ttu-id="27c3c-111">下面是在启用了 `Invalidated Qubits Use Checker` C#的情况下使用量程计算机 `Trace
Simulator` 的驱动程序代码示例：</span><span class="sxs-lookup"><span data-stu-id="27c3c-111">The following is an example of C# driver code for using the quantum computer `Trace
Simulator` with the `Invalidated Qubits Use Checker` enabled:</span></span> 

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

<span data-ttu-id="27c3c-112">类 `QCTraceSimulatorConfiguration` 存储量程计算机跟踪模拟器的配置，并可作为 `QCTraceSimulator` 构造函数的参数提供。</span><span class="sxs-lookup"><span data-stu-id="27c3c-112">The class `QCTraceSimulatorConfiguration` stores the configuration of the quantum computer trace simulator and can be provided as an argument for the `QCTraceSimulator` constructor.</span></span> <span data-ttu-id="27c3c-113">如果 `useInvalidatedQubitsUseChecker` 设置为 true，则 `Invalidated Qubits Use Checker` 处于启用状态。</span><span class="sxs-lookup"><span data-stu-id="27c3c-113">When `useInvalidatedQubitsUseChecker` is set to true the `Invalidated Qubits Use Checker` is enabled.</span></span> <span data-ttu-id="27c3c-114">有关更多详细信息，请参阅[QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator)和[QCTRACESIMULATORCONFIGURATION](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration)上的 API 文档。</span><span class="sxs-lookup"><span data-stu-id="27c3c-114">See the API documentation on [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) and [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) for more details.</span></span>

## <a name="see-also"></a><span data-ttu-id="27c3c-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="27c3c-115">See also</span></span> ##

- <span data-ttu-id="27c3c-116">量程计算机[跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)概述。</span><span class="sxs-lookup"><span data-stu-id="27c3c-116">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
