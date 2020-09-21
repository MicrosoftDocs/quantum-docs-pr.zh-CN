---
title: 不同输入检查器-量程开发工具包
description: 了解 Microsoft QDK distinct 输入检查器，该检查器使用量程跟踪模拟器检查 Q# 代码是否存在与共享 qubits 的潜在冲突。
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.distinct-inputs
no-loc:
- Q#
- $$v
ms.openlocfilehash: bcb0bc92a546279496d27ad9b8c5f943ac133e2a
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833466"
---
# <a name="quantum-trace-simulator-distinct-inputs-checker"></a><span data-ttu-id="c1ac2-103">量程跟踪模拟器：不同的输入检查器</span><span class="sxs-lookup"><span data-stu-id="c1ac2-103">Quantum trace simulator: distinct inputs checker</span></span>

<span data-ttu-id="c1ac2-104">Distinct 输入检查器是量程开发工具包 [量程跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)的一部分。</span><span class="sxs-lookup"><span data-stu-id="c1ac2-104">The distinct inputs checker is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="c1ac2-105">您可以使用它来检测因与共享 qubits 冲突而导致的代码中的潜在 bug。</span><span class="sxs-lookup"><span data-stu-id="c1ac2-105">You can use it to detect potential bugs in the code caused by conflicts with shared qubits.</span></span> 

## <a name="conflicts-with-shared-qubits"></a><span data-ttu-id="c1ac2-106">与共享的 qubits 冲突</span><span class="sxs-lookup"><span data-stu-id="c1ac2-106">Conflicts with shared qubits</span></span>

<span data-ttu-id="c1ac2-107">请考虑下面这段 Q# 代码，说明 distinct 输入检查器检测到的问题：</span><span class="sxs-lookup"><span data-stu-id="c1ac2-107">Consider the following piece of Q# code to illustrate the issues detected by the distinct inputs checker:</span></span>

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

<span data-ttu-id="c1ac2-108">当你查看此程序时，你可以假定其调用的顺序 `op1` 并不 `op2` 重要，因为和在不同的 `q1` `q2` qubits 上下班的 qubits 和操作是不同的。</span><span class="sxs-lookup"><span data-stu-id="c1ac2-108">When you look at this program, you can assume that the order in which it calls `op1` and `op2` does not matter, because `q1` and `q2` are different qubits and operations acting on different qubits commute.</span></span> 

<span data-ttu-id="c1ac2-109">现在，请看下面的示例：</span><span class="sxs-lookup"><span data-stu-id="c1ac2-109">Now, consider this example:</span></span>

```qsharp
operation ApplyWithNonDistinctInputs() : Unit {
    using (qubits = Qubit[3]) {
        let op1 = CNOT(_, qubits[1]);
        let op2 = CNOT(qubits[1], _);
        ApplyBoth(qubits[0], qubits[2], op1, op2);
    }
}
```

<span data-ttu-id="c1ac2-110">请注意， `op1` 和 `op2` 均使用部分应用程序获取，并共享 qubit。</span><span class="sxs-lookup"><span data-stu-id="c1ac2-110">Note that `op1` and `op2` are both obtained using partial application and share a qubit.</span></span> <span data-ttu-id="c1ac2-111">`ApplyBoth`在此示例中调用时，操作的结果取决于 `op1` 预期发生的顺序和 `op2` 内部 `ApplyBoth` 。</span><span class="sxs-lookup"><span data-stu-id="c1ac2-111">When you call `ApplyBoth` in this example, the result of the operation depends on the order of `op1` and `op2` inside `ApplyBoth` - not what you would expect to happen.</span></span> <span data-ttu-id="c1ac2-112">启用 distinct 输入检查器时，它会检测到这种情况并引发 `DistinctInputsCheckerException` 。</span><span class="sxs-lookup"><span data-stu-id="c1ac2-112">When you enable the distinct inputs checker, it detects such situations and throws a `DistinctInputsCheckerException`.</span></span> <span data-ttu-id="c1ac2-113">有关详细信息，请参阅 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException> Q# API 库中的。</span><span class="sxs-lookup"><span data-stu-id="c1ac2-113">For more information, see <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException> in the Q# API library.</span></span>

## <a name="invoking-the-distinct-inputs-checker"></a><span data-ttu-id="c1ac2-114">调用 distinct 输入检查器</span><span class="sxs-lookup"><span data-stu-id="c1ac2-114">Invoking the distinct inputs checker</span></span>

<span data-ttu-id="c1ac2-115">若要使用不同的输入检查器运行量程跟踪模拟器，您必须创建一个 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> 实例，将 `UseDistinctInputsChecker` 属性设置为 **true**，然后 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> 使用作为参数创建新的实例 `QCTraceSimulatorConfiguration` 。</span><span class="sxs-lookup"><span data-stu-id="c1ac2-115">To run the quantum trace simulator with the distinct inputs checker you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UseDistinctInputsChecker` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDistinctInputsChecker = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-distinct-inputs-checker-in-a-c-host-program"></a><span data-ttu-id="c1ac2-116">在 c # 宿主程序中使用不同的输入检查器</span><span class="sxs-lookup"><span data-stu-id="c1ac2-116">Using the distinct inputs checker in a C# host program</span></span>

<span data-ttu-id="c1ac2-117">下面是在启用了 distinct 输入检查器的情况下使用量程跟踪模拟器的 c # 宿主程序的示例：</span><span class="sxs-lookup"><span data-stu-id="c1ac2-117">The following is an example of C# host program that uses the quantum trace simulator with the distinct inputs checker enabled:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="c1ac2-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="c1ac2-118">See also</span></span>

- <span data-ttu-id="c1ac2-119">量程开发工具包 [量程跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro) 概述。</span><span class="sxs-lookup"><span data-stu-id="c1ac2-119">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="c1ac2-120"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API 参考。</span><span class="sxs-lookup"><span data-stu-id="c1ac2-120">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="c1ac2-121"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API 参考。</span><span class="sxs-lookup"><span data-stu-id="c1ac2-121">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="c1ac2-122"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException>API 参考。</span><span class="sxs-lookup"><span data-stu-id="c1ac2-122">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.DistinctInputsCheckerException> API reference.</span></span>
