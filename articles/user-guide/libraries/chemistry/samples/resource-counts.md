---
title: 获取资源计数
description: 了解如何使用量程跟踪模拟器获取资源估算。
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.resourcecounts
ms.openlocfilehash: 14d0a703a20a801dcee9678a113a33404859a1a9
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274432"
---
# <a name="obtaining-resource-counts"></a><span data-ttu-id="11601-103">获取资源计数</span><span class="sxs-lookup"><span data-stu-id="11601-103">Obtaining resource counts</span></span>

<span data-ttu-id="11601-104">模拟 $n $ qubits 在传统计算机上的成本按 $n $ 进行了线性缩放。</span><span class="sxs-lookup"><span data-stu-id="11601-104">The cost of simulating $n$ qubits on classical computers scales exponentially with $n$.</span></span> <span data-ttu-id="11601-105">这极大地限制了我们可以使用全状态模拟器执行的量程化学模拟的大小。</span><span class="sxs-lookup"><span data-stu-id="11601-105">This greatly limits the size of a quantum chemistry simulation we may perform with the full-state simulator.</span></span> <span data-ttu-id="11601-106">对于较大的化学实例，我们可能会获得有用的信息。</span><span class="sxs-lookup"><span data-stu-id="11601-106">For large instances of chemistry, we may nevertheless obtain useful information.</span></span> <span data-ttu-id="11601-107">在这里，我们将检查如何使用[跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)以自动方式获取用于模拟化学的资源成本（例如，T-SQL 或 cnot-contains 入口的数目）。</span><span class="sxs-lookup"><span data-stu-id="11601-107">Here, we examine how resource costs, such as the number of T-gates or CNOT gates, for simulating chemistry may be obtained in an automated fashion using the [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span> <span data-ttu-id="11601-108">此类信息通知我们以下情况：量程计算机可能足够大，无法运行这些量程化学算法。</span><span class="sxs-lookup"><span data-stu-id="11601-108">Such information informs us of when quantum computers might be large enough to run these quantum chemistry algorithms.</span></span> <span data-ttu-id="11601-109">有关参考，请参阅提供的 `GetGateCount` 示例。</span><span class="sxs-lookup"><span data-stu-id="11601-109">For reference, see the provided `GetGateCount` sample.</span></span>

<span data-ttu-id="11601-110">假设我们已有一个 `FermionHamiltonian` 实例，比如从 Broombridge 架构加载，如 "[从文件加载](xref:microsoft.quantum.chemistry.examples.loadhamiltonian)" 示例中所述。</span><span class="sxs-lookup"><span data-stu-id="11601-110">Let us assume that we already have a `FermionHamiltonian` instance, say, loaded from the Broombridge schema as discussed in the [loading-from-file](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) example.</span></span> 

```csharp
    // Filename of Hamiltonian to be loaded.
    var filename = "...";

    // This deserializes Broombridge.
    var problem = Broombridge.Deserializers.DeserializeBroombridge(filename).ProblemDescriptions.First();

    // This is a data structure representing the Jordan-Wigner encoding 
    // of the Hamiltonian that we may pass to a Q# algorithm.
    var qSharpData = problem.ToQSharpFormat();
```

<span data-ttu-id="11601-111">用于获取资源估算的语法几乎与在全状态模拟器上运行算法完全相同。</span><span class="sxs-lookup"><span data-stu-id="11601-111">The syntax for obtaining resource estimates is almost identical to running the algorithm on the full-state simulator.</span></span> <span data-ttu-id="11601-112">只需选择其他目标计算机。</span><span class="sxs-lookup"><span data-stu-id="11601-112">We simply choose a different target machine.</span></span> <span data-ttu-id="11601-113">出于资源估算的目的，后缀评估单个 Trotter 步骤的成本，或由 Qubitization 技术创建的量程指导。</span><span class="sxs-lookup"><span data-stu-id="11601-113">For the purposes of resource estimates, it suffices to evaluate the cost of a single Trotter step, or a quantum walk created by the Qubitization technique.</span></span> <span data-ttu-id="11601-114">用于调用这些算法的样板如下所示。</span><span class="sxs-lookup"><span data-stu-id="11601-114">The boilerplate for invoking these algorithms is as follows.</span></span>

```qsharp
//////////////////////////////////////////////////////////////////////////
// Using Trotterization //////////////////////////////////////////////////
//////////////////////////////////////////////////////////////////////////

/// # Summary
/// This allocates qubits and applies a single Trotter step.
operation RunTrotterStep (qSharpData: JordanWignerEncodingData) : Unit {
    
    // The data describing the Hamiltonian for all these steps is contained in
    // `qSharpData`
    // We use a Product formula, also known as `Trotterization` to
    // simulate the Hamiltonian.
    // The integrator step size does not affect the gate cost of a single step.
    let trotterStepSize = 1.0;
    
    // Order of integrator
    let trotterOrder = 1;
    let (nQubits, (rescaleFactor, oracle)) = TrotterStepOracle(qSharpData, trotterStepSize, trotterOrder);
    
    // We not allocate qubits an run a single step.
    using (qubits = Qubit[nQubits]) {
        oracle(qubits);
        ResetAll(qubits);
    }
}


//////////////////////////////////////////////////////////////////////////
// Using Qubitization ////////////////////////////////////////////////////
//////////////////////////////////////////////////////////////////////////

/// # Summary
/// This allocates qubits and applies a single qubitization step.
operation RunQubitizationStep (qSharpData: JordanWignerEncodingData) : Double {
    
    // The data describing the Hamiltonian for all these steps is contained in
    // `qSharpData`
    let (nQubits, (l1Norm, oracle)) = QubitizationOracle(qSharpData);
    
    // We now allocate qubits and run a single step.
    using (qubits = Qubit[nQubits]) {
        oracle(qubits);
        ResetAll(qubits);
    }
    
    return l1Norm;
}
```

<span data-ttu-id="11601-115">现在，我们配置跟踪模拟器以跟踪我们感兴趣的资源。</span><span class="sxs-lookup"><span data-stu-id="11601-115">We now configure the trace simulator to track the resources we are interested in.</span></span> <span data-ttu-id="11601-116">在这种情况下，我们通过将标志设置为来计算基元量子运算 `usePrimitiveOperationsCounter` `true` 。</span><span class="sxs-lookup"><span data-stu-id="11601-116">In this case, we count primitive quantum operations by setting the `usePrimitiveOperationsCounter` flag to `true`.</span></span> <span data-ttu-id="11601-117">`throwOnUnconstraintMeasurement` `false` 在 Q # 代码未正确断言度量结果的概率的情况下，技术详细信息设置为，以避免异常。</span><span class="sxs-lookup"><span data-stu-id="11601-117">A technical detail `throwOnUnconstraintMeasurement` is set to `false` to avoid exceptions in cases where the Q# code does not correctly assert of probability of measurement outcomes, if any are performed.</span></span>

```csharp
private static QCTraceSimulator CreateAndConfigureTraceSim()
{
    // Create and configure Trace Simulator
    var config = new QCTraceSimulatorConfiguration()
    {
        usePrimitiveOperationsCounter = true,
        throwOnUnconstraintMeasurement = false
    };

    return new QCTraceSimulator(config);
}
```

<span data-ttu-id="11601-118">现在，我们从驱动程序运行量程算法，如下所示。</span><span class="sxs-lookup"><span data-stu-id="11601-118">We now run the quantum algorithm from the driver program as follows.</span></span>

```csharp
// Instantiate a trace simulator instance
QCTraceSimulator sim = CreateAndConfigureTraceSim();

// Run the quantum algorithm on the trace simulator.
RunQubitizationStep.Run(sim, qSharpData);

// Print all resource counts to file.
var gateStats = sim.ToCSV();
foreach (var x in gateStats)
{
    System.IO.File.WriteAllLines($"QubitizationGateCountEstimates.{x.Key}.csv", new string[] { x.Value });
}
```