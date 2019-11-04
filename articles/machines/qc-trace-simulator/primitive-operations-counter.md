---
title: 基元操作计数器 |量程计算机跟踪模拟器 |Microsoft Docs
description: 量程计算机跟踪模拟器概述
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.primitive-counter
ms.openlocfilehash: b7ec8b0d7a713051e36cb778c087050f0257710f
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2019
ms.locfileid: "73184876"
---
# <a name="primitive-operations-counter"></a><span data-ttu-id="b2056-103">基元操作计数器</span><span class="sxs-lookup"><span data-stu-id="b2056-103">Primitive Operations Counter</span></span>  

<span data-ttu-id="b2056-104">`Primitive Operations Counter` 是 "量程计算机[跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)" 的一部分。</span><span class="sxs-lookup"><span data-stu-id="b2056-104">The `Primitive Operations Counter` is a part of the quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="b2056-105">它计算在量程程序中调用的每个操作所使用的原始执行数。</span><span class="sxs-lookup"><span data-stu-id="b2056-105">It counts the number of primitive executions used by every operation invoked in a quantum program.</span></span> <span data-ttu-id="b2056-106">`Microsoft.Quantum.Primitive` 中的所有操作都以单个 qubit 旋转、T 入口、单个 qubit Clifford 入口、CNOT-CONTAINS 入口和测量为多 qubit Pauli 可观察量表示。</span><span class="sxs-lookup"><span data-stu-id="b2056-106">All operations from `Microsoft.Quantum.Primitive` are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="b2056-107">收集的统计信息在操作调用关系图的边缘上聚合。</span><span class="sxs-lookup"><span data-stu-id="b2056-107">Collected statistics are aggregated over the edges of the operations call graph.</span></span> <span data-ttu-id="b2056-108">现在，让我们计算实现 `CCNOT` 操作需要多少 `T` 入口。</span><span class="sxs-lookup"><span data-stu-id="b2056-108">Let us now count how many `T` gates are needed to implement the `CCNOT` operation.</span></span> 

```qsharp
open Microsoft.Quantum.Primitive;
operation CCNOTDriver() : Unit {

    using (qubits = Qubit[3]) {
        CCNOT(qubits[0], qubits[1], qubits[2]);
        T(qubits[0]);
    } 
}
```

## <a name="using-the-primitive-operations-counter-within-a-c-program"></a><span data-ttu-id="b2056-109">在C#程序中使用基元操作计数器</span><span class="sxs-lookup"><span data-stu-id="b2056-109">Using the Primitive Operations Counter within a C# Program</span></span>

<span data-ttu-id="b2056-110">若要检查 `CCNOT` 确实需要 7 `T` 入口，`CCNOTDriver` 执行8个 `T` 入口，我们可以使用以下C#代码：</span><span class="sxs-lookup"><span data-stu-id="b2056-110">To check that `CCNOT` indeed requires 7 `T` gates and that `CCNOTDriver` executes 8 `T` gates we can use the following C# code:</span></span>

```csharp 
// using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;
// using System.Diagnostics;
var config = new QCTraceSimulatorConfiguration();
config.usePrimitiveOperationsCounter = true;
var sim = new QCTraceSimulator(config);
var res = CCNOTDriver.Run(sim).Result;

double tCountAll = sim.GetMetric<CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
double tCount = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
```

<span data-ttu-id="b2056-111">程序的第一个部分执行 `CCNOTDriver`。</span><span class="sxs-lookup"><span data-stu-id="b2056-111">The first part of the program executes `CCNOTDriver`.</span></span> <span data-ttu-id="b2056-112">在第二部分中，我们使用方法 `QCTraceSimulator.GetMetric` 获取 `CCNOTDriver`所执行的 T 入口数：</span><span class="sxs-lookup"><span data-stu-id="b2056-112">In the second part, we use the method `QCTraceSimulator.GetMetric` to get the number of T gates executed by `CCNOTDriver`:</span></span> 

```csharp
double tCount = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
double tCountAll = sim.GetMetric<CCNOTDriver>(PrimitiveOperationsGroupsNames.T);
```

<span data-ttu-id="b2056-113">如果使用两个类型参数调用 `GetMetric`，它将返回与给定的调用图形边缘关联的度量值。</span><span class="sxs-lookup"><span data-stu-id="b2056-113">When `GetMetric` is called with two type parameters it returns the value of the metric associated with a given call graph edge.</span></span> <span data-ttu-id="b2056-114">在我们的示例操作中 `Primitive.CCNOT` 在 `CCNOTDriver` 中调用，因此调用关系图包含 `<Primitive.CCNOT,CCNOTDriver>`的边缘。</span><span class="sxs-lookup"><span data-stu-id="b2056-114">In our example operation `Primitive.CCNOT` is called within `CCNOTDriver` and therefore the call graph contains the edge `<Primitive.CCNOT,CCNOTDriver>`.</span></span> 

<span data-ttu-id="b2056-115">若要获取使用的 `CNOT` 入口数，可以添加以下行：</span><span class="sxs-lookup"><span data-stu-id="b2056-115">To get the number of `CNOT` gates used, we can add the following line:</span></span>
```csharp
double cxCount = sim.GetMetric<Primitive.CCNOT, CCNOTDriver>(PrimitiveOperationsGroupsNames.CX);
```

<span data-ttu-id="b2056-116">最后，若要输出按 CSV 格式的入口计数器收集的所有统计信息，我们可以使用以下内容：</span><span class="sxs-lookup"><span data-stu-id="b2056-116">Finally, to output all the statistics collected by the gate counter in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.primitiveOperationsCounter];
```

## <a name="see-also"></a><span data-ttu-id="b2056-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b2056-117">See also</span></span> ##

- <span data-ttu-id="b2056-118">量程计算机[跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)概述。</span><span class="sxs-lookup"><span data-stu-id="b2056-118">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
