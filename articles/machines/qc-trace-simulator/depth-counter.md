---
title: 深度计数器 |量程计算机跟踪模拟器 |Microsoft Docs
description: 量程计算机跟踪模拟器概述
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
ms.openlocfilehash: f5fcaa64e91290d377eeba597df2e307e187277c
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184893"
---
# <a name="depth-counter"></a><span data-ttu-id="f23b0-103">深度计数器</span><span class="sxs-lookup"><span data-stu-id="f23b0-103">Depth Counter</span></span>

<span data-ttu-id="f23b0-104">`Depth Counter` 是 "量程计算机[跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)" 的一部分。</span><span class="sxs-lookup"><span data-stu-id="f23b0-104">The `Depth Counter` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span>
<span data-ttu-id="f23b0-105">它用于收集量程程序中调用的每个操作的深度计数。</span><span class="sxs-lookup"><span data-stu-id="f23b0-105">It is used to gather counts of the depth of every operation invoked in a quantum program.</span></span> <span data-ttu-id="f23b0-106"><xref:microsoft.quantum.intrinsic> 中的所有操作都以单个 qubit 旋转、T 入口、单个 qubit Clifford 入口、CNOT-CONTAINS 入口和测量为多 qubit Pauli 可观察量表示。</span><span class="sxs-lookup"><span data-stu-id="f23b0-106">All operations from <xref:microsoft.quantum.intrinsic> are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="f23b0-107">用户可以通过 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>的 "`gateTimes`" 字段设置每个基元操作的深度。</span><span class="sxs-lookup"><span data-stu-id="f23b0-107">Users can set the depth for each of the primitive operations via the `gateTimes` field of <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>.</span></span>

<span data-ttu-id="f23b0-108">默认情况下，除了深度为1的 T 门外，所有操作的深度为0。</span><span class="sxs-lookup"><span data-stu-id="f23b0-108">By default, all operations have depth 0 except the T gate which has depth 1.</span></span> <span data-ttu-id="f23b0-109">这意味着，在默认情况下，只计算 T 操作的 T 深度（通常是必需的）。</span><span class="sxs-lookup"><span data-stu-id="f23b0-109">This means that by default, only the T depth of operations is computed (which is often desirable).</span></span> <span data-ttu-id="f23b0-110">收集的统计信息在操作调用关系图的所有边缘上聚合在一起。</span><span class="sxs-lookup"><span data-stu-id="f23b0-110">Collected statistics are aggregated over all the edges of the operations call graph.</span></span> 

<span data-ttu-id="f23b0-111">现在，我们来计算 <xref:microsoft.quantum.intrinsic.ccnot> 操作的 <xref:microsoft.quantum.intrinsic.t> 深度。</span><span class="sxs-lookup"><span data-stu-id="f23b0-111">Let us now compute the <xref:microsoft.quantum.intrinsic.t> depth of the <xref:microsoft.quantum.intrinsic.ccnot> operation.</span></span> <span data-ttu-id="f23b0-112">我们将使用以下 Q # 驱动程序代码：</span><span class="sxs-lookup"><span data-stu-id="f23b0-112">We will use the following Q# driver code:</span></span> 

```qsharp
open Microsoft.Quantum.Primitive;
operation CCNOTDriver() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

## <a name="using-depth-counter-within-a-c-program"></a><span data-ttu-id="f23b0-113">在C#程序中使用深度计数器</span><span class="sxs-lookup"><span data-stu-id="f23b0-113">Using Depth Counter within a C# Program</span></span>

<span data-ttu-id="f23b0-114">若要检查 `CCNOT` 是否具有 `T` 深度5并且 `CCNOTDriver` 具有 `T` 深度6，我们可以使用C#以下代码：</span><span class="sxs-lookup"><span data-stu-id="f23b0-114">To check that `CCNOT` has `T` depth 5 and `CCNOTDriver` has `T` depth 6 we can use the following C# code:</span></span>

```csharp 
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.useDepthCounter = true;
var sim = new QCTraceSimulator(config);
var res = CCNOTDriver.Run(sim).Result;

double tDepth = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<CCNOTDriver>(DepthCounter.Metrics.Depth);
```

<span data-ttu-id="f23b0-115">程序的第一个部分执行 `CCNOTDriver`。</span><span class="sxs-lookup"><span data-stu-id="f23b0-115">The first part of the program executes `CCNOTDriver`.</span></span> <span data-ttu-id="f23b0-116">在第二部分中，我们使用方法 `QCTraceSimulator.GetMetric` 获取 `CCNOT` 和 `CCNOTDriver`的 `T` 深度：</span><span class="sxs-lookup"><span data-stu-id="f23b0-116">In the second part, we use the method `QCTraceSimulator.GetMetric` to get the `T` depth of `CCNOT` and `CCNOTDriver`:</span></span> 

```csharp
double tDepth = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<CCNOTDriver>(DepthCounter.Metrics.Depth);
```

<span data-ttu-id="f23b0-117">最后，若要输出按 CSV 格式 `Depth Counter` 收集的所有统计信息，可以使用以下内容：</span><span class="sxs-lookup"><span data-stu-id="f23b0-117">Finally, to output all the statistics collected by `Depth Counter` in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a><span data-ttu-id="f23b0-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f23b0-118">See also</span></span> ##

- <span data-ttu-id="f23b0-119">量程计算机[跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)概述。</span><span class="sxs-lookup"><span data-stu-id="f23b0-119">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
