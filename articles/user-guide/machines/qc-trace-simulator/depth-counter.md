---
title: 深度计数器-量程开发工具包
description: 了解 Microsoft QDK depth 计数器，该计数器使用量程跟踪模拟器收集程序中调用的每个操作的深度计数 Q# 。
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: conceptual
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
no-loc:
- Q#
- $$v
ms.openlocfilehash: 9c3a772861582e5c49fe5ad27519c25a59d617b1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98859050"
---
# <a name="quantum-trace-simulator-depth-counter"></a><span data-ttu-id="4dd05-103">量程跟踪模拟器：深度计数器</span><span class="sxs-lookup"><span data-stu-id="4dd05-103">Quantum trace simulator: depth counter</span></span>

<span data-ttu-id="4dd05-104">深度计数器是量程开发工具包 [量程跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)的一部分。</span><span class="sxs-lookup"><span data-stu-id="4dd05-104">The depth counter is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span>
<span data-ttu-id="4dd05-105">您可以使用它来收集表示在量程程序中调用的每个操作的深度下限的计数。</span><span class="sxs-lookup"><span data-stu-id="4dd05-105">You can use it to gather counts that represent the lower bound of the depth of every operation invoked in a quantum program.</span></span> 

## <a name="depth-values"></a><span data-ttu-id="4dd05-106">深度值</span><span class="sxs-lookup"><span data-stu-id="4dd05-106">Depth values</span></span>

<span data-ttu-id="4dd05-107">默认情况下，除 `T` 操作（深度为 **1**）外，所有操作的深度均为0。</span><span class="sxs-lookup"><span data-stu-id="4dd05-107">By default, all operations have a depth of **0** except the `T` operation, which has a depth of **1**.</span></span> <span data-ttu-id="4dd05-108">这意味着，在默认情况下，只 `T` 会计算操作深度 (通常需要) 。</span><span class="sxs-lookup"><span data-stu-id="4dd05-108">This means that by default, only the `T` depth of operations is computed (which is often desirable).</span></span> <span data-ttu-id="4dd05-109">深度计数器聚合并收集操作的 [调用关系图](https://en.wikipedia.org/wiki/Call_graph)的所有边缘上的统计信息。</span><span class="sxs-lookup"><span data-stu-id="4dd05-109">The depth counter aggregates and collects statistics over all the edges of the operation's [call graph](https://en.wikipedia.org/wiki/Call_graph).</span></span>

<span data-ttu-id="4dd05-110">所有 <xref:Microsoft.Quantum.Intrinsic> 操作都以单 qubit 循环、 <xref:Microsoft.Quantum.Intrinsic.T> 操作、qubit Clifford 操作、 <xref:Microsoft.Quantum.Intrinsic.CNOT> 操作和多 qubit Pauli 可观察量的度量来表示。</span><span class="sxs-lookup"><span data-stu-id="4dd05-110">All <xref:Microsoft.Quantum.Intrinsic> operations are expressed in terms of single-qubit rotations, <xref:Microsoft.Quantum.Intrinsic.T> operations, single-qubit Clifford operations, <xref:Microsoft.Quantum.Intrinsic.CNOT> operations, and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="4dd05-111">用户可以通过的字段设置每个基元操作的深度 `gateTimes` <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> 。</span><span class="sxs-lookup"><span data-stu-id="4dd05-111">Users can set the depth for each of the primitive operations via the `gateTimes` field of <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>.</span></span>

## <a name="invoking-the-depth-counter"></a><span data-ttu-id="4dd05-112">调用深度计数器</span><span class="sxs-lookup"><span data-stu-id="4dd05-112">Invoking the depth counter</span></span>

<span data-ttu-id="4dd05-113">若要使用深度计数器运行量程跟踪模拟器，您必须创建一个 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> 实例，将其 `UseDepthCounter` 属性设置为 **true**，然后 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> 使用作为参数创建新的实例 `QCTraceSimulatorConfiguration` 。</span><span class="sxs-lookup"><span data-stu-id="4dd05-113">To run the quantum trace simulator with the depth counter, you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set its `UseDepthCounter` property to **true**, and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with `QCTraceSimulatorConfiguration` as the parameter.</span></span> 

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UseDepthCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-depth-counter-in-a-c-host-program"></a><span data-ttu-id="4dd05-114">在 c # 宿主程序中使用深度计数器</span><span class="sxs-lookup"><span data-stu-id="4dd05-114">Using the depth counter in a C# host program</span></span>

<span data-ttu-id="4dd05-115">本部分中的 c # 示例将 `T` `CCNOT` 根据下面的示例代码计算操作的深度 Q# ：</span><span class="sxs-lookup"><span data-stu-id="4dd05-115">The C# example that follows in this section computes the `T` depth of the `CCNOT` operation, based on the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

<span data-ttu-id="4dd05-116">若要检查 `CCNOT` 是否具有 `T` 深度 **5** 并 `ApplySampleWithCCNOT` 具有 `T` 深度 **6**，请使用以下 c # 代码：</span><span class="sxs-lookup"><span data-stu-id="4dd05-116">To check that `CCNOT` has `T` depth **5** and `ApplySampleWithCCNOT` has `T` depth **6**, use the following C# code:</span></span>

```csharp
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.UseDepthCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

<span data-ttu-id="4dd05-117">程序的第一部分将运行 `ApplySampleWithCCNOT` 。</span><span class="sxs-lookup"><span data-stu-id="4dd05-117">The first part of the program runs `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="4dd05-118">第二部分使用 [`GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) 方法检索 `T` 和的深度 `CCNOT` `ApplySampleWithCCNOT` 。</span><span class="sxs-lookup"><span data-stu-id="4dd05-118">The second part uses the [`GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) method to retrieve the `T` depth of `CCNOT` and `ApplySampleWithCCNOT`.</span></span> 

<span data-ttu-id="4dd05-119">最后，你可以使用以下方法输出以 CSV 格式的深度计数器收集的所有统计信息：</span><span class="sxs-lookup"><span data-stu-id="4dd05-119">Finally, you can output all the statistics collected by the depth counter in CSV format using the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a><span data-ttu-id="4dd05-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4dd05-120">See also</span></span>

- <span data-ttu-id="4dd05-121">量程开发工具包 [量程跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro) 概述。</span><span class="sxs-lookup"><span data-stu-id="4dd05-121">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="4dd05-122"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API 参考。</span><span class="sxs-lookup"><span data-stu-id="4dd05-122">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="4dd05-123"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API 参考。</span><span class="sxs-lookup"><span data-stu-id="4dd05-123">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="4dd05-124"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.DepthCounter>API 参考。</span><span class="sxs-lookup"><span data-stu-id="4dd05-124">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.MetricsNames.DepthCounter> API reference.</span></span>
