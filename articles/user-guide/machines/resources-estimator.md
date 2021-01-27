---
title: 量程资源估计器-量程开发工具包
description: 了解 Microsoft QDK resources 估计器，它估算 Q# 在量程计算机上运行某一给定操作实例所需的资源。
author: anpaz
ms.author: anpaz
ms.date: 06/26/2020
ms.topic: conceptual
uid: microsoft.quantum.machines.resources-estimator
no-loc:
- Q#
- $$v
ms.openlocfilehash: c3aa94c8b34ad7247fbdeab4bf4dcb96ce746014
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847465"
---
# <a name="quantum-development-kit-qdk-resources-estimator"></a><span data-ttu-id="25969-103">量程开发工具包 (QDK) 资源估计器</span><span class="sxs-lookup"><span data-stu-id="25969-103">Quantum Development Kit (QDK) resources estimator</span></span>

<span data-ttu-id="25969-104">顾名思义，类会估算在 `ResourcesEstimator` 量程计算机上运行某一给定操作实例所需的资源 Q# 。</span><span class="sxs-lookup"><span data-stu-id="25969-104">As the name implies, the `ResourcesEstimator` class estimates the resources required to run a given instance of a Q# operation on a quantum computer.</span></span> <span data-ttu-id="25969-105">它通过运行量程操作来实现此操作，而无需实际模拟量子计算机的状态;出于此原因，它会估算 Q# 使用上千个 qubits 的操作的资源，前提是代码的传统部分在合理的时间内运行。</span><span class="sxs-lookup"><span data-stu-id="25969-105">It accomplishes this by running the quantum operation without actually simulating the state of a quantum computer; for this reason, it estimates resources for Q# operations that use thousands of qubits, provided that the classical part of the code runs in a reasonable time.</span></span>

<span data-ttu-id="25969-106">资源估计器是在 [量程跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)的基础上构建的，它提供了一组更丰富的指标和工具来帮助调试 Q# 程序。</span><span class="sxs-lookup"><span data-stu-id="25969-106">The resources estimator is built on top of the [Quantum trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), which provides a richer set of metrics and tools to help debug Q# programs.</span></span>

## <a name="invoking-and-running-the-resources-estimator"></a><span data-ttu-id="25969-107">调用和运行资源估计器</span><span class="sxs-lookup"><span data-stu-id="25969-107">Invoking and running the resources estimator</span></span>

<span data-ttu-id="25969-108">可以使用资源估计器运行任何 Q# 操作。</span><span class="sxs-lookup"><span data-stu-id="25969-108">You can use the resources estimator to run any Q# operation.</span></span> <span data-ttu-id="25969-109">有关更多详细信息，请参阅 [运行 Q# 程序的方法](xref:microsoft.quantum.guide.host-programs)。</span><span class="sxs-lookup"><span data-stu-id="25969-109">For additional details, see [Ways to run a Q# program](xref:microsoft.quantum.guide.host-programs).</span></span>

### <a name="invoking-the-resources-estimator-from-c"></a><span data-ttu-id="25969-110">从 C 调用资源估计器#</span><span class="sxs-lookup"><span data-stu-id="25969-110">Invoking the resources estimator from C#</span></span> 

<span data-ttu-id="25969-111">与使用其他目标计算机一样，你首先创建 `ResourcesEstimator` 类的实例，然后将其作为操作的 `Run` 方法的第一个参数传递。</span><span class="sxs-lookup"><span data-stu-id="25969-111">As with other target machines, you first create an instance of the `ResourcesEstimator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="25969-112">请注意，与 `QuantumSimulator` 类不同，`ResourcesEstimator` 类不实现 <xref:System.IDisposable> 接口，因此不需要将其放在 `using` 语句中。</span><span class="sxs-lookup"><span data-stu-id="25969-112">Note that, unlike the `QuantumSimulator` class, the `ResourcesEstimator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

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

<span data-ttu-id="25969-113">如示例所示， `ResourcesEstimator` 提供 `ToTSV()` 方法，该方法生成一个表，其中包含以制表符分隔的值 (TSV) 。</span><span class="sxs-lookup"><span data-stu-id="25969-113">As the example shows, `ResourcesEstimator` provides the `ToTSV()` method, which generates a table with tab-separated values (TSV).</span></span> <span data-ttu-id="25969-114">可以将表保存到文件或将其显示在控制台中进行分析。</span><span class="sxs-lookup"><span data-stu-id="25969-114">You can save the table to a file or display it to the console for analysis.</span></span> <span data-ttu-id="25969-115">下面是前述程序的示例输出：</span><span class="sxs-lookup"><span data-stu-id="25969-115">The following is a sample output from the preceding program:</span></span>

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
> <span data-ttu-id="25969-116">`ResourcesEstimator`实例不会在每次运行时重置其计算。</span><span class="sxs-lookup"><span data-stu-id="25969-116">A `ResourcesEstimator` instance does not reset its calculations on every run.</span></span> <span data-ttu-id="25969-117">如果使用同一个实例运行另一个操作，则会将新结果与现有结果聚合在一起。</span><span class="sxs-lookup"><span data-stu-id="25969-117">If you use the same instance to run another operation, it aggregates the new results with the existing results.</span></span> <span data-ttu-id="25969-118">如果需要在运行之间重置计算，则为每次运行创建一个新的实例。</span><span class="sxs-lookup"><span data-stu-id="25969-118">If you need to reset calculations between runs, create a new instance for every run.</span></span>

### <a name="invoking-the-resources-estimator-from-python"></a><span data-ttu-id="25969-119">从 Python 调用资源估计器</span><span class="sxs-lookup"><span data-stu-id="25969-119">Invoking the resources estimator from Python</span></span>

<span data-ttu-id="25969-120">使用导入的操作在 Python 库中使用 [estimate_resources ( # B1 ](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) 方法 Q# ：</span><span class="sxs-lookup"><span data-stu-id="25969-120">Use the [estimate_resources()](https://docs.microsoft.com/python/qsharp-core/qsharp.loader.qsharpcallable) method from the Python library with the imported Q# operation:</span></span>

```python
qubit_result = myOperation.estimate_resources()
```

### <a name="invoking-the-resources-estimator-from-the-command-line"></a><span data-ttu-id="25969-121">从命令行调用资源估计器</span><span class="sxs-lookup"><span data-stu-id="25969-121">Invoking the resources estimator from the command line</span></span>

<span data-ttu-id="25969-122">在 Q# 从命令行运行程序时，使用 **--模拟器** (或 **-s** 快捷) 参数来指定 `ResourcesEstimator` 目标计算机。</span><span class="sxs-lookup"><span data-stu-id="25969-122">When running a Q# program from the command line, use the **--simulator** (or **-s** shortcut) parameter to specify the `ResourcesEstimator` target machine.</span></span> <span data-ttu-id="25969-123">以下命令使用资源估计器运行程序：</span><span class="sxs-lookup"><span data-stu-id="25969-123">The following command runs a program using the resources estimator:</span></span> 

```dotnetcli
dotnet run -s ResourcesEstimator
```

### <a name="invoking-the-resources-estimator-from-juptyer-notebooks"></a><span data-ttu-id="25969-124">从 Juptyer 笔记本调用资源估计器</span><span class="sxs-lookup"><span data-stu-id="25969-124">Invoking the resources estimator from Juptyer Notebooks</span></span>

<span data-ttu-id="25969-125">使用 I Q# 幻命令 [% 估算](xref:microsoft.quantum.iqsharp.magic-ref.simulate) 来运行 Q# 操作。</span><span class="sxs-lookup"><span data-stu-id="25969-125">Use the IQ# magic command [%estimate](xref:microsoft.quantum.iqsharp.magic-ref.simulate) to run the Q# operation.</span></span>

```
%estimate myOperation
```

## <a name="programmatically-retrieving-the-estimated-data"></a><span data-ttu-id="25969-126">以编程方式检索估计的数据</span><span class="sxs-lookup"><span data-stu-id="25969-126">Programmatically retrieving the estimated data</span></span>

<span data-ttu-id="25969-127">除了 TSV 表之外，还可以通过资源估计器的属性以编程方式检索在运行期间估计的资源 `Data` 。</span><span class="sxs-lookup"><span data-stu-id="25969-127">In addition to a TSV table, you can programmatically retrieve the resources estimated during the run via the `Data` property of the resources estimator.</span></span> <span data-ttu-id="25969-128">`Data`属性提供一个 `System.DataTable` 具有两列的实例： `Metric` 和 `Sum` ，并按指标的名称编制索引。</span><span class="sxs-lookup"><span data-stu-id="25969-128">The `Data` property provides a `System.DataTable` instance with two columns: `Metric` and `Sum`, indexed by the metrics' names.</span></span>

<span data-ttu-id="25969-129">下面的代码演示如何检索和打印操作所使用的的 `QubitClifford` 总数 `T` 和 `CNOT` 操作 Q# ：</span><span class="sxs-lookup"><span data-stu-id="25969-129">The following code shows how to retrieve and print the total number of `QubitClifford`, `T` and `CNOT` operations used by a Q# operation:</span></span>

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

## <a name="metrics-reported"></a><span data-ttu-id="25969-130">报告的指标</span><span class="sxs-lookup"><span data-stu-id="25969-130">Metrics Reported</span></span>

<span data-ttu-id="25969-131">资源估计器跟踪以下度量值：</span><span class="sxs-lookup"><span data-stu-id="25969-131">The resources estimator tracks the following metrics:</span></span>

|<span data-ttu-id="25969-132">指标</span><span class="sxs-lookup"><span data-stu-id="25969-132">Metric</span></span>|<span data-ttu-id="25969-133">说明</span><span class="sxs-lookup"><span data-stu-id="25969-133">Description</span></span>|
|----|----|
|<span data-ttu-id="25969-134">__CNOT__</span><span class="sxs-lookup"><span data-stu-id="25969-134">__CNOT__</span></span>    |<span data-ttu-id="25969-135">操作的运行计数 `CNOT` (也称为受控 Pauli X 操作) 。</span><span class="sxs-lookup"><span data-stu-id="25969-135">The run count of `CNOT` operations (also known as Controlled Pauli X operations).</span></span>|
|<span data-ttu-id="25969-136">__QubitClifford__</span><span class="sxs-lookup"><span data-stu-id="25969-136">__QubitClifford__</span></span> |<span data-ttu-id="25969-137">任何单个 qubit Clifford 和 Pauli 操作的运行计数。</span><span class="sxs-lookup"><span data-stu-id="25969-137">The run count of any single qubit Clifford and Pauli operations.</span></span>|
|<span data-ttu-id="25969-138">度量 </span><span class="sxs-lookup"><span data-stu-id="25969-138">__Measure__</span></span>    |<span data-ttu-id="25969-139">任何度量值的运行计数。</span><span class="sxs-lookup"><span data-stu-id="25969-139">The run count of any measurements.</span></span>  |
|<span data-ttu-id="25969-140">__R__</span><span class="sxs-lookup"><span data-stu-id="25969-140">__R__</span></span>    |<span data-ttu-id="25969-141">任何单 qubit 循环、不包括 `T` 、Clifford 和 Pauli 操作的运行计数。</span><span class="sxs-lookup"><span data-stu-id="25969-141">The run count of any single-qubit rotations, excluding `T`, Clifford and Pauli operations.</span></span>  |
|<span data-ttu-id="25969-142">__T__</span><span class="sxs-lookup"><span data-stu-id="25969-142">__T__</span></span>    |<span data-ttu-id="25969-143">操作的运行计数 `T` 及其词干，包括 `T` 操作、T_x = 1xt-hy-ubw 和 T_y = 1Xt-hy-ubw。。</span><span class="sxs-lookup"><span data-stu-id="25969-143">The run count of `T` operations and their conjugates, including the `T` operations, T_x = H.T.H, and T_y = Hy.T.Hy.</span></span>  |
|<span data-ttu-id="25969-144">__Depth__</span><span class="sxs-lookup"><span data-stu-id="25969-144">__Depth__</span></span>|<span data-ttu-id="25969-145">操作运行的量程线路的深度 Q# (参见 [下面](#depth-width-and-qubitcount)) 。</span><span class="sxs-lookup"><span data-stu-id="25969-145">Depth of the quantum circuit run by the Q# operation (see [below](#depth-width-and-qubitcount)).</span></span> <span data-ttu-id="25969-146">默认情况下，深度指标仅计算 `T` 入口。</span><span class="sxs-lookup"><span data-stu-id="25969-146">By default, the depth metric only counts `T` gates.</span></span> <span data-ttu-id="25969-147">有关更多详细信息，请参阅 [深度计数器](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)。</span><span class="sxs-lookup"><span data-stu-id="25969-147">For more details, see [Depth Counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter).</span></span>   |
|<span data-ttu-id="25969-148">__Width__</span><span class="sxs-lookup"><span data-stu-id="25969-148">__Width__</span></span>|<span data-ttu-id="25969-149">操作运行的量程线路的宽度 Q# (参见 [下面](#depth-width-and-qubitcount)) 。</span><span class="sxs-lookup"><span data-stu-id="25969-149">Width of the quantum circuit run by the Q# operation (see [below](#depth-width-and-qubitcount)).</span></span> <span data-ttu-id="25969-150">默认情况下，深度指标仅计算 `T` 入口。</span><span class="sxs-lookup"><span data-stu-id="25969-150">By default, the depth metric only counts `T` gates.</span></span> <span data-ttu-id="25969-151">有关更多详细信息，请参阅 [Width Counter](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)。</span><span class="sxs-lookup"><span data-stu-id="25969-151">For more details, see [Width Counter](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter).</span></span>   |
|<span data-ttu-id="25969-152">__QubitCount__</span><span class="sxs-lookup"><span data-stu-id="25969-152">__QubitCount__</span></span>    |<span data-ttu-id="25969-153">运行操作期间分配的最大 qubits 数的下限 Q# 。</span><span class="sxs-lookup"><span data-stu-id="25969-153">The lower bound for the maximum number of qubits allocated during the run of the Q# operation.</span></span> <span data-ttu-id="25969-154">此指标可能不与 __深度__ 兼容 (请参阅下面) 。</span><span class="sxs-lookup"><span data-stu-id="25969-154">This metric might not be compatible with __Depth__ (see below).</span></span>  |
|<span data-ttu-id="25969-155">__BorrowedWidth__</span><span class="sxs-lookup"><span data-stu-id="25969-155">__BorrowedWidth__</span></span>    |<span data-ttu-id="25969-156">操作中借用的最大 qubits 数 Q# 。</span><span class="sxs-lookup"><span data-stu-id="25969-156">The maximum number of qubits borrowed inside the Q# operation.</span></span>  |


## <a name="depth-width-and-qubitcount"></a><span data-ttu-id="25969-157">深度、宽度和 QubitCount</span><span class="sxs-lookup"><span data-stu-id="25969-157">Depth, Width, and QubitCount</span></span>

<span data-ttu-id="25969-158">报告的深度和宽度估计值彼此兼容。</span><span class="sxs-lookup"><span data-stu-id="25969-158">Reported Depth and Width estimates are compatible with each other.</span></span>
<span data-ttu-id="25969-159"> (以前都可以使用这两个数字，但宽度和宽度需要不同的线路。 ) 当前这对中的这两个指标都可以同时通过相同的线路实现。</span><span class="sxs-lookup"><span data-stu-id="25969-159">(Previously both numbers were achievable, but different circuits would be required for Depth and for Width.) Currently both metrics in this pair can be achieved by the same circuit at the same time.</span></span>

<span data-ttu-id="25969-160">报告以下指标：</span><span class="sxs-lookup"><span data-stu-id="25969-160">The following metrics are reported:</span></span>

<span data-ttu-id="25969-161">__深度：__ 对于根操作-执行此操作所用的时间（假定配置的入口时间）。</span><span class="sxs-lookup"><span data-stu-id="25969-161">__Depth:__ For the root operation - time it takes to execute it assuming configured gate times.</span></span>
<span data-ttu-id="25969-162">对于调用的操作或后续操作-在操作开始和结束时最新 qubit 可用性时间之间的时间差。</span><span class="sxs-lookup"><span data-stu-id="25969-162">For operations called or subsequent operations - time difference between the latest qubit availability time at the beginning and the end of the operation.</span></span>

<span data-ttu-id="25969-163">__宽度：__ 对于根操作-实际用于执行它的 qubits 的数目 (和操作，它将调用) 。</span><span class="sxs-lookup"><span data-stu-id="25969-163">__Width:__ For the root operation - number of qubits actually used to execute it (and operation it calls).</span></span>
<span data-ttu-id="25969-164">对于被调用的操作或后续操作，还使用了除操作开始时已使用的 qubits 以外还有多少 qubits。</span><span class="sxs-lookup"><span data-stu-id="25969-164">For operations called or subsequent operations - how many more qubits were used in addition to the qubits already used at the beginning of the operation.</span></span>

<span data-ttu-id="25969-165">请注意，重复使用 qubits 不会影响此数字。</span><span class="sxs-lookup"><span data-stu-id="25969-165">Please note, that reused qubits do not contribute to this number.</span></span>
<span data-ttu-id="25969-166">例如，如果在操作 A 开始之前已释放几个 qubits，并且此操作要求的所有 qubit 都是通过重复使用以前的版本 qubits 满足的 (和从) 调用的操作，则将操作 A 的宽度报告为0。</span><span class="sxs-lookup"><span data-stu-id="25969-166">I.e. if a few qubits have been released before operation A starts, and all qubit demanded by this operation A (and operations called from A) were satisfied by reusing previously release qubits, the Width of operation A is reported as 0.</span></span> <span data-ttu-id="25969-167">成功的借用 qubits 不会影响宽度。</span><span class="sxs-lookup"><span data-stu-id="25969-167">Successfully borrowed qubits do not contribute to the Width either.</span></span>

<span data-ttu-id="25969-168">__QubitCount：__ 对于根操作-qubits 执行此 (操作所需的最小数量的和从其调用) 的操作。</span><span class="sxs-lookup"><span data-stu-id="25969-168">__QubitCount:__ For the root operation - minimum number of qubits that would be sufficient to execute this operation (and operations called from it).</span></span>
<span data-ttu-id="25969-169">对于被调用的操作或后续操作，为单独执行此操作所需的最小 qubits 数。</span><span class="sxs-lookup"><span data-stu-id="25969-169">For operations called or subsequent operations - minimum number of qubits that would be sufficient to execute this operation separately.</span></span> <span data-ttu-id="25969-170">此数值不包括输入 qubits。</span><span class="sxs-lookup"><span data-stu-id="25969-170">This number doesn't include input qubits.</span></span> <span data-ttu-id="25969-171">它包括借用 qubits。</span><span class="sxs-lookup"><span data-stu-id="25969-171">It does include borrowed qubits.</span></span>

<span data-ttu-id="25969-172">支持两种操作模式。</span><span class="sxs-lookup"><span data-stu-id="25969-172">Two modes of operation are supported.</span></span> <span data-ttu-id="25969-173">通过设置 QCTraceSimulatorConfiguration 来选择模式。</span><span class="sxs-lookup"><span data-stu-id="25969-173">Mode is selected by setting QCTraceSimulatorConfiguration.OptimizeDepth.</span></span>

<span data-ttu-id="25969-174">__OptimizeDepth = false：__ 这是默认模式。</span><span class="sxs-lookup"><span data-stu-id="25969-174">__OptimizeDepth=false:__ This is the default mode.</span></span> <span data-ttu-id="25969-175">建议使用 QubitManager，以便在分配新的 qubits 之前重复使用已发布的。</span><span class="sxs-lookup"><span data-stu-id="25969-175">QubitManager is encouraged to reuse qubits and will reuse released qubits before allocating new ones.</span></span> <span data-ttu-id="25969-176">对于根操作，" __宽度__ " 将成为 (下限) 的最小宽度。</span><span class="sxs-lookup"><span data-stu-id="25969-176">For the root operation __Width__ becomes the minimal width (lower bound).</span></span> <span data-ttu-id="25969-177">系统会报告兼容 __深度__ ，可对其进行实现。</span><span class="sxs-lookup"><span data-stu-id="25969-177">Compatible __Depth__ is reported on which it can be achieved.</span></span> <span data-ttu-id="25969-178">__QubitCount__ 将与根操作的 __宽度__ 相同，假设没有借款。</span><span class="sxs-lookup"><span data-stu-id="25969-178">__QubitCount__ will be the same as __Width__ for the root operation assuming no borrowing.</span></span>

<span data-ttu-id="25969-179">__OptimizeDepth = true：__ 不建议在执行和执行过程中执行 QubitManager，qubit 重复使用和基于启发式的优化进行 qubit。</span><span class="sxs-lookup"><span data-stu-id="25969-179">__OptimizeDepth=true:__ QubitManager is discouraged from qubit reuse and heuristic-based optimization for qubit reuse is performed during and after execution.</span></span> <span data-ttu-id="25969-180">对于根操作 __深度__ ，将成为下限)  (最小深度。</span><span class="sxs-lookup"><span data-stu-id="25969-180">For the root operation __Depth__ becomes the minimum depth (lower bound).</span></span> <span data-ttu-id="25969-181">为此深度报告兼容的 __宽度__ (同时) 可以实现这两者。</span><span class="sxs-lookup"><span data-stu-id="25969-181">Compatible __Width__ is reported for this depth (both can be achieved at the same time).</span></span> <span data-ttu-id="25969-182">若要优化宽度，程序中稍后遇到的入口可能计划在程序前面所遇到的关口之前，但 qubits 计划为在深度保持最少的情况下重复使用。</span><span class="sxs-lookup"><span data-stu-id="25969-182">To optimize width, gates encountered later in the program may be scheduled before the gates encountered earlier in the program, but qubits are scheduled to be reused in such a way that the depth remains minimal.</span></span> <span data-ttu-id="25969-183">由于 qubits 基于时间值重用，因此建议将入口时间配置为整数值。</span><span class="sxs-lookup"><span data-stu-id="25969-183">As qubits are reused based on time values, it is recommended that the gate times are configured to be integer values.</span></span> <span data-ttu-id="25969-184">不保证 __宽度__ 是最佳的。</span><span class="sxs-lookup"><span data-stu-id="25969-184">__Width__ is not guaranteed to be optimal.</span></span> <span data-ttu-id="25969-185">有关详细信息，请参阅跟踪的白皮书 [宽度和深度](https://github.com/microsoft/qsharp-runtime/tree/main/src/Simulation/Simulators/QCTraceSimulator/Docs)。</span><span class="sxs-lookup"><span data-stu-id="25969-185">More information can be found in the whitepaper [Width and Depth in the Tracer](https://github.com/microsoft/qsharp-runtime/tree/main/src/Simulation/Simulators/QCTraceSimulator/Docs).</span></span>

## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="25969-186">提供测量结果的概率</span><span class="sxs-lookup"><span data-stu-id="25969-186">Providing the probability of measurement outcomes</span></span>

<span data-ttu-id="25969-187">您可以使用 <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> <xref:Microsoft.Quantum.Diagnostics> 命名空间中的来提供有关测量操作预期概率的信息。</span><span class="sxs-lookup"><span data-stu-id="25969-187">You can use <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> from the <xref:Microsoft.Quantum.Diagnostics> namespace to provide information about the expected probability of a measurement operation.</span></span> <span data-ttu-id="25969-188">有关详细信息，请参阅 [量程跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span><span class="sxs-lookup"><span data-stu-id="25969-188">For more information, see [Quantum Trace Simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro)</span></span>

## <a name="see-also"></a><span data-ttu-id="25969-189">另请参阅</span><span class="sxs-lookup"><span data-stu-id="25969-189">See also</span></span>

- [<span data-ttu-id="25969-190">量程跟踪模拟器</span><span class="sxs-lookup"><span data-stu-id="25969-190">Quantum trace simulator</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.intro)
- [<span data-ttu-id="25969-191">量子 Toffoli 模拟器</span><span class="sxs-lookup"><span data-stu-id="25969-191">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="25969-192">量子全状态模拟器</span><span class="sxs-lookup"><span data-stu-id="25969-192">Quantum full state simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 
