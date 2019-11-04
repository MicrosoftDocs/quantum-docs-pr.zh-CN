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
# <a name="invalidated-qubits-use-checker"></a><span data-ttu-id="a98db-103">Qubits Use 检查器失效</span><span class="sxs-lookup"><span data-stu-id="a98db-103">Invalidated Qubits Use Checker</span></span>

<span data-ttu-id="a98db-104">`Invalidated Qubits Use Checker` 是量程计算机[TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)的一部分，旨在检测代码中的潜在 bug。</span><span class="sxs-lookup"><span data-stu-id="a98db-104">The `Invalidated Qubits Use Checker` is a part of the quantum computer [TraceSimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) designed for detecting potential bugs in the code.</span></span> <span data-ttu-id="a98db-105">请考虑以下 Q # 代码部分，以说明 `Invalidated Qubits Use Checker`检测到的问题。</span><span class="sxs-lookup"><span data-stu-id="a98db-105">Consider the following piece of Q# code to illustrate the issues detected by the `Invalidated Qubits Use Checker`.</span></span>

```qsharp
operation UseReleasedQubitTest () : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

<span data-ttu-id="a98db-106">将 `H` 应用到时 `q[0]` 它指向已释放的 qubit。</span><span class="sxs-lookup"><span data-stu-id="a98db-106">When `H` is applied to `q[0]` it points to an already released qubit.</span></span> <span data-ttu-id="a98db-107">这可能会导致未定义的行为。</span><span class="sxs-lookup"><span data-stu-id="a98db-107">This can cause undefined behavior.</span></span> <span data-ttu-id="a98db-108">启用 `Invalidated Qubits Use Checker` 时，如果将操作应用于已发布的 qubit，则将引发异常 `InvalidatedQubitsUseCheckerException`。</span><span class="sxs-lookup"><span data-stu-id="a98db-108">When the `Invalidated Qubits Use Checker` is enabled, the exception `InvalidatedQubitsUseCheckerException` will be thrown if an operation is applied to an already released qubit.</span></span> <span data-ttu-id="a98db-109">有关更多详细信息，请参阅[InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException)上的 API 文档。</span><span class="sxs-lookup"><span data-stu-id="a98db-109">See the API documentation on [InvalidatedQubitsUseCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException) for more details.</span></span>

## <a name="using-the-invalidated-qubits-use-checker-in-your-c-program"></a><span data-ttu-id="a98db-110">在C#程序中使用无效的 Qubits Use 检查器</span><span class="sxs-lookup"><span data-stu-id="a98db-110">Using the Invalidated Qubits Use Checker in your C# Program</span></span>

<span data-ttu-id="a98db-111">下面是在启用了 `Invalidated Qubits Use Checker` C#的情况下使用量程计算机 `Trace
Simulator` 的驱动程序代码示例：</span><span class="sxs-lookup"><span data-stu-id="a98db-111">The following is an example of C# driver code for using the quantum computer `Trace
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

<span data-ttu-id="a98db-112">类 `QCTraceSimulatorConfiguration` 存储量程计算机跟踪模拟器的配置，并可作为 `QCTraceSimulator` 构造函数的参数提供。</span><span class="sxs-lookup"><span data-stu-id="a98db-112">The class `QCTraceSimulatorConfiguration` stores the configuration of the quantum computer trace simulator and can be provided as an argument for the `QCTraceSimulator` constructor.</span></span> <span data-ttu-id="a98db-113">如果 `useInvalidatedQubitsUseChecker` 设置为 true，则 `Invalidated Qubits Use Checker` 处于启用状态。</span><span class="sxs-lookup"><span data-stu-id="a98db-113">When `useInvalidatedQubitsUseChecker` is set to true the `Invalidated Qubits Use Checker` is enabled.</span></span> <span data-ttu-id="a98db-114">有关更多详细信息，请参阅[QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator)和[QCTRACESIMULATORCONFIGURATION](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration)上的 API 文档。</span><span class="sxs-lookup"><span data-stu-id="a98db-114">See the API documentation on [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) and [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) for more details.</span></span>

## <a name="see-also"></a><span data-ttu-id="a98db-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a98db-115">See also</span></span> ##

- <span data-ttu-id="a98db-116">量程计算机[跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)概述。</span><span class="sxs-lookup"><span data-stu-id="a98db-116">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
