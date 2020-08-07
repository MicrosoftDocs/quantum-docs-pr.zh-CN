---
title: 量程资源估计器-量程开发工具包
description: 了解 Microsoft QDK resources 估计器，它估算 Q# 在量程计算机上运行某一给定操作实例所需的资源。
author: anpaz-msft
ms.author: anpaz@microsoft.com
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
no-loc:
- Q#
- $$v
ms.openlocfilehash: d5338eb740716d9d7f408703347f572688bbccb2
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868179"
---
# <a name="quantum-development-kit-qdk-resources-estimator"></a><span data-ttu-id="49ae7-103">量程开发工具包 (QDK) 资源估计器</span><span class="sxs-lookup"><span data-stu-id="49ae7-103">Quantum Development Kit (QDK) resources estimator</span></span>

<span data-ttu-id="49ae7-104">顾名思义，类会估算在 `ResourcesEstimator` 量程计算机上运行某一给定操作实例所需的资源 Q# 。</span><span class="sxs-lookup"><span data-stu-id="49ae7-104">As the name implies, the `ResourcesEstimator` class estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span> <span data-ttu-id="49ae7-105">它通过执行量程操作来实现此操作，而无需实际模拟量子计算机的状态;出于此原因，它会估算 Q# 使用上千个 qubits 的操作的资源，前提是代码的传统部分在合理的时间内运行。</span><span class="sxs-lookup"><span data-stu-id="49ae7-105">It accomplishes this by executing the quantum operation without actually simulating the state of a quantum computer; for this reason, it estimates resources for Q# operations that use thousands of qubits, provided that the classical part of the code runs in a reasonable time.</span></span>

<span data-ttu-id="49ae7-106">资源估计器是在[量程跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)的基础上构建的，它提供了一组更丰富的指标和工具来帮助调试 Q# 程序。</span><span class="sxs-lookup"><span data-stu-id="49ae7-106">The resources estimator is built on top of the [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), which provides a richer set of metrics and tools to help debug Q# programs.</span></span>

## <a name="invoking-and-running-the-resources-estimator"></a><span data-ttu-id="49ae7-107">调用和运行资源估计器</span><span class="sxs-lookup"><span data-stu-id="49ae7-107">Invoking and running the resources estimator</span></span>

<span data-ttu-id="49ae7-108">可以使用资源估计器运行任何 Q# 操作。</span><span class="sxs-lookup"><span data-stu-id="49ae7-108">You can use the resources estimator to run any Q# operation.</span></span> <span data-ttu-id="49ae7-109">有关更多详细信息，请参阅[运行 Q# 程序的方法](xref:microsoft.quantum.guide.host-programs)。</span><span class="sxs-lookup"><span data-stu-id="49ae7-109">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-resources-estimator-from-c"></a><span data-ttu-id="49ae7-110">从 C 调用资源估计器#</span><span class="sxs-lookup"><span data-stu-id="49ae7-110">Invoking the resources estimator from C#</span></span> 

<span data-ttu-id="49ae7-111">与使用其他目标计算机一样，你首先创建 `ResourceEstimator` 类的实例，然后将其作为操作的 `Run` 方法的第一个参数传递。</span><span class="sxs-lookup"><span data-stu-id="49ae7-111">As with other target machines, you first create an instance of the `ResourceEstimator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="49ae7-112">请注意，与 `QuantumSimulator` 类不同，`ResourceEstimator` 类不实现 <xref:System.IDisposable> 接口，因此不需要将其放在 `using` 语句中。</span><span class="sxs-lookup"><span data-stu-id="49ae7-112">Note that, unlike the `QuantumSimulator` class, the `ResourceEstimator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

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

<span data-ttu-id="49ae7-113">如示例所示， `ResourcesEstimator` 提供 `ToTSV()` 方法，该方法生成一个表，其中包含以制表符分隔的值 (TSV) 。</span><span class="sxs-lookup"><span data-stu-id="49ae7-113">As the example shows, `ResourcesEstimator` provides the `ToTSV()` method, which generates a table with tab-separated values (TSV).</span></span> <span data-ttu-id="49ae7-114">可以将表保存到文件或将其显示在控制台中进行分析。</span><span class="sxs-lookup"><span data-stu-id="49ae7-114">You can save the table to a file or display it to the console for analysis.</span></span> <span data-ttu-id="49ae7-115">下面是前述程序的示例输出：</span><span class="sxs-lookup"><span data-stu-id="49ae7-115">The following is a sample output from the preceding program:</span></span>

```output
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
> <span data-ttu-id="49ae7-116">`ResourcesEstimator`实例不会在每次运行时重置其计算。</span><span class="sxs-lookup"><span data-stu-id="49ae7-116">A `ResourcesEstimator` instance does not reset its calculations on every run.</span></span> <span data-ttu-id="49ae7-117">如果使用同一个实例运行另一个操作，则会将新结果与现有结果聚合在一起。</span><span class="sxs-lookup"><span data-stu-id="49ae7-117">If you use the same instance to run another operation, it aggregates the new results with the existing results.</span></span> <span data-ttu-id="49ae7-118">如果需要在运行之间重置计算，则为每次运行创建一个新的实例。</span><span class="sxs-lookup"><span data-stu-id="49ae7-118">If you need to reset calculations between runs, create a new instance for every run.</span></span>

### <a name="invoking-the-resources-estimator-from-python"></a><span data-ttu-id="49ae7-119">从 Python 调用资源估计器</span><span class="sxs-lookup"><span data-stu-id="49ae7-119">Invoking the resources estimator from Python</span></span>

<span data-ttu-id="49ae7-120">使用导入的操作在 Python 库中使用[estimate_resources ( # B1](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable)方法 Q# ：</span><span class="sxs-lookup"><span data-stu-id="49ae7-120">Use the [estimate_resources()](https://docs.microsoft.com/python/qsharp/qsharp.loader.qsharpcallable) method from the Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.estimate_resources()
```

### <a name="invoking-the-resources-estimator-from-the-command-line"></a><span data-ttu-id="49ae7-121">从命令行调用资源估计器</span><span class="sxs-lookup"><span data-stu-id="49ae7-121">Invoking the resources estimator from the command line</span></span>

<span data-ttu-id="49ae7-122">在 Q# 从命令行运行程序时，使用 **--模拟器** (或 **-s**快捷) 参数来指定 `ResourcesEstimator` 目标计算机。</span><span class="sxs-lookup"><span data-stu-id="49ae7-122">When running a Q# program from the command line, use the **--simulator** (or **-s** shortcut) parameter to specify the `ResourcesEstimator` target machine.</span></span> <span data-ttu-id="49ae7-123">以下命令使用资源估计器运行程序：</span><span class="sxs-lookup"><span data-stu-id="49ae7-123">The following command runs a program using the resources estimator:</span></span> 

```dotnetcli
dotnet run -s ResourcesEstimator
```

### <a name="invoking-the-resources-estimator-from-juptyer-notebooks"></a><span data-ttu-id="49ae7-124">从 Juptyer 笔记本调用资源估计器</span><span class="sxs-lookup"><span data-stu-id="49ae7-124">Invoking the resources estimator from Juptyer Notebooks</span></span>

<span data-ttu-id="49ae7-125">使用 I Q# 幻命令[% 估算](xref:microsoft.quantum.iqsharp.magic-ref.simulate)来运行 Q# 操作。</span><span class="sxs-lookup"><span data-stu-id="49ae7-125">Use the IQ# magic command [%estimate](xref:microsoft.quantum.iqsharp.magic-ref.simulate) to run the Q# operation.</span></span>

```
%estimate myOperation
```

## <a name="programmatically-retrieving-the-estimated-data"></a><span data-ttu-id="49ae7-126">以编程方式检索估计的数据</span><span class="sxs-lookup"><span data-stu-id="49ae7-126">Programmatically retrieving the estimated data</span></span>

<span data-ttu-id="49ae7-127">除了 TSV 表之外，还可以通过资源估计器的属性以编程方式检索在运行期间估计的资源 `Data` 。</span><span class="sxs-lookup"><span data-stu-id="49ae7-127">In addition to a TSV table, you can programmatically retrieve the resources estimated during the run via the `Data` property of the resources estimator.</span></span> <span data-ttu-id="49ae7-128">`Data`属性提供一个 `System.DataTable` 具有两列的实例： `Metric` 和 `Sum` ，并按指标的名称编制索引。</span><span class="sxs-lookup"><span data-stu-id="49ae7-128">The `Data` property provides a `System.DataTable` instance with two columns: `Metric` and `Sum`, indexed by the metrics' names.</span></span>

<span data-ttu-id="49ae7-129">下面的代码演示如何检索和打印操作所使用的的 `QubitClifford` 总数 `T` 和 `CNOT` 操作 Q# ：</span><span class="sxs-lookup"><span data-stu-id="49ae7-129">The following code shows how to retrieve and print the total number of `QubitClifford`, `T` and `CNOT` operations used by a Q# operation:</span></span>

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

## <a name="metrics-reported"></a><span data-ttu-id="49ae7-130">报告的指标</span><span class="sxs-lookup"><span data-stu-id="49ae7-130">Metrics Reported</span></span>

<span data-ttu-id="49ae7-131">资源估计器跟踪以下度量值：</span><span class="sxs-lookup"><span data-stu-id="49ae7-131">The resources estimator tracks the following metrics:</span></span>

|<span data-ttu-id="49ae7-132">指标</span><span class="sxs-lookup"><span data-stu-id="49ae7-132">Metric</span></span>|<span data-ttu-id="49ae7-133">描述</span><span class="sxs-lookup"><span data-stu-id="49ae7-133">Description</span></span>|
|----|----|
|<span data-ttu-id="49ae7-134">__CNOT__</span><span class="sxs-lookup"><span data-stu-id="49ae7-134">__CNOT__</span></span>    |<span data-ttu-id="49ae7-135">操作的运行计数 `CNOT` (也称为受控 Pauli X 操作) 。</span><span class="sxs-lookup"><span data-stu-id="49ae7-135">The run count of `CNOT` operations (also known as Controlled Pauli X operations).</span></span>|
|<span data-ttu-id="49ae7-136">__QubitClifford__</span><span class="sxs-lookup"><span data-stu-id="49ae7-136">__QubitClifford__</span></span> |<span data-ttu-id="49ae7-137">任何单个 qubit Clifford 和 Pauli 操作的运行计数。</span><span class="sxs-lookup"><span data-stu-id="49ae7-137">The run count of any single qubit Clifford and Pauli operations.</span></span>|
|<span data-ttu-id="49ae7-138">度量 </span><span class="sxs-lookup"><span data-stu-id="49ae7-138">__Measure__</span></span>    |<span data-ttu-id="49ae7-139">任何度量值的运行计数。</span><span class="sxs-lookup"><span data-stu-id="49ae7-139">The run count of any measurements.</span></span>  |
|<span data-ttu-id="49ae7-140">__R__</span><span class="sxs-lookup"><span data-stu-id="49ae7-140">__R__</span></span>    |<span data-ttu-id="49ae7-141">任何单 qubit 循环、不包括 `T` 、Clifford 和 Pauli 操作的运行计数。</span><span class="sxs-lookup"><span data-stu-id="49ae7-141">The run count of any single-qubit rotations, excluding `T`, Clifford and Pauli operations.</span></span>  |
|<span data-ttu-id="49ae7-142">__T__</span><span class="sxs-lookup"><span data-stu-id="49ae7-142">__T__</span></span>    |<span data-ttu-id="49ae7-143">操作的运行计数 `T` 及其词干，包括 `T` 操作、T_x = 1xt-hy-ubw 和 T_y = 1Xt-hy-ubw。。</span><span class="sxs-lookup"><span data-stu-id="49ae7-143">The run count of `T` operations and their conjugates, including the `T` operations, T_x = H.T.H, and T_y = Hy.T.Hy.</span></span>  |
|<span data-ttu-id="49ae7-144">__Depth__</span><span class="sxs-lookup"><span data-stu-id="49ae7-144">__Depth__</span></span>|<span data-ttu-id="49ae7-145">该操作运行的量程线路深度的下限 Q# 。</span><span class="sxs-lookup"><span data-stu-id="49ae7-145">The lower bound for the depth of the quantum circuit run by the Q# operation.</span></span> <span data-ttu-id="49ae7-146">默认情况下，深度指标仅计算 `T` 入口。</span><span class="sxs-lookup"><span data-stu-id="49ae7-146">By default, the depth metric only counts `T` gates.</span></span> <span data-ttu-id="49ae7-147">有关更多详细信息，请参阅[深度计数器](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)。</span><span class="sxs-lookup"><span data-stu-id="49ae7-147">For more details, see [Depth Counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span></span>   |
|<span data-ttu-id="49ae7-148">Width</span><span class="sxs-lookup"><span data-stu-id="49ae7-148">__Width__</span></span>    |<span data-ttu-id="49ae7-149">运行操作期间分配的最大 qubits 数的下限 Q# 。</span><span class="sxs-lookup"><span data-stu-id="49ae7-149">The lower bound for the maximum number of qubits allocated during the run of the Q# operation.</span></span> <span data-ttu-id="49ae7-150">可能无法同时实现__深度__和__宽度__下限。</span><span class="sxs-lookup"><span data-stu-id="49ae7-150">It might not be possible to achieve both __Depth__ and __Width__ lower bounds simultaneously.</span></span>  |
|<span data-ttu-id="49ae7-151">__BorrowedWidth__</span><span class="sxs-lookup"><span data-stu-id="49ae7-151">__BorrowedWidth__</span></span>    |<span data-ttu-id="49ae7-152">操作中借用的最大 qubits 数 Q# 。</span><span class="sxs-lookup"><span data-stu-id="49ae7-152">The maximum number of qubits borrowed inside the Q# operation.</span></span>  |

## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="49ae7-153">提供测量结果的概率</span><span class="sxs-lookup"><span data-stu-id="49ae7-153">Providing the probability of measurement outcomes</span></span>

<span data-ttu-id="49ae7-154">您可以使用 <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> <xref:microsoft.quantum.diagnostics> 命名空间中的来提供有关测量操作预期概率的信息。</span><span class="sxs-lookup"><span data-stu-id="49ae7-154">You can use <xref:microsoft.quantum.diagnostics.assertmeasurementprobability> from the <xref:microsoft.quantum.diagnostics> namespace to provide information about the expected probability of a measurement operation.</span></span> <span data-ttu-id="49ae7-155">有关详细信息，请参阅[量程跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span><span class="sxs-lookup"><span data-stu-id="49ae7-155">For more information, see [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span></span>

## <a name="see-also"></a><span data-ttu-id="49ae7-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="49ae7-156">See also</span></span>

- [<span data-ttu-id="49ae7-157">量程跟踪模拟器</span><span class="sxs-lookup"><span data-stu-id="49ae7-157">Quantum trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [<span data-ttu-id="49ae7-158">量子 Toffoli 模拟器</span><span class="sxs-lookup"><span data-stu-id="49ae7-158">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="49ae7-159">量子全状态模拟器</span><span class="sxs-lookup"><span data-stu-id="49ae7-159">Quantum full state simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 