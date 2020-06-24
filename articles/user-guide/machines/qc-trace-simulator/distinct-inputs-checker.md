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
# <a name="distinct-inputs-checker"></a><span data-ttu-id="bdebd-103">Distinct 输入检查器</span><span class="sxs-lookup"><span data-stu-id="bdebd-103">Distinct Inputs Checker</span></span>

<span data-ttu-id="bdebd-104">`Distinct Inputs Checker`是 "量程计算机[跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)" 的一部分。</span><span class="sxs-lookup"><span data-stu-id="bdebd-104">The `Distinct Inputs Checker` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="bdebd-105">它专用于检测代码中的潜在 bug。</span><span class="sxs-lookup"><span data-stu-id="bdebd-105">It is designed for detecting potential bugs in the code.</span></span> <span data-ttu-id="bdebd-106">请考虑以下 Q # 代码部分，以说明此包检测到的问题：</span><span class="sxs-lookup"><span data-stu-id="bdebd-106">Consider the following piece of Q# code to illustrate the issues detected by this package:</span></span>

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

<span data-ttu-id="bdebd-107">当用户查看此程序时，他们会假设和调用的顺序并 `op1` `op2` 不重要，因为 `q1` 和在不同的 `q2` qubits 上下班的 qubits 和操作是不同的。</span><span class="sxs-lookup"><span data-stu-id="bdebd-107">When the user looks at this program, they assume that the order in which `op1` and `op2` are called does not matter because `q1` and `q2` are different qubits and operations acting on different qubits commute.</span></span> <span data-ttu-id="bdebd-108">现在，我们来看一个示例，其中使用了此操作：</span><span class="sxs-lookup"><span data-stu-id="bdebd-108">Let us now consider an example, where this operation is used:</span></span>

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

<span data-ttu-id="bdebd-109">现在 `op1` 和 `op2` 都是使用部分应用程序获得的并共享 qubit。</span><span class="sxs-lookup"><span data-stu-id="bdebd-109">Now `op1` and `op2` are both obtained using partial application and share a qubit.</span></span> <span data-ttu-id="bdebd-110">当用户 `ApplyBoth` 在上面的示例中调用时，操作的结果将取决于 `op1` 和内部的顺序 `op2` `ApplyBoth` 。</span><span class="sxs-lookup"><span data-stu-id="bdebd-110">When the user calls `ApplyBoth` in the example above the result of the operation will depend on the order of `op1` and `op2` inside `ApplyBoth`.</span></span> <span data-ttu-id="bdebd-111">这无疑是用户预期会发生的情况。</span><span class="sxs-lookup"><span data-stu-id="bdebd-111">This is definitely not what the user would expect to happen.</span></span> <span data-ttu-id="bdebd-112">`Distinct Inputs Checker`会在启用并引发时检测到这种情况 `DistinctInputsCheckerException` 。</span><span class="sxs-lookup"><span data-stu-id="bdebd-112">The `Distinct Inputs Checker` will detect such situations when enabled and will throw `DistinctInputsCheckerException`.</span></span> <span data-ttu-id="bdebd-113">有关更多详细信息，请参阅[DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException)上的 API 文档。</span><span class="sxs-lookup"><span data-stu-id="bdebd-113">See the API documentation on [DistinctInputsCheckerException](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException) for more details.</span></span>

## <a name="using-the-distinct-inputs-checker-in-your-c-program"></a><span data-ttu-id="bdebd-114">在 c # 程序中使用不同的输入检查器</span><span class="sxs-lookup"><span data-stu-id="bdebd-114">Using the Distinct Inputs Checker in your C# Program</span></span>

<span data-ttu-id="bdebd-115">下面是将量程计算机跟踪模拟器用于已启用的 c # 驱动程序代码的示例 `Distinct Inputs Checker` ：</span><span class="sxs-lookup"><span data-stu-id="bdebd-115">The following is an example of C# driver code for using the quantum computer trace simulator with the `Distinct Inputs Checker` enabled:</span></span>

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

<span data-ttu-id="bdebd-116">类 `QCTraceSimulatorConfiguration` 存储量程计算机跟踪模拟器的配置，并可作为构造函数的参数提供 `QCTraceSimulator` 。</span><span class="sxs-lookup"><span data-stu-id="bdebd-116">The class `QCTraceSimulatorConfiguration` stores the configuration of the quantum computer trace simulator and can be provided as an argument for the `QCTraceSimulator` constructor.</span></span> <span data-ttu-id="bdebd-117">如果 `useDistinctInputsChecker` 设置为 true，则 `Distinct Inputs Checker` 启用。</span><span class="sxs-lookup"><span data-stu-id="bdebd-117">When `useDistinctInputsChecker` is set to true the `Distinct Inputs Checker` is enabled.</span></span> <span data-ttu-id="bdebd-118">有关更多详细信息，请参阅[QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator)和[QCTRACESIMULATORCONFIGURATION](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?)上的 API 文档。</span><span class="sxs-lookup"><span data-stu-id="bdebd-118">See the API documentation on [QCTraceSimulator](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) and [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration?) for more details.</span></span>

## <a name="see-also"></a><span data-ttu-id="bdebd-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="bdebd-119">See also</span></span>

- <span data-ttu-id="bdebd-120">量程计算机[跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)概述。</span><span class="sxs-lookup"><span data-stu-id="bdebd-120">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
