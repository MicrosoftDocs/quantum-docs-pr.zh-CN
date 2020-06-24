---
title: 深度计数器
description: 了解 Microsoft QDK Depth 计数器，该计数器收集在量程程序中调用的每个操作的深度计数。
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.depth-counter
ms.openlocfilehash: d532a9f512b8c87d83d62ed26e3bb67e1b6f668b
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274401"
---
# <a name="depth-counter"></a><span data-ttu-id="a221e-103">深度计数器</span><span class="sxs-lookup"><span data-stu-id="a221e-103">Depth Counter</span></span>

<span data-ttu-id="a221e-104">`Depth Counter`是 "量程计算机[跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)" 的一部分。</span><span class="sxs-lookup"><span data-stu-id="a221e-104">The `Depth Counter` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span>
<span data-ttu-id="a221e-105">它用于收集量程程序中调用的每个操作的深度计数。</span><span class="sxs-lookup"><span data-stu-id="a221e-105">It is used to gather counts of the depth of every operation invoked in a quantum program.</span></span> <span data-ttu-id="a221e-106">中的所有操作 <xref:microsoft.quantum.intrinsic> 都以单个 qubit 旋转、T 入口、单个 Qubit Clifford 门、cnot-contains 入口和度量值表示。</span><span class="sxs-lookup"><span data-stu-id="a221e-106">All operations from <xref:microsoft.quantum.intrinsic> are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="a221e-107">用户可以通过的字段设置每个基元操作的深度 `gateTimes` <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> 。</span><span class="sxs-lookup"><span data-stu-id="a221e-107">Users can set the depth for each of the primitive operations via the `gateTimes` field of <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>.</span></span>

<span data-ttu-id="a221e-108">默认情况下，除了深度为1的 T 门外，所有操作的深度为0。</span><span class="sxs-lookup"><span data-stu-id="a221e-108">By default, all operations have depth 0 except the T gate which has depth 1.</span></span> <span data-ttu-id="a221e-109">这意味着，在默认情况下，只计算 T 操作的 T 深度（通常是必需的）。</span><span class="sxs-lookup"><span data-stu-id="a221e-109">This means that by default, only the T depth of operations is computed (which is often desirable).</span></span> <span data-ttu-id="a221e-110">收集的统计信息在操作调用关系图的所有边缘上聚合在一起。</span><span class="sxs-lookup"><span data-stu-id="a221e-110">Collected statistics are aggregated over all the edges of the operations call graph.</span></span> 

<span data-ttu-id="a221e-111">现在，让我们计算 <xref:microsoft.quantum.intrinsic.t> 操作的深度 <xref:microsoft.quantum.intrinsic.ccnot> 。</span><span class="sxs-lookup"><span data-stu-id="a221e-111">Let us now compute the <xref:microsoft.quantum.intrinsic.t> depth of the <xref:microsoft.quantum.intrinsic.ccnot> operation.</span></span> <span data-ttu-id="a221e-112">我们将使用下面的 Q # 示例代码：</span><span class="sxs-lookup"><span data-stu-id="a221e-112">We will use the following Q# sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;

operation ApplySampleWithCCNOT() : Unit {
    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

## <a name="using-depth-counter-within-a-c-program"></a><span data-ttu-id="a221e-113">在 c # 程序中使用深度计数器</span><span class="sxs-lookup"><span data-stu-id="a221e-113">Using Depth Counter within a C# Program</span></span>

<span data-ttu-id="a221e-114">若要检查 `CCNOT` 是否具有 `T` 深度5并 `ApplySampleWithCCNOT` 具有 `T` 深度6，我们可以使用以下 c # 代码：</span><span class="sxs-lookup"><span data-stu-id="a221e-114">To check that `CCNOT` has `T` depth 5 and `ApplySampleWithCCNOT` has `T` depth 6 we can use the following C# code:</span></span>

```csharp
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.useDepthCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

<span data-ttu-id="a221e-115">程序的第一部分执行 `ApplySampleWithCCNOT` 。</span><span class="sxs-lookup"><span data-stu-id="a221e-115">The first part of the program executes `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="a221e-116">在第二部分中，我们将使用方法 `QCTraceSimulator.GetMetric` 来获取 `T` 和的 `CCNOT` 深度 `ApplySampleWithCCNOT` ：</span><span class="sxs-lookup"><span data-stu-id="a221e-116">In the second part, we use the method `QCTraceSimulator.GetMetric` to get the `T` depth of `CCNOT` and `ApplySampleWithCCNOT`:</span></span> 

```csharp
double tDepth = sim.GetMetric<Intrinsic.CCNOT, ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
double tDepthAll = sim.GetMetric<ApplySampleWithCCNOT>(DepthCounter.Metrics.Depth);
```

<span data-ttu-id="a221e-117">最后，若要输出 CSV 格式收集的所有统计信息， `Depth Counter` 可以使用以下内容：</span><span class="sxs-lookup"><span data-stu-id="a221e-117">Finally, to output all the statistics collected by `Depth Counter` in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.depthCounter];
```

## <a name="see-also"></a><span data-ttu-id="a221e-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="a221e-118">See also</span></span> ##

- <span data-ttu-id="a221e-119">量程计算机[跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)概述。</span><span class="sxs-lookup"><span data-stu-id="a221e-119">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
