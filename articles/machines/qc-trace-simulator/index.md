---
title: 量子计算机跟踪模拟器
description: 了解如何使用 Microsoft 量子计算机跟踪模拟器来调试经典代码，并估计量子程序的资源要求。
author: vadym-kl
ms.author: vadym@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.machines.qc-trace-simulator.intro
ms.openlocfilehash: 72c259933d2df8f79319e6c0c65ae181a9f9cff3
ms.sourcegitcommit: 9d1c045cf1a2c3e19030cb38dbc7496dbd24ab58
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2020
ms.locfileid: "77906077"
---
# <a name="quantum-trace-simulator"></a><span data-ttu-id="08403-103">量子跟踪模拟器</span><span class="sxs-lookup"><span data-stu-id="08403-103">Quantum Trace Simulator</span></span>

<span data-ttu-id="08403-104">Microsoft 量子计算机跟踪模拟器执行量子程序，而无需实际模拟量子计算机的状态。</span><span class="sxs-lookup"><span data-stu-id="08403-104">The Microsoft quantum computer trace simulator executes a quantum program without actually simulating the state of a quantum computer.</span></span>  <span data-ttu-id="08403-105">出于此原因，跟踪模拟器可以执行使用数千个量子位的量子程序。</span><span class="sxs-lookup"><span data-stu-id="08403-105">For this reason, the trace simulator can execute quantum programs that use thousands of qubits.</span></span>  <span data-ttu-id="08403-106">它适用于两个主要目的：</span><span class="sxs-lookup"><span data-stu-id="08403-106">It is useful for two main purposes:</span></span> 

* <span data-ttu-id="08403-107">调试属于量子程序的一部分的典型代码。</span><span class="sxs-lookup"><span data-stu-id="08403-107">Debugging classical code that is part of a quantum program.</span></span> 
* <span data-ttu-id="08403-108">估计在量子计算机上运行量子程序给定实例所需的资源。</span><span class="sxs-lookup"><span data-stu-id="08403-108">Estimating the resources required to run a given instance of a quantum program on a quantum computer.</span></span>

<span data-ttu-id="08403-109">必须执行度量时，跟踪模拟器依赖于用户提供的其他信息。</span><span class="sxs-lookup"><span data-stu-id="08403-109">The trace simulator relies on additional information provided by the user when measurements must be performed.</span></span> <span data-ttu-id="08403-110">有关详细信息，请参阅[提供度量结果的概率](#providing-the-probability-of-measurement-outcomes)部分。</span><span class="sxs-lookup"><span data-stu-id="08403-110">See Section [Providing the probability of measurement outcomes](#providing-the-probability-of-measurement-outcomes) for more details on this.</span></span> 

## <a name="providing-the-probability-of-measurement-outcomes"></a><span data-ttu-id="08403-111">提供度量结果的概率</span><span class="sxs-lookup"><span data-stu-id="08403-111">Providing the Probability of Measurement Outcomes</span></span>

<span data-ttu-id="08403-112">量子算法中出现两种类型的度量。</span><span class="sxs-lookup"><span data-stu-id="08403-112">There are two kinds of measurements that appear in quantum algorithms.</span></span> <span data-ttu-id="08403-113">第一种类型起到辅助作用，用户通常从中了解结果的概率。</span><span class="sxs-lookup"><span data-stu-id="08403-113">The first kind plays an auxiliary role where the user usually knows the probability of the outcomes.</span></span> <span data-ttu-id="08403-114">在这种情况下，用户可以编写 <xref:microsoft.quantum.intrinsic> 命名空间中的 <xref:microsoft.quantum.intrinsic.assertprob> 来表达此知识。</span><span class="sxs-lookup"><span data-stu-id="08403-114">In this case the user can write <xref:microsoft.quantum.intrinsic.assertprob> from the <xref:microsoft.quantum.intrinsic> namespace to express this knowledge.</span></span> <span data-ttu-id="08403-115">以下示例对此进行了说明：</span><span class="sxs-lookup"><span data-stu-id="08403-115">The following example illustrates this:</span></span>

```qsharp
operation TeleportQubit(source : Qubit, target : Qubit) : Unit {
    using (qubit = Qubit()) {
        H(qubit);
        CNOT(qubit, target);
        CNOT(source, qubit);
        H(source);

        AssertProb([PauliZ], [source], Zero, 0.5, "Outcomes must be equally likely", 1e-5);
        AssertProb([PauliZ], [q], Zero, 0.5, "Outcomes must be equally likely", 1e-5);

        if (M(source) == One)  { Z(target); X(source); }
        if (M(q) == One) { X(target); X(q); }
    }
}
```

<span data-ttu-id="08403-116">当跟踪模拟器执行 `AssertProb` 时，它将在 `source` 上记录测量 `PauliZ`，并且应向 `q` 提供 `Zero` 的结果，其概率为 0.5。</span><span class="sxs-lookup"><span data-stu-id="08403-116">When the trace simulator executes `AssertProb` it will record that measuring `PauliZ` on `source` and `q` should be given an outcome of `Zero` with probability 0.5.</span></span> <span data-ttu-id="08403-117">当模拟器稍后执行 `M` 时，它将找到结果概率的记录值，并且 `M` 将返回 `Zero` 或 `One`，其概率为 0.5。</span><span class="sxs-lookup"><span data-stu-id="08403-117">When the simulator executes `M` later, it will find the recorded values of the outcome probabilities and `M` will return `Zero` or `One` with probability 0.5.</span></span> <span data-ttu-id="08403-118">在跟踪量子状态的模拟器上执行相同的代码时，此类模拟器将检查 `AssertProb` 中提供的概率是否正确。</span><span class="sxs-lookup"><span data-stu-id="08403-118">When the same code is executed on a simulator that keeps track of the quantum state, such a simulator will check that the provided probabilities in `AssertProb` are correct.</span></span>

## <a name="running-your-program-with-the-quantum-computer-trace-simulator"></a><span data-ttu-id="08403-119">使用量子计算机跟踪模拟器运行程序</span><span class="sxs-lookup"><span data-stu-id="08403-119">Running your Program with the Quantum Computer Trace Simulator</span></span> 

<span data-ttu-id="08403-120">量子计算机跟踪模拟器可以被视为另一台目标计算机。</span><span class="sxs-lookup"><span data-stu-id="08403-120">The quantum computer trace simulator may be viewed as just another target machine.</span></span> <span data-ttu-id="08403-121">使用该模拟器的 C# 驱动程序与任何其他量子模拟器的 C# 驱动程序非常相似：</span><span class="sxs-lookup"><span data-stu-id="08403-121">The C# driver program for using it is very similar to the one for any other quantum Simulator:</span></span> 

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
            var res = MyQuantumProgram.Run().Result;
            System.Console.WriteLine("Press any key to continue...");
            System.Console.ReadKey();
        }
    }
}
```

<span data-ttu-id="08403-122">请注意，如果至少有一个度量未使用 `AssertProb` 进行批注，则模拟器将从 `Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators` 命名空间引发 `UnconstrainedMeasurementException`。</span><span class="sxs-lookup"><span data-stu-id="08403-122">Note that if there is at least one measurement not annotated using `AssertProb`, the simulator will throw `UnconstrainedMeasurementException` from the `Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators` namespace.</span></span> <span data-ttu-id="08403-123">请参阅有关 [UnconstrainedMeasurementException](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.UnconstrainedMeasurementException) 的 API 文档以了解更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="08403-123">See the API documentation on [UnconstrainedMeasurementException](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.UnconstrainedMeasurementException) for more details.</span></span>

<span data-ttu-id="08403-124">除了运行量子程序之外，跟踪模拟器还附带了五个用于检测程序中的 bug 和执行量子程序资源估计的组件：</span><span class="sxs-lookup"><span data-stu-id="08403-124">In addition to running quantum programs, the trace simulator comes with five components for detecting bugs in programs and performing quantum program resource estimates:</span></span> 

* [<span data-ttu-id="08403-125">不同输入检查器</span><span class="sxs-lookup"><span data-stu-id="08403-125">Distinct Inputs Checker</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.distinct-inputs)
* [<span data-ttu-id="08403-126">失效的量子位使用检查器</span><span class="sxs-lookup"><span data-stu-id="08403-126">Invalidated Qubits Use Checker</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.invalidated-qubits)
* [<span data-ttu-id="08403-127">基元操作计数器</span><span class="sxs-lookup"><span data-stu-id="08403-127">Primitive Operations Counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.primitive-counter)
* [<span data-ttu-id="08403-128">线路深度计数器</span><span class="sxs-lookup"><span data-stu-id="08403-128">Circuit Depth Counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.depth-counter)
* [<span data-ttu-id="08403-129">线路宽度计数器</span><span class="sxs-lookup"><span data-stu-id="08403-129">Circuit Width Counter</span></span>](xref:microsoft.quantum.machines.qc-trace-simulator.width-counter)

<span data-ttu-id="08403-130">其中每个组件都可以通过在 `QCTraceSimulatorConfiguration` 中设置相应的标志来启用。</span><span class="sxs-lookup"><span data-stu-id="08403-130">Each of these components may be enabled by setting appropriate flags in `QCTraceSimulatorConfiguration`.</span></span> <span data-ttu-id="08403-131">相应的引用文件中提供了有关使用其中每个组件的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="08403-131">More details about using each of these components are provided in the corresponding reference files.</span></span> <span data-ttu-id="08403-132">请参阅有关 [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) 的 API 文档以了解特定详细信息。</span><span class="sxs-lookup"><span data-stu-id="08403-132">See the API documentation on [QCTraceSimulatorConfiguration](https://docs.microsoft.com/dotnet/api/Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulatorConfiguration) for specific details.</span></span>

## <a name="see-also"></a><span data-ttu-id="08403-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="08403-133">See also</span></span>
<span data-ttu-id="08403-134">量子计算机[跟踪模拟器](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) C# 参考</span><span class="sxs-lookup"><span data-stu-id="08403-134">The quantum computer [trace simulator](xref:Microsoft.Quantum.Simulation.Simulators.QCTraceSimulators.QCTraceSimulator) C# reference</span></span> 

