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
# <a name="quantum-trace-simulator-invalidated-qubits-use-checker"></a><span data-ttu-id="91779-103">量程跟踪模拟器： qubits use 检查器失效</span><span class="sxs-lookup"><span data-stu-id="91779-103">Quantum trace simulator: invalidated qubits use checker</span></span>

<span data-ttu-id="91779-104">无效的 qubits use 检查器是量程开发工具包 [量程跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)的组成部分。</span><span class="sxs-lookup"><span data-stu-id="91779-104">The invalidated qubits use checker is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="91779-105">您可以使用它来检测由无效 qubits 导致的代码中的潜在 bug。</span><span class="sxs-lookup"><span data-stu-id="91779-105">You can use it to detect potential bugs in the code caused by invalid qubits.</span></span> 

## <a name="invalid-qubits"></a><span data-ttu-id="91779-106">无效的 qubits</span><span class="sxs-lookup"><span data-stu-id="91779-106">Invalid qubits</span></span>

<span data-ttu-id="91779-107">请考虑下面这段 Q# 代码，说明无效 qubits use 检测器检测到的问题：</span><span class="sxs-lookup"><span data-stu-id="91779-107">Consider the following piece of Q# code to illustrate the issues detected by the invalidated qubits use checker:</span></span>

```qsharp
operation UseReleasedQubit() : Unit {
    mutable q = new Qubit[1];
    using (ans = Qubit()) {
        set q w/= 0 <- ans;
    }
    H(q[0]);
}
```

<span data-ttu-id="91779-108">将 `H` 操作应用到时 `q[0]` ，它会指向已释放的 qubit，这可能会导致未定义的行为。</span><span class="sxs-lookup"><span data-stu-id="91779-108">When you apply the `H` operation to `q[0]`, it points to an already released qubit, which can cause undefined behavior.</span></span> <span data-ttu-id="91779-109">当启用了无效的 Qubits Use 检查器时， `InvalidatedQubitsUseCheckerException` 如果程序将操作应用于已发布的 qubit，则会引发异常。</span><span class="sxs-lookup"><span data-stu-id="91779-109">When the Invalidated Qubits Use Checker is enabled, it throws the exception `InvalidatedQubitsUseCheckerException` if the program applies an operation to an already released qubit.</span></span> <span data-ttu-id="91779-110">有关详细信息，请参阅 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException>。</span><span class="sxs-lookup"><span data-stu-id="91779-110">For more information, see <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException>.</span></span>

## <a name="invoking-the-invalidated-qubits-use-checker"></a><span data-ttu-id="91779-111">调用无效的 qubits use 检查器</span><span class="sxs-lookup"><span data-stu-id="91779-111">Invoking the invalidated qubits use checker</span></span>

<span data-ttu-id="91779-112">若要运行具有无效 qubits use 检查器的量程跟踪模拟器，您必须创建一个 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> 实例，将 `UseInvalidatedQubitsUseChecker` 属性设置为 **true**，然后 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> 使用作为参数创建新的实例 `QCTraceSimulatorConfiguration` 。</span><span class="sxs-lookup"><span data-stu-id="91779-112">To run the quantum trace simulator with the invalidated qubits use checker you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UseInvalidatedQubitsUseChecker` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseInvalidatedQubitsUseChecker = true;
var sim = new QCTraceSimulator(config);
```


## <a name="using-the-invalidated-qubits-use-checker-in-a-c-host-program"></a><span data-ttu-id="91779-113">在 c # 宿主程序中使用无效的 qubits use 检查器</span><span class="sxs-lookup"><span data-stu-id="91779-113">Using the invalidated qubits use checker in a C# host program</span></span>

<span data-ttu-id="91779-114">下面是一个 c # 宿主程序的示例，该程序使用已启用无效 qubits use 检查器的量程跟踪模拟器：</span><span class="sxs-lookup"><span data-stu-id="91779-114">The following is an example of C# host programs that uses the quantum trace simulator with the invalidated qubits use checker enabled:</span></span> 

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

## <a name="see-also"></a><span data-ttu-id="91779-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="91779-115">See also</span></span>

- <span data-ttu-id="91779-116">量程开发工具包 [量程跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro) 概述。</span><span class="sxs-lookup"><span data-stu-id="91779-116">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="91779-117"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API 参考。</span><span class="sxs-lookup"><span data-stu-id="91779-117">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="91779-118"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API 参考。</span><span class="sxs-lookup"><span data-stu-id="91779-118">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="91779-119"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException>API 参考。</span><span class="sxs-lookup"><span data-stu-id="91779-119">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.InvalidatedQubitsUseCheckerException> API reference.</span></span>