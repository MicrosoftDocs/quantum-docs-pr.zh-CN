---
title: Width 计数器 |量程计算机跟踪模拟器 |Microsoft Docs
description: 量子计算机跟踪模拟器的概述
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: 9c3601e74eec17bd6b463e90f8f3085c959d6f95
ms.sourcegitcommit: f8d6d32d16c3e758046337fb4b16a8c42fb04c39
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "76820362"
---
# <a name="width-counter"></a><span data-ttu-id="44327-103">Width 计数器</span><span class="sxs-lookup"><span data-stu-id="44327-103">Width Counter</span></span>

<span data-ttu-id="44327-104">`Width Counter` 计算每个操作分配和借用的 qubits 的数目。</span><span class="sxs-lookup"><span data-stu-id="44327-104">The `Width Counter` counts the number of qubits allocated and borrowed by each operation.</span></span>
<span data-ttu-id="44327-105">`Microsoft.Quantum.Intrinsic` 命名空间中的所有操作都以单个 qubit 旋转、T 入口、单个 qubit Clifford 门、CNOT-CONTAINS 关口和多 qubit Pauli 可观察量度量来表示。</span><span class="sxs-lookup"><span data-stu-id="44327-105">All operations from the `Microsoft.Quantum.Intrinsic` namespace are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="44327-106">一些基元操作可以分配额外的 qubits。</span><span class="sxs-lookup"><span data-stu-id="44327-106">Some of the primitive operations can allocate extra qubits.</span></span> <span data-ttu-id="44327-107">例如，将受控 `X` 入口或受控 `T` 入口。</span><span class="sxs-lookup"><span data-stu-id="44327-107">For example, multiply controlled `X` gates or controlled `T` gates.</span></span> <span data-ttu-id="44327-108">让我们计算 qubits `X` 控制的分配的额外数：</span><span class="sxs-lookup"><span data-stu-id="44327-108">Let us compute the number of extra qubits allocated by the implementation of a multiply controlled `X` gate:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

## <a name="using-width-counter-within-a-c-program"></a><span data-ttu-id="44327-109">在C#程序中使用 Width 计数器</span><span class="sxs-lookup"><span data-stu-id="44327-109">Using Width Counter within a C# Program</span></span>

<span data-ttu-id="44327-110">将受控 `X` 作用于总共5个 qubits 将分配2个辅助 qubits，其输入宽度将为5。</span><span class="sxs-lookup"><span data-stu-id="44327-110">Multiply controlled `X` acting on a total of 5 qubits will allocate 2 ancillary qubits and its input width will be 5.</span></span> <span data-ttu-id="44327-111">若要检查是否是这种情况，可以使用以下C#程序：</span><span class="sxs-lookup"><span data-stu-id="44327-111">To check that this is the case, we can use the following C# program:</span></span>

```csharp 
var config = new QCTraceSimulatorConfiguration();
config.useWidthCounter = true;
var sim = new QCTraceSimulator(config);
int totalNumberOfQubits = 5;
var res = ApplyMultiControlledX.Run(sim, totalNumberOfQubits).Result;

double allocatedQubits = 
    sim.GetMetric<Primitive.X, ApplyMultiControlledX>(
        WidthCounter.Metrics.ExtraWidth,
        functor: OperationFunctor.Controlled); 

double inputWidth =
    sim.GetMetric<Primitive.X, ApplyMultiControlledX>(
        WidthCounter.Metrics.InputWidth,
        functor: OperationFunctor.Controlled);
```

<span data-ttu-id="44327-112">程序的第一个部分执行 `ApplyMultiControlledX`。</span><span class="sxs-lookup"><span data-stu-id="44327-112">The first part of the program executes `ApplyMultiControlledX`.</span></span> <span data-ttu-id="44327-113">在第二部分中，我们使用方法 `QCTraceSimulator.GetMetric` 获取分配的 qubits 数，以及受控 `X` 接收为输入的 qubits 数。</span><span class="sxs-lookup"><span data-stu-id="44327-113">In the second part we use the method `QCTraceSimulator.GetMetric` to get the number of allocated qubits as well as the number of qubits that Controlled `X` received as input.</span></span> 

<span data-ttu-id="44327-114">最后，若要以 CSV 格式输出 width 计数器收集的所有统计信息，我们可以使用以下内容：</span><span class="sxs-lookup"><span data-stu-id="44327-114">Finally, to output all the statistics collected by width counter in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a><span data-ttu-id="44327-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="44327-115">See also</span></span> ##

- <span data-ttu-id="44327-116">量程计算机[跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)概述。</span><span class="sxs-lookup"><span data-stu-id="44327-116">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
