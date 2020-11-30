---
title: 量程资源估计器-量程开发工具包
description: 了解 Microsoft QDK resources 估计器，它估算 Q# 在量程计算机上运行某一给定操作实例所需的资源。
author: anpaz-msft
ms.author: anpaz
ms.date: 06/26/2020
ms.topic: article
uid: microsoft.quantum.machines.resources-estimator
no-loc:
- Q#
- $$v
ms.openlocfilehash: 57f6602effd25fff353a8fee7f27acc529ce82af
ms.sourcegitcommit: c3c892ef35eae6926d0c4339d9d26bfd8be77e9a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/30/2020
ms.locfileid: "96318484"
---
# <a name="quantum-development-kit-qdk-resources-estimator"></a><span data-ttu-id="21ff0-103">量程开发工具包 (QDK) 资源估计器</span><span class="sxs-lookup"><span data-stu-id="21ff0-103">Quantum Development Kit (QDK) resources estimator</span></span>

<span data-ttu-id="21ff0-104">顾名思义，类会估算在 `ResourcesEstimator` 量程计算机上运行某一给定操作实例所需的资源 Q# 。</span><span class="sxs-lookup"><span data-stu-id="21ff0-104">As the name implies, the `ResourcesEstimator` class estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span> <span data-ttu-id="21ff0-105">它通过运行量程操作来实现此操作，而无需实际模拟量子计算机的状态;出于此原因，它会估算 Q# 使用上千个 qubits 的操作的资源，前提是代码的传统部分在合理的时间内运行。</span><span class="sxs-lookup"><span data-stu-id="21ff0-105">It accomplishes this by running the quantum operation without actually simulating the state of a quantum computer; for this reason, it estimates resources for Q# operations that use thousands of qubits, provided that the classical part of the code runs in a reasonable time.</span></span>

<span data-ttu-id="21ff0-106">资源估计器是在 [量程跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)的基础上构建的，它提供了一组更丰富的指标和工具来帮助调试 Q# 程序。</span><span class="sxs-lookup"><span data-stu-id="21ff0-106">The resources estimator is built on top of the [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), which provides a richer set of metrics and tools to help debug Q# programs.</span></span>

## <a name="invoking-and-running-the-resources-estimator"></a><span data-ttu-id="21ff0-107">调用和运行资源估计器</span><span class="sxs-lookup"><span data-stu-id="21ff0-107">Invoking and running the resources estimator</span></span>

<span data-ttu-id="21ff0-108">可以使用资源估计器运行任何 Q# 操作。</span><span class="sxs-lookup"><span data-stu-id="21ff0-108">You can use the resources estimator to run any Q# operation.</span></span> <span data-ttu-id="21ff0-109">有关更多详细信息，请参阅 [运行 Q# 程序的方法](xref:microsoft.quantum.guide.host-programs)。</span><span class="sxs-lookup"><span data-stu-id="21ff0-109">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-resources-estimator-from-c"></a><span data-ttu-id="21ff0-110">从 C 调用资源估计器#</span><span class="sxs-lookup"><span data-stu-id="21ff0-110">Invoking the resources estimator from C#</span></span> 

<span data-ttu-id="21ff0-111">与使用其他目标计算机一样，你首先创建 `ResourceEstimator` 类的实例，然后将其作为操作的 `Run` 方法的第一个参数传递。</span><span class="sxs-lookup"><span data-stu-id="21ff0-111">As with other target machines, you first create an instance of the `ResourceEstimator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="21ff0-112">请注意，与 `QuantumSimulator` 类不同，`ResourceEstimator` 类不实现 <xref:System.IDisposable> 接口，因此不需要将其放在 `using` 语句中。</span><span class="sxs-lookup"><span data-stu-id="21ff0-112">Note that, unlike the `QuantumSimulator` class, the `ResourceEstimator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

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

<span data-ttu-id="21ff0-113">如示例所示， `ResourcesEstimator` 提供 `ToTSV()` 方法，该方法生成一个表，其中包含以制表符分隔的值 (TSV) 。</span><span class="sxs-lookup"><span data-stu-id="21ff0-113">As the example shows, `ResourcesEstimator` provides the `ToTSV()` method, which generates a table with tab-separated values (TSV).</span></span> <span data-ttu-id="21ff0-114">可以将表保存到文件或将其显示在控制台中进行分析。</span><span class="sxs-lookup"><span data-stu-id="21ff0-114">You can save the table to a file or display it to the console for analysis.</span></span> <span data-ttu-id="21ff0-115">下面是前述程序的示例输出：</span><span class="sxs-lookup"><span data-stu-id="21ff0-115">The following is a sample output from the preceding program:</span></span>

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
> <span data-ttu-id="21ff0-116">`ResourcesEstimator`实例不会在每次运行时重置其计算。</span><span class="sxs-lookup"><span data-stu-id="21ff0-116">A `ResourcesEstimator` instance does not reset its calculations on every run.</span></span> <span data-ttu-id="21ff0-117">如果使用同一个实例运行另一个操作，则会将新结果与现有结果聚合在一起。</span><span class="sxs-lookup"><span data-stu-id="21ff0-117">If you use the same instance to run another operation, it aggregates the new results with the existing results.</span></span> <span data-ttu-id="21ff0-118">如果需要在运行之间重置计算，则为每次运行创建一个新的实例。</span><span class="sxs-lookup"><span data-stu-id="21ff0-118">If you need to reset calculations between runs, create a new instance for every run.</span></span>

### <a name="invoking-the-resources-estimator-from-python"></a><span data-ttu-id="21ff0-119">从 Python 调用资源估计器</span><span class="sxs-lookup"><span data-stu-id="21ff0-119">Invoking the resources estimator from Python</span></span>

<span data-ttu-id="21ff0-120">使用导入的操作在 Python 库中使用 [estimate_resources ( # B1 ](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) 方法 Q# ：</span><span class="sxs-lookup"><span data-stu-id="21ff0-120">Use the [estimate_resources()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) method from the Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.estimate_resources()
```

### <a name="invoking-the-resources-estimator-from-the-command-line"></a><span data-ttu-id="21ff0-121">从命令行调用资源估计器</span><span class="sxs-lookup"><span data-stu-id="21ff0-121">Invoking the resources estimator from the command line</span></span>

<span data-ttu-id="21ff0-122">在 Q# 从命令行运行程序时，使用 **--模拟器** (或 **-s** 快捷) 参数来指定 `ResourcesEstimator` 目标计算机。</span><span class="sxs-lookup"><span data-stu-id="21ff0-122">When running a Q# program from the command line, use the **--simulator** (or **-s** shortcut) parameter to specify the `ResourcesEstimator` target machine.</span></span> <span data-ttu-id="21ff0-123">以下命令使用资源估计器运行程序：</span><span class="sxs-lookup"><span data-stu-id="21ff0-123">The following command runs a program using the resources estimator:</span></span> 

```dotnetcli
dotnet run -s ResourcesEstimator
```

### <a name="invoking-the-resources-estimator-from-juptyer-notebooks"></a><span data-ttu-id="21ff0-124">从 Juptyer 笔记本调用资源估计器</span><span class="sxs-lookup"><span data-stu-id="21ff0-124">Invoking the resources estimator from Juptyer Notebooks</span></span>

<span data-ttu-id="21ff0-125">使用 I Q# 幻命令 [% 估算](xref:microsoft.quantum.iqsharp.magic-ref.simulate) 来运行 Q# 操作。</span><span class="sxs-lookup"><span data-stu-id="21ff0-125">Use the IQ# magic command [%estimate](xref:microsoft.quantum.iqsharp.magic-ref.simulate) to run the Q# operation.</span></span>

```
%estimate myOperation
```

## <a name="programmatically-retrieving-the-estimated-data"></a><span data-ttu-id="21ff0-126">以编程方式检索估计的数据</span><span class="sxs-lookup"><span data-stu-id="21ff0-126">Programmatically retrieving the estimated data</span></span>

<span data-ttu-id="21ff0-127">除了 TSV 表之外，还可以通过资源估计器的属性以编程方式检索在运行期间估计的资源 `Data` 。</span><span class="sxs-lookup"><span data-stu-id="21ff0-127">In addition to a TSV table, you can programmatically retrieve the resources estimated during the run via the `Data` property of the resources estimator.</span></span> <span data-ttu-id="21ff0-128">`Data`属性提供一个 `System.DataTable` 具有两列的实例： `Metric` 和 `Sum` ，并按指标的名称编制索引。</span><span class="sxs-lookup"><span data-stu-id="21ff0-128">The `Data` property provides a `System.DataTable` instance with two columns: `Metric` and `Sum`, indexed by the metrics' names.</span></span>

<span data-ttu-id="21ff0-129">下面的代码演示如何检索和打印操作所使用的的 `QubitClifford` 总数 `T` 和 `CNOT` 操作 Q# ：</span><span class="sxs-lookup"><span data-stu-id="21ff0-129">The following code shows how to retrieve and print the total number of `QubitClifford`, `T` and `CNOT` operations used by a Q# operation:</span></span>

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

## <a name="metrics-reported"></a><span data-ttu-id="21ff0-130">报告的指标</span><span class="sxs-lookup"><span data-stu-id="21ff0-130">Metrics Reported</span></span>

<span data-ttu-id="21ff0-131">资源估计器跟踪以下度量值：</span><span class="sxs-lookup"><span data-stu-id="21ff0-131">The resources estimator tracks the following metrics:</span></span>

|<span data-ttu-id="21ff0-132">指标</span><span class="sxs-lookup"><span data-stu-id="21ff0-132">Metric</span></span>|<span data-ttu-id="21ff0-133">描述</span><span class="sxs-lookup"><span data-stu-id="21ff0-133">Description</span></span>|
|----|----|
|<span data-ttu-id="21ff0-134">__CNOT__</span><span class="sxs-lookup"><span data-stu-id="21ff0-134">__CNOT__</span></span>    |<span data-ttu-id="21ff0-135">操作的运行计数 `CNOT` (也称为受控 Pauli X 操作) 。</span><span class="sxs-lookup"><span data-stu-id="21ff0-135">The run count of `CNOT` operations (also known as Controlled Pauli X operations).</span></span>|
|<span data-ttu-id="21ff0-136">__QubitClifford__</span><span class="sxs-lookup"><span data-stu-id="21ff0-136">__QubitClifford__</span></span> |<span data-ttu-id="21ff0-137">任何单个 qubit Clifford 和 Pauli 操作的运行计数。</span><span class="sxs-lookup"><span data-stu-id="21ff0-137">The run count of any single qubit Clifford and Pauli operations.</span></span>|
|<span data-ttu-id="21ff0-138">度量 </span><span class="sxs-lookup"><span data-stu-id="21ff0-138">__Measure__</span></span>    |<span data-ttu-id="21ff0-139">任何度量值的运行计数。</span><span class="sxs-lookup"><span data-stu-id="21ff0-139">The run count of any measurements.</span></span>  |
|<span data-ttu-id="21ff0-140">__R__</span><span class="sxs-lookup"><span data-stu-id="21ff0-140">__R__</span></span>    |<span data-ttu-id="21ff0-141">任何单 qubit 循环、不包括 `T` 、Clifford 和 Pauli 操作的运行计数。</span><span class="sxs-lookup"><span data-stu-id="21ff0-141">The run count of any single-qubit rotations, excluding `T`, Clifford and Pauli operations.</span></span>  |
|<span data-ttu-id="21ff0-142">__T__</span><span class="sxs-lookup"><span data-stu-id="21ff0-142">__T__</span></span>    |<span data-ttu-id="21ff0-143">操作的运行计数 `T` 及其词干，包括 `T` 操作、T_x = 1xt-hy-ubw 和 T_y = 1Xt-hy-ubw。。</span><span class="sxs-lookup"><span data-stu-id="21ff0-143">The run count of `T` operations and their conjugates, including the `T` operations, T_x = H.T.H, and T_y = Hy.T.Hy.</span></span>  |
|<span data-ttu-id="21ff0-144">__深度__</span><span class="sxs-lookup"><span data-stu-id="21ff0-144">__Depth__</span></span>|<span data-ttu-id="21ff0-145">操作运行的量程线路的深度 Q# (参见 [下面](#depth-width-and-qubitcount)) 。</span><span class="sxs-lookup"><span data-stu-id="21ff0-145">Depth of the quantum circuit run by the Q# operation (see [below](#depth-width-and-qubitcount)).</span></span> <span data-ttu-id="21ff0-146">默认情况下，深度指标仅计算 `T` 入口。</span><span class="sxs-lookup"><span data-stu-id="21ff0-146">By default, the depth metric only counts `T` gates.</span></span> <span data-ttu-id="21ff0-147">有关更多详细信息，请参阅 [深度计数器](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)。</span><span class="sxs-lookup"><span data-stu-id="21ff0-147">For more details, see [Depth Counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span></span>   |
|<span data-ttu-id="21ff0-148">Width </span><span class="sxs-lookup"><span data-stu-id="21ff0-148">__Width__</span></span>|<span data-ttu-id="21ff0-149">操作运行的量程线路的宽度 Q# (参见 [下面](#depth-width-and-qubitcount)) 。</span><span class="sxs-lookup"><span data-stu-id="21ff0-149">Width of the quantum circuit run by the Q# operation (see [below](#depth-width-and-qubitcount)).</span></span> <span data-ttu-id="21ff0-150">默认情况下，深度指标仅计算 `T` 入口。</span><span class="sxs-lookup"><span data-stu-id="21ff0-150">By default, the depth metric only counts `T` gates.</span></span> <span data-ttu-id="21ff0-151">有关更多详细信息，请参阅 [Width Counter](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)。</span><span class="sxs-lookup"><span data-stu-id="21ff0-151">For more details, see [Width Counter](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter).</span></span>   |
|<span data-ttu-id="21ff0-152">__QubitCount__</span><span class="sxs-lookup"><span data-stu-id="21ff0-152">__QubitCount__</span></span>    |<span data-ttu-id="21ff0-153">运行操作期间分配的最大 qubits 数的下限 Q# 。</span><span class="sxs-lookup"><span data-stu-id="21ff0-153">The lower bound for the maximum number of qubits allocated during the run of the Q# operation.</span></span> <span data-ttu-id="21ff0-154">此指标可能不与 __深度__ 兼容 (请参阅下面) 。</span><span class="sxs-lookup"><span data-stu-id="21ff0-154">This metric might not be compatible with __Depth__ (see below).</span></span>  |
|<span data-ttu-id="21ff0-155">__BorrowedWidth__</span><span class="sxs-lookup"><span data-stu-id="21ff0-155">__BorrowedWidth__</span></span>    |<span data-ttu-id="21ff0-156">操作中借用的最大 qubits 数 Q# 。</span><span class="sxs-lookup"><span data-stu-id="21ff0-156">The maximum number of qubits borrowed inside the Q# operation.</span></span>  |


## <a name="depth-width-and-qubitcount"></a><span data-ttu-id="21ff0-157">深度、宽度和 QubitCount</span><span class="sxs-lookup"><span data-stu-id="21ff0-157">Depth, Width, and QubitCount</span></span>

<span data-ttu-id="21ff0-158">报告的深度和宽度估计值彼此兼容。</span><span class="sxs-lookup"><span data-stu-id="21ff0-158">Reported Depth and Width estimates are compatible with each other.</span></span>
<span data-ttu-id="21ff0-159"> (以前都可以使用这两个数字，但宽度和宽度需要不同的线路。 ) 当前这对中的这两个指标都可以同时通过相同的线路实现。</span><span class="sxs-lookup"><span data-stu-id="21ff0-159">(Previously both numbers were achievable, but different circuits would be required for Depth and for Width.) Currently both metrics in this pair can be achieved by the same circuit at the same time.</span></span>

<span data-ttu-id="21ff0-160">报告以下指标：</span><span class="sxs-lookup"><span data-stu-id="21ff0-160">The following metrics are reported:</span></span>

<span data-ttu-id="21ff0-161">__深度：__ 对于根操作-执行此操作所用的时间（假定特定的入口时间）。</span><span class="sxs-lookup"><span data-stu-id="21ff0-161">__Depth:__ For the root operation - time it takes to execute it assuming specific gate times.</span></span>
<span data-ttu-id="21ff0-162">对于调用的操作或后续操作-在操作开始和结束时最新 qubit 可用性时间之间的时间差。</span><span class="sxs-lookup"><span data-stu-id="21ff0-162">For operations called or subsequent operations - time difference between latest qubit availability time at the beginning and the end of the operation.</span></span>

<span data-ttu-id="21ff0-163">__宽度：__ 对于根操作-实际用于执行它的 qubits 的数目 (和操作，它将调用) 。</span><span class="sxs-lookup"><span data-stu-id="21ff0-163">__Width:__ For the root operation - number of qubits actually used to execute it (and operation it calls).</span></span>
<span data-ttu-id="21ff0-164">对于被调用的操作或后续操作，还使用了除操作开始时已使用的 qubits 以外还有多少 qubits。</span><span class="sxs-lookup"><span data-stu-id="21ff0-164">For operations called or subsequent operations - how many more qubits were used in addition to the qubits already used at the beginning of the operation.</span></span>

<span data-ttu-id="21ff0-165">请注意，重复使用 qubits 不会影响此数字。</span><span class="sxs-lookup"><span data-stu-id="21ff0-165">Please note, that reused qubits do not contribute to this number.</span></span>
<span data-ttu-id="21ff0-166">例如，如果在操作 A 开始之前已释放几个 qubits，并且此操作要求的所有 qubit 都是通过重复使用以前的版本 qubits 满足的 (和从) 调用的操作，则将操作 A 的宽度报告为0。</span><span class="sxs-lookup"><span data-stu-id="21ff0-166">I.e. if a few qubits have been released before operation A starts, and all qubit demanded by this operation A (and operations called from A) were satisfied by reusing previously release qubits, the Width of operation A is reported as 0.</span></span> <span data-ttu-id="21ff0-167">成功的借用 qubits 不会影响宽度。</span><span class="sxs-lookup"><span data-stu-id="21ff0-167">Successfully borrowed qubits do not contribute to the Width either.</span></span>

<span data-ttu-id="21ff0-168">__QubitCount：__ 对于根操作-qubits 执行此 (操作所需的最小数量的和从其调用) 的操作。</span><span class="sxs-lookup"><span data-stu-id="21ff0-168">__QubitCount:__ For the root operation - minimum number of qubits that would be sufficient to execute this operation (and operations called from it).</span></span>
<span data-ttu-id="21ff0-169">对于被调用的操作或后续操作，为单独执行此操作所需的最小 qubits 数。</span><span class="sxs-lookup"><span data-stu-id="21ff0-169">For operations called or subsequent operations - minimum number of qubits that would be sufficient to execute this operation separately.</span></span> <span data-ttu-id="21ff0-170">此数值不包括输入 qubits。</span><span class="sxs-lookup"><span data-stu-id="21ff0-170">This number doesn't include input qubits.</span></span> <span data-ttu-id="21ff0-171">它包括借用 qubits。</span><span class="sxs-lookup"><span data-stu-id="21ff0-171">It does include borrowed qubits.</span></span>

<span data-ttu-id="21ff0-172">支持两种操作模式。</span><span class="sxs-lookup"><span data-stu-id="21ff0-172">Two modes of operation are supported.</span></span> <span data-ttu-id="21ff0-173">通过设置 QCTraceSimulatorConfiguration 来选择模式。</span><span class="sxs-lookup"><span data-stu-id="21ff0-173">Mode is selected by setting QCTraceSimulatorConfiguration.OptimizeDepth.</span></span>

<span data-ttu-id="21ff0-174">__OptimizeDepth = true：__ 不建议在 qubit 重复使用 QubitManager，并在每次请求 qubit 时分配新的 qubit。</span><span class="sxs-lookup"><span data-stu-id="21ff0-174">__OptimizeDepth=true:__ QubitManager is discouraged from qubit reuse and allocates new qubit every time it is asked for a qubit.</span></span> <span data-ttu-id="21ff0-175">对于根操作 __深度__ ，将成为下限)  (最小深度。</span><span class="sxs-lookup"><span data-stu-id="21ff0-175">For the root operation __Depth__ becomes the minimum depth (lower bound).</span></span> <span data-ttu-id="21ff0-176">为此深度报告兼容的 __宽度__ (同时) 可以实现这两者。</span><span class="sxs-lookup"><span data-stu-id="21ff0-176">Compatible __Width__ is reported for this depth (both can be achieved at the same time).</span></span> <span data-ttu-id="21ff0-177">请注意，对于此深度，此宽度可能并不是最佳的。</span><span class="sxs-lookup"><span data-stu-id="21ff0-177">Note, that this width will likely be not optimal given this depth.</span></span> <span data-ttu-id="21ff0-178">__QubitCount__ 可能低于根操作的宽度，因为它会采用重复使用。</span><span class="sxs-lookup"><span data-stu-id="21ff0-178">__QubitCount__ may be lower than Width for the root operation because it assumes reuse.</span></span>

<span data-ttu-id="21ff0-179">__OptimizeDepth = false：__ 建议使用 QubitManager，以便在分配新的 qubits 之前重复使用已发布的。</span><span class="sxs-lookup"><span data-stu-id="21ff0-179">__OptimizeDepth=false:__ QubitManager is encouraged to reuse qubits and will reuse released qubits before allocating new ones.</span></span> <span data-ttu-id="21ff0-180">对于根操作，" __宽度__ " 将成为 (下限) 的最小宽度。</span><span class="sxs-lookup"><span data-stu-id="21ff0-180">For the root operation __Width__ becomes the minimal width (lower bound).</span></span> <span data-ttu-id="21ff0-181">系统会报告兼容 __深度__ ，可对其进行实现。</span><span class="sxs-lookup"><span data-stu-id="21ff0-181">Compatible __Depth__ is reported on which it can be achieved.</span></span> <span data-ttu-id="21ff0-182">__QubitCount__ 将与根操作的 __宽度__ 相同，假设没有借款。</span><span class="sxs-lookup"><span data-stu-id="21ff0-182">__QubitCount__ will be the same as __Width__ for the root operation assuming no borrowing.</span></span>

## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="21ff0-183">提供测量结果的概率</span><span class="sxs-lookup"><span data-stu-id="21ff0-183">Providing the probability of measurement outcomes</span></span>

<span data-ttu-id="21ff0-184">您可以使用 <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> <xref:Microsoft.Quantum.Diagnostics> 命名空间中的来提供有关测量操作预期概率的信息。</span><span class="sxs-lookup"><span data-stu-id="21ff0-184">You can use <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> from the <xref:Microsoft.Quantum.Diagnostics> namespace to provide information about the expected probability of a measurement operation.</span></span> <span data-ttu-id="21ff0-185">有关详细信息，请参阅 [量程跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span><span class="sxs-lookup"><span data-stu-id="21ff0-185">For more information, see [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span></span>

## <a name="see-also"></a><span data-ttu-id="21ff0-186">请参阅</span><span class="sxs-lookup"><span data-stu-id="21ff0-186">See also</span></span>

- [<span data-ttu-id="21ff0-187">量程跟踪模拟器</span><span class="sxs-lookup"><span data-stu-id="21ff0-187">Quantum trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [<span data-ttu-id="21ff0-188">量子 Toffoli 模拟器</span><span class="sxs-lookup"><span data-stu-id="21ff0-188">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="21ff0-189">量子全状态模拟器</span><span class="sxs-lookup"><span data-stu-id="21ff0-189">Quantum full state simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 
