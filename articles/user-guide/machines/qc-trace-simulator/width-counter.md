---
title: Width 计数器
description: 了解 Microsoft QDK Width 计数器，该计数器计算量程程序中每个操作所分配和借用的 qubits 数量。
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.width-counter
ms.openlocfilehash: a76292222950310acc90dded02980e4a5b792e76
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274393"
---
# <a name="width-counter"></a><span data-ttu-id="03483-103">Width 计数器</span><span class="sxs-lookup"><span data-stu-id="03483-103">Width Counter</span></span>

<span data-ttu-id="03483-104">`Width Counter`计算每个操作分配和借用的 qubits 的数目。</span><span class="sxs-lookup"><span data-stu-id="03483-104">The `Width Counter` counts the number of qubits allocated and borrowed by each operation.</span></span>
<span data-ttu-id="03483-105">来自命名空间的所有操作 `Microsoft.Quantum.Intrinsic` 都以单个 qubit 旋转、T 入口、单个 Qubit Clifford 门、cnot-contains 入口和度量标准表示。</span><span class="sxs-lookup"><span data-stu-id="03483-105">All operations from the `Microsoft.Quantum.Intrinsic` namespace are expressed in terms of single qubit rotations, T gates, single qubit Clifford gates, CNOT gates and measurements of multi-qubit Pauli observables.</span></span> <span data-ttu-id="03483-106">一些基元操作可以分配额外的 qubits。</span><span class="sxs-lookup"><span data-stu-id="03483-106">Some of the primitive operations can allocate extra qubits.</span></span> <span data-ttu-id="03483-107">例如，将控制的 `X` 入口或控制的 `T` 入口相乘。</span><span class="sxs-lookup"><span data-stu-id="03483-107">For example, multiply controlled `X` gates or controlled `T` gates.</span></span> <span data-ttu-id="03483-108">让我们计算由多次控制的门的实现所分配的额外 qubits 数 `X` ：</span><span class="sxs-lookup"><span data-stu-id="03483-108">Let us compute the number of extra qubits allocated by the implementation of a multiply controlled `X` gate:</span></span>

```qsharp
open Microsoft.Quantum.Intrinsic;
open Microsoft.Quantum.Arrays;
operation ApplyMultiControlledX( numberOfQubits : Int ) : Unit {
    using(qubits = Qubit[numberOfQubits]) {
        Controlled X (Rest(qubits), Head(qubits));
    } 
}
```

## <a name="using-width-counter-within-a-c-program"></a><span data-ttu-id="03483-109">在 c # 程序中使用 Width 计数器</span><span class="sxs-lookup"><span data-stu-id="03483-109">Using Width Counter within a C# Program</span></span>

<span data-ttu-id="03483-110">多次控制 `X` 对总计 5 qubits 的操作将分配2个辅助 qubits，其输入宽度将为5。</span><span class="sxs-lookup"><span data-stu-id="03483-110">Multiply controlled `X` acting on a total of 5 qubits will allocate 2 ancillary qubits and its input width will be 5.</span></span> <span data-ttu-id="03483-111">若要检查是否是这种情况，可以使用以下 c # 程序：</span><span class="sxs-lookup"><span data-stu-id="03483-111">To check that this is the case, we can use the following C# program:</span></span>

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

<span data-ttu-id="03483-112">程序的第一部分执行 `ApplyMultiControlledX` 。</span><span class="sxs-lookup"><span data-stu-id="03483-112">The first part of the program executes `ApplyMultiControlledX`.</span></span> <span data-ttu-id="03483-113">在第二部分中，我们使用方法 `QCTraceSimulator.GetMetric` 来获取分配的 qubits 数，以及受控接收的 qubits 数 `X` 。</span><span class="sxs-lookup"><span data-stu-id="03483-113">In the second part we use the method `QCTraceSimulator.GetMetric` to get the number of allocated qubits as well as the number of qubits that Controlled `X` received as input.</span></span> 

<span data-ttu-id="03483-114">最后，若要以 CSV 格式输出 width 计数器收集的所有统计信息，我们可以使用以下内容：</span><span class="sxs-lookup"><span data-stu-id="03483-114">Finally, to output all the statistics collected by width counter in CSV format we can use the following:</span></span>
```csharp
string csvSummary = sim.ToCSV()[MetricsCountersNames.widthCounter];
```

## <a name="see-also"></a><span data-ttu-id="03483-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="03483-115">See also</span></span> ##

- <span data-ttu-id="03483-116">量程计算机[跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)概述。</span><span class="sxs-lookup"><span data-stu-id="03483-116">The quantum computer [Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) overview.</span></span>
