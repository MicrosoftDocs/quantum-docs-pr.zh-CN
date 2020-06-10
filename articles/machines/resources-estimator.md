---
title: 量程开发工具包资源估计器
description: '了解资源估计器，这些资源估计在量程计算机上运行 Q # 操作的给定实例所需的资源。'
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 1/22/2019
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
ms.openlocfilehash: b0c800c3946d2e4ba4457127fb9495dc9dcf2934
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630137"
---
# <a name="the-resources-estimator-target-machine"></a><span data-ttu-id="42e2f-103">资源估计器目标计算机</span><span class="sxs-lookup"><span data-stu-id="42e2f-103">The Resources Estimator Target Machine</span></span>

<span data-ttu-id="42e2f-104">顾名思义， `ResourcesEstimator` 估计在量程计算机上运行 Q # 操作的给定实例所需的资源。</span><span class="sxs-lookup"><span data-stu-id="42e2f-104">As the name implies, the `ResourcesEstimator` estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span>
<span data-ttu-id="42e2f-105">它通过执行量程操作来实现此操作，而无需实际模拟量子计算机的状态;出于此原因，如果代码的传统部分可以在合理的时间内运行，则它可以估计使用上千个 qubits 的 Q # 操作的资源。</span><span class="sxs-lookup"><span data-stu-id="42e2f-105">It accomplishes this by executing the quantum operation without actually simulating the state of a quantum computer; for this reason, it can estimate resources for Q# operations that use thousands of qubits, if the classical part of the code can be run in a reasonable time.</span></span>

## <a name="usage"></a><span data-ttu-id="42e2f-106">使用情况</span><span class="sxs-lookup"><span data-stu-id="42e2f-106">Usage</span></span>

<span data-ttu-id="42e2f-107">`ResourcesEstimator`只是另一种类型的目标计算机，因此它可用于运行任何 Q # 操作。</span><span class="sxs-lookup"><span data-stu-id="42e2f-107">The `ResourcesEstimator` is just another type of target machine, thus it can be used to run any Q# operation.</span></span> 

<span data-ttu-id="42e2f-108">作为其他目标计算机，若要在 c # 主机程序上使用该实例，请创建一个实例，并将其作为该操作方法的第一个参数进行传递 `Run` ：</span><span class="sxs-lookup"><span data-stu-id="42e2f-108">As other target machines, to use it on a C# host program create an instance and pass it as the first parameter of the operation's `Run` method:</span></span>

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            ResourcesEstimator estimator = new ResourcesEstimator();
            MyQuantumProgram.Run(estimator).Wait();
            Console.WriteLine(estimator.ToTSV());
        }
    }
}
```

<span data-ttu-id="42e2f-109">如示例所示， `ResourcesEstimator` 提供了一个 `ToTSV()` 方法，该方法生成一个包含制表符分隔值（TSV）的表，该表可以保存到文件中或写入控制台进行分析。</span><span class="sxs-lookup"><span data-stu-id="42e2f-109">As the example shows, the `ResourcesEstimator` provides a `ToTSV()` method to generate a table with tab-separated-values (TSV) that can be saved into a file or written to the console for analysis.</span></span> <span data-ttu-id="42e2f-110">上述程序的输出应如下所示：</span><span class="sxs-lookup"><span data-stu-id="42e2f-110">The output of the above program should look something like this:</span></span>

```Output
Metric          Sum
CNOT            1000
QubitClifford   1000
R               0
Measure         4002
T               0
Depth           0
Width           2
BorrowedWidth   0
```

> [!NOTE]
> <span data-ttu-id="42e2f-111">`ResourcesEstimator`不会在每次运行时重置其计算，如果使用同一个实例执行其他操作，它将使聚合计数保持在现有结果的顶部。</span><span class="sxs-lookup"><span data-stu-id="42e2f-111">The `ResourcesEstimator` does not reset its calculations on every run, if the same instance is used to execute another operation it will keep aggregating counts on top of existing results.</span></span>
> <span data-ttu-id="42e2f-112">如果需要在运行之间重置计算，则为每次执行创建一个新的实例。</span><span class="sxs-lookup"><span data-stu-id="42e2f-112">If you need to reset calculations between runs, create a new instance for every execution.</span></span>


## <a name="programmatically-retrieving-the-estimated-data"></a><span data-ttu-id="42e2f-113">以编程方式检索估计的数据</span><span class="sxs-lookup"><span data-stu-id="42e2f-113">Programmatically Retrieving the Estimated Data</span></span>

<span data-ttu-id="42e2f-114">除了 TSV 表之外，还可以通过的属性以编程方式检索资源估算 `ResourcesEstimator` `Data` 。</span><span class="sxs-lookup"><span data-stu-id="42e2f-114">In addition to a TSV table, the resources estimated can be retrieved programmatically via the `ResourcesEstimator`'s `Data` property.</span></span> <span data-ttu-id="42e2f-115">`Data`提供一个 `System.DataTable` 具有两列的实例： `Metric` 和 `Sum` ，并按指标名称进行索引。</span><span class="sxs-lookup"><span data-stu-id="42e2f-115">`Data` provides a `System.DataTable` instance with two columns: `Metric` and `Sum`, indexed by the metrics names.</span></span>

<span data-ttu-id="42e2f-116">下面的代码演示如何检索和打印 `QubitClifford` `T` `CNOT` Q # 操作使用的和入口总数：</span><span class="sxs-lookup"><span data-stu-id="42e2f-116">The following code shows how to retrieve and print the total number of `QubitClifford`, `T` and `CNOT` gates used by a Q# operation:</span></span>

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            ResourcesEstimator estimator = new ResourcesEstimator();
            MyQuantumProgram.Run(estimator).Wait();

            var data = estimator.Data;
            Console.WriteLine($"QubitCliffords: {data.Rows.Find("QubitClifford")["Sum"]}");
            Console.WriteLine($"Ts: {data.Rows.Find("T")["Sum"]}");
            Console.WriteLine($"CNOTs: {data.Rows.Find("CNOT")["Sum"]}");
        }
    }
}
```

## <a name="metrics-reported"></a><span data-ttu-id="42e2f-117">报告的指标</span><span class="sxs-lookup"><span data-stu-id="42e2f-117">Metrics Reported</span></span>

<span data-ttu-id="42e2f-118">下面是估计的指标列表 `ResourcesEstimator` ：</span><span class="sxs-lookup"><span data-stu-id="42e2f-118">The following is the list of metrics estimated by the `ResourcesEstimator`:</span></span>

* <span data-ttu-id="42e2f-119">__Cnot-contains__：已执行的 cnot-contains （也称为受控 Pauli X 入口）入口的计数。</span><span class="sxs-lookup"><span data-stu-id="42e2f-119">__CNOT__: The count of CNOT (also known as the Controlled Pauli X gate) gates executed.</span></span>
* <span data-ttu-id="42e2f-120">__QubitClifford__：执行的任何单个 qubit Clifford 和 Pauli 入口的计数。</span><span class="sxs-lookup"><span data-stu-id="42e2f-120">__QubitClifford__: The count of any single qubit Clifford and Pauli gates executed.</span></span>
* <span data-ttu-id="42e2f-121">__度量值__：执行的任何度量值的计数。</span><span class="sxs-lookup"><span data-stu-id="42e2f-121">__Measure__:  The count of any measurements executed.</span></span>
* <span data-ttu-id="42e2f-122">__R__：执行的任何单个 qubit 循环的计数，不包括 T、Clifford 和 Pauli 入口。</span><span class="sxs-lookup"><span data-stu-id="42e2f-122">__R__: The count of any single qubit rotations executed, excluding T, Clifford and Pauli gates.</span></span>
* <span data-ttu-id="42e2f-123">__T__： t 入口及其词干的计数（包括 t 入口、T_x = 1xt-hy-ubw）和 T_y = 1xt-hy-ubw，已执行。</span><span class="sxs-lookup"><span data-stu-id="42e2f-123">__T__: The count of T gates and their conjugates, including the T gate, T_x = H.T.H, and T_y = Hy.T.Hy, executed.</span></span>
* <span data-ttu-id="42e2f-124">__深度__：由 Q # 操作执行的量程线路的深度。</span><span class="sxs-lookup"><span data-stu-id="42e2f-124">__Depth__: Depth of the quantum circuit executed by the Q# operation.</span></span> <span data-ttu-id="42e2f-125">默认情况下，在深度中只对 T 个入口计数，有关详细信息，请参阅[深度计数器](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)。</span><span class="sxs-lookup"><span data-stu-id="42e2f-125">By default, only T gates are counted in the depth, see [depth counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter) for details.</span></span>
* <span data-ttu-id="42e2f-126">__Width__：在执行 Q # 操作期间分配的最大 qubits 数。</span><span class="sxs-lookup"><span data-stu-id="42e2f-126">__Width__: Maximum number of qubits allocated during the execution of the Q# operation.</span></span>
* <span data-ttu-id="42e2f-127">__BorrowedWidth__： Q # 操作内借用的最大 qubits 数。</span><span class="sxs-lookup"><span data-stu-id="42e2f-127">__BorrowedWidth__: Maximum number of qubits borrowed inside the Q# operation.</span></span>


## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="42e2f-128">提供度量结果的概率</span><span class="sxs-lookup"><span data-stu-id="42e2f-128">Providing the Probability of Measurement Outcomes</span></span>

<span data-ttu-id="42e2f-129"><xref:microsoft.quantum.intrinsic.assertprob><xref:microsoft.quantum.intrinsic>可以使用命名空间中的信息来提供有关测量结果的信息，以帮助推动 Q # 计划的执行。</span><span class="sxs-lookup"><span data-stu-id="42e2f-129"><xref:microsoft.quantum.intrinsic.assertprob> from the <xref:microsoft.quantum.intrinsic> namespace can be used to provide information about the expected probability of a measurement to help drive the execution of the Q# program.</span></span> <span data-ttu-id="42e2f-130">以下示例对此进行了说明：</span><span class="sxs-lookup"><span data-stu-id="42e2f-130">The following example illustrates this:</span></span>

```qsharp
operation Teleport(source : Qubit, target : Qubit) : Unit {

    using (qubit = Qubit()) {

        H(q);
        CNOT(qubit, target);

        CNOT(source, qubit);
        H(source);

        AssertProb([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertProb([PauliZ], [qubit], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(qubit) == One) { X(target); X(qubit); }
    }
}
```

<span data-ttu-id="42e2f-131">当遇到此情况时， `ResourcesEstimator` `AssertProb` 它将记录对的度量， `PauliZ` `source` 并 `q` 应为其给定结果 `Zero` ，其概率为0.5。</span><span class="sxs-lookup"><span data-stu-id="42e2f-131">When the `ResourcesEstimator` encounters `AssertProb` it will record that measuring `PauliZ` on `source` and `q` should be given an outcome of `Zero` with probability 0.5.</span></span> <span data-ttu-id="42e2f-132">当它稍后执行时 `M` ，它将查找结果概率的已记录值，并 `M` 返回 `Zero` `One` 概率为0.5 的或。</span><span class="sxs-lookup"><span data-stu-id="42e2f-132">When it executes `M` later, it will find the recorded values of the outcome probabilities and `M` will return `Zero` or `One` with probability 0.5.</span></span>


## <a name="see-also"></a><span data-ttu-id="42e2f-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="42e2f-133">See also</span></span>

<span data-ttu-id="42e2f-134">在 `ResourcesEstimator` 量程计算机[跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)的基础上构建，它提供了一组更丰富的指标，可以在完整的调用关系图上报告指标，还可以使用[不同的输入检查器](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs)来帮助查找 Q # 计划中的 bug。</span><span class="sxs-lookup"><span data-stu-id="42e2f-134">The `ResourcesEstimator` is built on top of the quantum computer [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), which provides a richer set of metrics, the ability to report metrics on the full call-graph, and features like [distinct inputs checker](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) to help find bugs on Q# programs.</span></span> <span data-ttu-id="42e2f-135">有关详细信息，请参阅[跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)文档。</span><span class="sxs-lookup"><span data-stu-id="42e2f-135">Please refer to the [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro) documentation for more information.</span></span>

