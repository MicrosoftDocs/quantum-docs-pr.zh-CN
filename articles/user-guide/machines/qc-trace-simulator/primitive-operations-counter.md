---
title: 基元操作计数器-量程开发工具包
description: '了解 Microsoft QDK 基元操作计数器，该计数器使用量程跟踪模拟器跟踪程序中操作所使用的基元进程 :::no-loc(Q#)::: 。'
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
no-loc:
- ':::no-loc(Q#):::'
- ':::no-loc($$v):::'
ms.openlocfilehash: bf75eb94696a489a587316928bc3f33baa4a1785
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92690959"
---
# <a name="quantum-trace-simulator-primitive-operations-counter"></a><span data-ttu-id="9deb4-103">量程跟踪模拟器：基元操作计数器</span><span class="sxs-lookup"><span data-stu-id="9deb4-103">Quantum trace simulator: primitive operations counter</span></span>

<span data-ttu-id="9deb4-104">基元操作计数器是量程开发工具包 [量程跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)的一部分。</span><span class="sxs-lookup"><span data-stu-id="9deb4-104">The primitive operation counter is a part of the Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="9deb4-105">它计算在量程程序中调用的每个操作所使用的基元进程的数目。</span><span class="sxs-lookup"><span data-stu-id="9deb4-105">It counts the number of primitive processes used by every operation invoked in a quantum program.</span></span> 

<span data-ttu-id="9deb4-106">所有 <xref:Microsoft.Quantum.Intrinsic> 操作都以单 qubit 循环、T 操作、Qubit Clifford 操作、cnot-contains 操作和多 Qubit Pauli 可观察量的度量来表示。</span><span class="sxs-lookup"><span data-stu-id="9deb4-106">All <xref:Microsoft.Quantum.Intrinsic> operations are expressed in terms of single-qubit rotations, T operations, single-qubit Clifford operations, CNOT operations, and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="9deb4-107">基元操作计数器聚合并收集操作的 [调用关系图](https://en.wikipedia.org/wiki/Call_graph)边缘的统计信息。</span><span class="sxs-lookup"><span data-stu-id="9deb4-107">The Primitive Operations Counter aggregates and collects statistics over all the edges of the operation's [call graph](https://en.wikipedia.org/wiki/Call_graph).</span></span>

## <a name="invoking-the-primitive-operation-counter"></a><span data-ttu-id="9deb4-108">调用基元操作计数器</span><span class="sxs-lookup"><span data-stu-id="9deb4-108">Invoking the primitive operation counter</span></span>

<span data-ttu-id="9deb4-109">若要使用基元操作计数器运行量程跟踪模拟器，您必须创建一个 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> 实例，将属性设置 `UsePrimitiveOperationsCounter` 为 **true** ，然后 <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> 使用作为参数创建新的实例 `QCTraceSimulatorConfiguration` 。</span><span class="sxs-lookup"><span data-stu-id="9deb4-109">To run the quantum trace simulator with the primitive operation counter, you must create a <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> instance, set the `UsePrimitiveOperationsCounter` property to **true** , and then create a new <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> instance with the `QCTraceSimulatorConfiguration` as the parameter.</span></span>

```csharp
var config = new QCTraceSimulatorConfiguration();
config.UsePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
```

## <a name="using-the-primitive-operation-counter-in-a-c-host-program"></a><span data-ttu-id="9deb4-110">在 c # 宿主程序中使用基元操作计数器</span><span class="sxs-lookup"><span data-stu-id="9deb4-110">Using the primitive operation counter in a C# host program</span></span>

<span data-ttu-id="9deb4-111">本部分中的 c # 示例将根据 <xref:Microsoft.Quantum.Intrinsic.T> <xref:Microsoft.Quantum.Intrinsic.ccnot> 下面的示例代码，计算实现该操作所需的操作数 :::no-loc(Q#)::: ：</span><span class="sxs-lookup"><span data-stu-id="9deb4-111">The C# example that follows in this section counts how many <xref:Microsoft.Quantum.Intrinsic.T> operations are needed to implement the <xref:Microsoft.Quantum.Intrinsic.ccnot> operation, based on the following :::no-loc(Q#)::: sample code:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;
operation ApplySampleWithCCNOT() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    }
}
```

<span data-ttu-id="9deb4-112">若要检查是否 `CCNOT` 需要七个 `T` 操作并 `ApplySampleWithCCNOT` 运行8个 `T` 操作，请使用以下 c # 代码：</span><span class="sxs-lookup"><span data-stu-id="9deb4-112">To check that `CCNOT` requires seven `T` operations and that `ApplySampleWithCCNOT` runs eight `T` operations, use the following C# code:</span></span>

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.UsePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = ApplySampleWithCCNOT.Run(sim).Result;

double tCountAll = sim.GetMetric<ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.T);
```

<span data-ttu-id="9deb4-113">程序的第一部分将运行 `ApplySampleWithCCNOT` 。</span><span class="sxs-lookup"><span data-stu-id="9deb4-113">The first part of the program runs `ApplySampleWithCCNOT`.</span></span> <span data-ttu-id="9deb4-114">第二部分使用 [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) 方法检索运行的操作的数目 `T` `ApplySampleWithCCNOT` ：</span><span class="sxs-lookup"><span data-stu-id="9deb4-114">The second part uses the [`QCTraceSimulator.GetMetric`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) method to retrieve the number of `T` operations run by `ApplySampleWithCCNOT`:</span></span> 

<span data-ttu-id="9deb4-115">`GetMetric`使用两个类型参数调用时，它将返回与给定的调用图形边缘关联的度量值。</span><span class="sxs-lookup"><span data-stu-id="9deb4-115">When you call `GetMetric` with two type parameters, it returns the value of the metric associated with a given call graph edge.</span></span> <span data-ttu-id="9deb4-116">在前面的示例中，程序在 `Primitive.CCNOT` 中调用操作 `ApplySampleWithCCNOT` ，因此调用关系图包含边缘 `<Primitive.CCNOT, ApplySampleWithCCNOT>` 。</span><span class="sxs-lookup"><span data-stu-id="9deb4-116">In the preceding example, the program calls the `Primitive.CCNOT` operation  within `ApplySampleWithCCNOT` and therefore the call graph contains the edge `<Primitive.CCNOT, ApplySampleWithCCNOT>`.</span></span> 

<span data-ttu-id="9deb4-117">若要检索使用的 `CNOT` 操作数，请添加以下行：</span><span class="sxs-lookup"><span data-stu-id="9deb4-117">To retrieve the number of `CNOT` operations used, add the following line:</span></span>
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, ApplySampleWithCCNOT>(PrimitiveOperationsGroupsNames.CX);
```

<span data-ttu-id="9deb4-118">最后，你可以使用以下方法输出使用 CSV 格式的基元操作计数器收集的所有统计信息：</span><span class="sxs-lookup"><span data-stu-id="9deb4-118">Finally, you can output all the statistics collected by the Primitive Operations Counter in CSV format using the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a><span data-ttu-id="9deb4-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9deb4-119">See also</span></span>

- <span data-ttu-id="9deb4-120">量程开发工具包 [量程跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro) 概述。</span><span class="sxs-lookup"><span data-stu-id="9deb4-120">The Quantum Development Kit [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
- <span data-ttu-id="9deb4-121"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator>API 参考。</span><span class="sxs-lookup"><span data-stu-id="9deb4-121">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> API reference.</span></span>
- <span data-ttu-id="9deb4-122"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration>API 参考。</span><span class="sxs-lookup"><span data-stu-id="9deb4-122">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration> API reference.</span></span>
- <span data-ttu-id="9deb4-123"><xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.PrimitiveOperationsGroupsNames>API 参考。</span><span class="sxs-lookup"><span data-stu-id="9deb4-123">The <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.PrimitiveOperationsGroupsNames> API reference.</span></span>