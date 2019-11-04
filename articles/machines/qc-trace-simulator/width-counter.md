---
title: Width 计数器 |量程计算机跟踪模拟器 |Microsoft Docs
description: 量子计算机跟踪模拟器的概述
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: ae0c0ec2e677be03dc8dc1497dc62ad9034295a4
ms.sourcegitcommit: aa5e6f4a2deb4271a333d3f1b1eb69b5bb9a7bad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2019
ms.locfileid: "73442407"
---
# <a name="width-counter"></a><span data-ttu-id="d8649-103">Width 计数器</span><span class="sxs-lookup"><span data-stu-id="d8649-103">Width Counter</span></span>

<span data-ttu-id="d8649-104">`Width Counter` 计算每个操作分配和借用的 qubits 的数目。</span><span class="sxs-lookup"><span data-stu-id="d8649-104">The `Width Counter` counts the number of qubits allocated and borrowed by each operation.</span></span>
<span data-ttu-id="d8649-105">`Microsoft.Quantum.Primitive` 命名空间中的所有操作都以单个 qubit 旋转、T 入口、单个 qubit Clifford 门、CNOT-CONTAINS 关口和多 qubit Pauli 可观察量度量来表示。</span><span class="sxs-lookup"><span data-stu-id="d8649-105">All operations from the `Microsoft.Quantum.Primitive` namespace are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="d8649-106">一些基元操作可以分配额外的 qubits。</span><span class="sxs-lookup"><span data-stu-id="d8649-106">Some of the primitive operations can allocate extra qubits.</span></span> <span data-ttu-id="d8649-107">例如，将受控 `X` 入口或受控 `T` 入口。</span><span class="sxs-lookup"><span data-stu-id="d8649-107">For example, multiply controlled `X` gates or controlled `T` gates.</span></span> <span data-ttu-id="d8649-108">让我们计算 qubits `X` 控制的分配的额外数：</span><span class="sxs-lookup"><span data-stu-id="d8649-108">Let us compute the number of extra qubits allocated by the implementation of a multiply controlled `X` gate:</span></span>

```qsharp
open Microsoft.Quantum.Primitive;
open Microsoft.Quantum.Arrays;
operation MultiControlledXDriver( numberOfQubits : Int ) : Unit {

    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

## <a name="using-width-counter-within-a-c-program"></a><span data-ttu-id="d8649-109">在C#程序中使用 Width 计数器</span><span class="sxs-lookup"><span data-stu-id="d8649-109">Using Width Counter within a C# Program</span></span>

<span data-ttu-id="d8649-110">将受控 `X` 作用于总共5个 qubits 将分配2个辅助 qubits，其输入宽度将为5。</span><span class="sxs-lookup"><span data-stu-id="d8649-110">Multiply controlled `X` acting on a total of 5 qubits will allocate 2 ancillary qubits and its input width will be 5.</span></span> <span data-ttu-id="d8649-111">若要检查是否是这种情况，可以使用以下C#程序：</span><span class="sxs-lookup"><span data-stu-id="d8649-111">To check that this is the case, we can use the following C# program:</span></span>

```csharp 
var config = new QCTraceSimulatorConfiguration();
config.useWidthCounter = true;
var sim = new QCTraceSimulator(config);
int totalNumberOfQubits = 5;
var res = MultiControlledXDriver.Run(sim, totalNumberOfQubits).Result;

double allocatedQubits = 
    sim.GetMetric<Primitive.X, MultiControlledXDriver>(
        WidthCounter.Metrics.ExtraWidth,
        functor: OperationFunctor.Controlled); 

double inputWidth =
    sim.GetMetric<Primitive.X, MultiControlledXDriver>(
        WidthCounter.Metrics.InputWidth,
        functor: OperationFunctor.Controlled);
```

<span data-ttu-id="d8649-112">程序的第一个部分执行 `MultiControlledXDriver`。</span><span class="sxs-lookup"><span data-stu-id="d8649-112">The first part of the program executes `MultiControlledXDriver`.</span></span> <span data-ttu-id="d8649-113">在第二部分中，我们使用方法 `QCTraceSimulator.GetMetric` 获取分配的 qubits 数，以及受控 `X` 接收为输入的 qubits 数。</span><span class="sxs-lookup"><span data-stu-id="d8649-113">In the second part we use the method `QCTraceSimulator.GetMetric` to get the number of allocated qubits as well as the number of qubits that Controlled `X` received as input.</span></span> 

<span data-ttu-id="d8649-114">最后，若要以 CSV 格式输出 width 计数器收集的所有统计信息，我们可以使用以下内容：</span><span class="sxs-lookup"><span data-stu-id="d8649-114">Finally, to output all the statistics collected by width counter in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a><span data-ttu-id="d8649-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d8649-115">See also</span></span> ##

- <span data-ttu-id="d8649-116">量程计算机[跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)概述。</span><span class="sxs-lookup"><span data-stu-id="d8649-116">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
