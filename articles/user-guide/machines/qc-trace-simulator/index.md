---
title: 量子跟踪模拟器 - Quantum 开发工具包
description: 了解如何使用 Microsoft 量子计算机跟踪模拟器来调试经典代码，并估计 Q# 程序的资源要求。
author: vadym-kl
ms.author: vadym
ms.date: 06/25/2020
ms.topic: conceptual
uid: microsoft.quantum.machines.qc-trace-simulator.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 1e9207d7dcd6ec09353b234654e0567b377144e9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858636"
---
# <a name="microsoft-quantum-development-kit-qdk-quantum-trace-simulator"></a><span data-ttu-id="d1e27-103">Microsoft Quantum 开发工具包 (QDK) 量子跟踪模拟器</span><span class="sxs-lookup"><span data-stu-id="d1e27-103">Microsoft Quantum Development Kit (QDK) quantum trace simulator</span></span>

<span data-ttu-id="d1e27-104">QDK <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> 类运行量子程序，而无需实际模拟量子计算机的状态。</span><span class="sxs-lookup"><span data-stu-id="d1e27-104">The QDK <xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator> class runs a quantum program without actually simulating the state of a quantum computer.</span></span> <span data-ttu-id="d1e27-105">因此，量子跟踪模拟器能够运行使用数千个量子位的量子程序。</span><span class="sxs-lookup"><span data-stu-id="d1e27-105">For this reason, the quantum trace simulator is able to run quantum programs that use thousands of qubits.</span></span>  <span data-ttu-id="d1e27-106">它适用于两个主要目的：</span><span class="sxs-lookup"><span data-stu-id="d1e27-106">It is useful for two main purposes:</span></span> 

* <span data-ttu-id="d1e27-107">调试属于量子程序的一部分的典型代码。</span><span class="sxs-lookup"><span data-stu-id="d1e27-107">Debugging classical code that is part of a quantum program.</span></span> 
* <span data-ttu-id="d1e27-108">估计在量子计算机上运行量子程序给定实例所需的资源。</span><span class="sxs-lookup"><span data-stu-id="d1e27-108">Estimating the resources required to run a given instance of a quantum program on a quantum computer.</span></span> <span data-ttu-id="d1e27-109">事实上，[资源估算器](xref:microsoft.quantum.machines.resources-estimator)（提供更加有限的一组指标）是基于跟踪模拟器构建的。</span><span class="sxs-lookup"><span data-stu-id="d1e27-109">In fact, the [Resources estimator](xref:microsoft.quantum.machines.resources-estimator), which provides a more limited set of metrics, is built upon the trace simulator.</span></span>

## <a name="invoking-the-quantum-trace-simulator"></a><span data-ttu-id="d1e27-110">调用量子跟踪模拟器</span><span class="sxs-lookup"><span data-stu-id="d1e27-110">Invoking the quantum trace simulator</span></span>

<span data-ttu-id="d1e27-111">可以使用量子跟踪模拟器来运行任何 Q# 操作。</span><span class="sxs-lookup"><span data-stu-id="d1e27-111">You can use the quantum trace simulator to run any Q# operation.</span></span>

<span data-ttu-id="d1e27-112">与使用其他目标计算机一样，你首先创建 `QCTraceSimulator` 类的实例，然后将其作为操作的 `Run` 方法的第一个参数传递。</span><span class="sxs-lookup"><span data-stu-id="d1e27-112">As with other target machines, you first create an instance of the `QCTraceSimulator` class and then pass it as the first parameter of an operation's `Run` method.</span></span>

<span data-ttu-id="d1e27-113">请注意，与 `QuantumSimulator` 类不同，`QCTraceSimulator` 类不实现 <xref:System.IDisposable> 接口，因此不需要将其放在 `using` 语句中。</span><span class="sxs-lookup"><span data-stu-id="d1e27-113">Note that, unlike the `QuantumSimulator` class, the `QCTraceSimulator` class does not implement the <xref:System.IDisposable> interface, and thus you do not need to enclose it within a `using` statement.</span></span>

```csharp
using Microsoft.Quantum.Simulation.Core;
using Microsoft.Quantum.Simulation.Simulators;
using Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators;

namespace Quantum.MyProgram
{
    class Driver
    {
        static void Main(string[] args)
        {
            QCTraceSimulator sim = new QCTraceSimulator();
            var res = MyQuantumProgram.Run(sim).Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="d1e27-114">提供测量结果的概率</span><span class="sxs-lookup"><span data-stu-id="d1e27-114">Providing the probability of measurement outcomes</span></span>

<span data-ttu-id="d1e27-115">因为量子跟踪模拟器不模拟实际的量子状态，所以它不能计算某个操作中的测量结果的概率。</span><span class="sxs-lookup"><span data-stu-id="d1e27-115">Because the quantum trace simulator does not simulate the actual quantum state, it cannot calculate the probability of measurement outcomes within an operation.</span></span> 

<span data-ttu-id="d1e27-116">因此，如果某个操作包含测量，你必须使用 <xref:Microsoft.Quantum.Diagnostics> 命名空间中的 <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> 操作显式提供这些概率。</span><span class="sxs-lookup"><span data-stu-id="d1e27-116">Therefore, if an operation includes measurements, you must explicitly provide these probabilities using the <xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability> operation from the <xref:Microsoft.Quantum.Diagnostics> namespace.</span></span> <span data-ttu-id="d1e27-117">以下示例对此进行了说明：</span><span class="sxs-lookup"><span data-stu-id="d1e27-117">The following example illustrates this:</span></span>

```qsharp
operation TeleportQubit(source : Qubit, target : Qubit) : Unit {
    using (qubit = Qubit()) {
        H(qubit);
        CNOT(qubit, target);
        CNOT(source, qubit);
        H(source);

        AssertMeasurementProbability([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertMeasurementProbability([PauliZ], [q], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(q) == One) { X(target); X(q); }
    }
}
```

<span data-ttu-id="d1e27-118">当量子跟踪模拟器遇到 `AssertMeasurementProbability` 时，它将在 `source` 上记录该测量 `PauliZ`，而 `q` 应提供结果 `Zero`，其概率为 **0.5**。</span><span class="sxs-lookup"><span data-stu-id="d1e27-118">When the quantum trace simulator encounters `AssertMeasurementProbability` it records that measuring `PauliZ` on `source` and `q` should give an outcome of `Zero`, with probability **0.5**.</span></span> <span data-ttu-id="d1e27-119">当它稍后运行 `M` 操作时，它会找到结果概率的记录值，而 `M` 将返回 `Zero` 或 `One`，其概率为 **0.5**。</span><span class="sxs-lookup"><span data-stu-id="d1e27-119">When it runs the `M` operation later, it finds the recorded values of the outcome probabilities, and `M` returns `Zero` or `One`, with probability **0.5**.</span></span> <span data-ttu-id="d1e27-120">当相同的代码在跟踪量子状态的模拟器上运行时，该模拟器会检查 `AssertMeasurementProbability` 中提供的概率是否正确。</span><span class="sxs-lookup"><span data-stu-id="d1e27-120">When the same code runs on a simulator that keeps track of the quantum state, that simulator checks that the provided probabilities in `AssertMeasurementProbability` are correct.</span></span>

<span data-ttu-id="d1e27-121">请注意，如果至少有一个测量操作未使用 `AssertMeasurementProbability` 进行批注，则模拟器会引发 [`UnconstrainedMeasurementException`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.unconstrainedmeasurementexception)。</span><span class="sxs-lookup"><span data-stu-id="d1e27-121">Note that if there is at least one measurement operation that is not annotated using `AssertMeasurementProbability`, the simulator throws an [`UnconstrainedMeasurementException`](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.unconstrainedmeasurementexception).</span></span>

## <a name="quantum-trace-simulator-tools"></a><span data-ttu-id="d1e27-122">量子跟踪模拟器工具</span><span class="sxs-lookup"><span data-stu-id="d1e27-122">Quantum trace simulator tools</span></span>

<span data-ttu-id="d1e27-123">QDK 包括五个工具。你可以将这些工具与量子跟踪模拟器一起使用，以便检测程序中的 bug 以及进行量子程序资源估算：</span><span class="sxs-lookup"><span data-stu-id="d1e27-123">The QDK includes five tools that you can use with the quantum trace simulator to detect bugs in your programs and perform quantum program resource estimates:</span></span> 

|<span data-ttu-id="d1e27-124">工具</span><span class="sxs-lookup"><span data-stu-id="d1e27-124">Tool</span></span> | <span data-ttu-id="d1e27-125">说明</span><span class="sxs-lookup"><span data-stu-id="d1e27-125">Description</span></span> |
|-----| -----|
|[<span data-ttu-id="d1e27-126">不同输入检查器</span><span class="sxs-lookup"><span data-stu-id="d1e27-126">Distinct inputs checker</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs) |<span data-ttu-id="d1e27-127">检查是否与共享量子位存在潜在冲突</span><span class="sxs-lookup"><span data-stu-id="d1e27-127">Checks for potential conflicts with shared qubits</span></span> |
|[<span data-ttu-id="d1e27-128">失效的量子位使用检查器</span><span class="sxs-lookup"><span data-stu-id="d1e27-128">Invalidated qubits use checker</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits)  |<span data-ttu-id="d1e27-129">检查程序是否已将操作应用到已释放的量子位</span><span class="sxs-lookup"><span data-stu-id="d1e27-129">Checks if the program applies an operation to a qubit that is already released</span></span> |
|[<span data-ttu-id="d1e27-130">基元操作计数器</span><span class="sxs-lookup"><span data-stu-id="d1e27-130">Primitive operations counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter)  | <span data-ttu-id="d1e27-131">计算在量子程序中调用的每个操作所使用的基元的数目</span><span class="sxs-lookup"><span data-stu-id="d1e27-131">Counts the number of primitives used by every operation invoked in a quantum program</span></span>  |
|[<span data-ttu-id="d1e27-132">深度计数器</span><span class="sxs-lookup"><span data-stu-id="d1e27-132">Depth counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)  |<span data-ttu-id="d1e27-133">收集的计数表示在量子程序中调用的每个操作的深度的下限</span><span class="sxs-lookup"><span data-stu-id="d1e27-133">Gathers counts that represent the lower bound of the depth of every operation invoked in a quantum program</span></span>   |
|[<span data-ttu-id="d1e27-134">宽度计数器</span><span class="sxs-lookup"><span data-stu-id="d1e27-134">Width counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)  |<span data-ttu-id="d1e27-135">计算量子程序中每个操作所分配和借用的量子位数目</span><span class="sxs-lookup"><span data-stu-id="d1e27-135">Counts the number of qubits allocated and borrowed by each operation in a quantum program</span></span> |

<span data-ttu-id="d1e27-136">这些工具中的每一个均可通过以下方法启用：先在 `QCTraceSimulatorConfiguration` 中设置相应的标志，然后将配置传递给 `QCTraceSimulator` 声明。</span><span class="sxs-lookup"><span data-stu-id="d1e27-136">Each of these tools is enabled by setting appropriate flags in `QCTraceSimulatorConfiguration` and then passing the configuration to the `QCTraceSimulator` declaration.</span></span> <span data-ttu-id="d1e27-137">若要了解如何使用这些工具中的每一个，请查看上一列表中的链接。</span><span class="sxs-lookup"><span data-stu-id="d1e27-137">For information on using each of these tools, see the links in the preceding list.</span></span> <span data-ttu-id="d1e27-138">若要详细了解如何配置 `QCTraceSimulator`，请参阅 [QCTraceSimulatorConfiguration](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration)。</span><span class="sxs-lookup"><span data-stu-id="d1e27-138">For more information about configuring `QCTraceSimulator`, see [QCTraceSimulatorConfiguration](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration).</span></span>

## <a name="qctracesimulator-methods"></a><span data-ttu-id="d1e27-139">QCTraceSimulator 方法</span><span class="sxs-lookup"><span data-stu-id="d1e27-139">QCTraceSimulator methods</span></span>

<span data-ttu-id="d1e27-140">`QCTraceSimulator` 有多个内置方法，用于检索在量子操作期间跟踪的指标的值。</span><span class="sxs-lookup"><span data-stu-id="d1e27-140">`QCTraceSimulator` has several built-in methods to retrieve the values of the metrics tracked during a quantum operation.</span></span> <span data-ttu-id="d1e27-141">[QCTraceSimulator.GetMetric](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) 和 [QCTraceSimulator.ToCSV](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.tocsv) 方法的示例可在以下文章中找到：[基元操作计数器](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter)、[深度计数器](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)和[宽度计数器](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)。</span><span class="sxs-lookup"><span data-stu-id="d1e27-141">Examples of the [QCTraceSimulator.GetMetric](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.getmetric) and the [QCTraceSimulator.ToCSV](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulator.tocsv) methods can be found in the [Primitive operations counter](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter), [Depth counter](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter), and [Width counter](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter) articles.</span></span> <span data-ttu-id="d1e27-142">有关所有可用方法的详细信息，请参阅 Q# API 参考中的 [QCTraceSimulator](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator)。</span><span class="sxs-lookup"><span data-stu-id="d1e27-142">For more information on all available methods, see [QCTraceSimulator](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) in the Q# API reference.</span></span>  

## <a name="see-also"></a><span data-ttu-id="d1e27-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d1e27-143">See also</span></span>

- [<span data-ttu-id="d1e27-144">量子资源估算器</span><span class="sxs-lookup"><span data-stu-id="d1e27-144">Quantum resources estimator</span></span>](xref:microsoft.quantum.machines.resources-estimator)
- [<span data-ttu-id="d1e27-145">量子 Toffoli 模拟器</span><span class="sxs-lookup"><span data-stu-id="d1e27-145">Quantum Toffoli simulator</span></span>](xref:microsoft.quantum.machines.toffoli-simulator)
- [<span data-ttu-id="d1e27-146">量子全状态模拟器</span><span class="sxs-lookup"><span data-stu-id="d1e27-146">Quantum full state simulator</span></span>](xref:microsoft.quantum.machines.full-state-simulator) 