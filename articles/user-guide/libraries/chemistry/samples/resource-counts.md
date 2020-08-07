---
title: 获取资源计数
description: 了解如何使用量程跟踪模拟器获取资源估算。
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples.resourcecounts
no-loc:
- Q#
- $$v
ms.openlocfilehash: 35c16e622a390b730ad7385efcc365c212e981fe
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869318"
---
# <a name="obtaining-resource-counts"></a>获取资源计数

模拟 $n $ qubits 在传统计算机上的成本按 $n $ 进行了线性缩放。 这极大地限制了我们可以使用全状态模拟器执行的量程化学模拟的大小。 对于较大的化学实例，我们可能会获得有用的信息。 在这里，我们将检查如何使用[跟踪模拟器](xref:microsoft.quantum.machines.qc-trace-simulator.intro)以自动方式获取用于模拟化学的资源成本（例如，T-SQL 或 cnot-contains 入口的数目）。 此类信息通知我们以下情况：量程计算机可能足够大，无法运行这些量程化学算法。 有关参考，请参阅提供的 `GetGateCount` 示例。

假设我们已有一个 `FermionHamiltonian` 实例，比如从 Broombridge 架构加载，如 "[从文件加载](xref:microsoft.quantum.chemistry.examples.loadhamiltonian)" 示例中所述。 

```csharp
    // Filename of Hamiltonian to be loaded.
    var filename = "...";

    // This deserializes Broombridge.
    var problem = Broombridge.Deserializers.DeserializeBroombridge(filename).ProblemDescriptions.First();

    // This is a data structure representing the Jordan-Wigner encoding 
    // of the Hamiltonian that we may pass to a Q# algorithm.
    var qSharpData = problem.ToQSharpFormat();
```

用于获取资源估算的语法几乎与在全状态模拟器上运行算法完全相同。 只需选择其他目标计算机。 出于资源估算的目的，后缀评估单个 Trotter 步骤的成本，或由 Qubitization 技术创建的量程指导。 用于调用这些算法的样板如下所示。

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

现在，我们配置跟踪模拟器以跟踪我们感兴趣的资源。 在这种情况下，我们通过将标志设置为来计算基元量子运算 `usePrimitiveOperationsCounter` `true` 。 `throwOnUnconstraintMeasurement` `false` 在 Q# 代码未正确断言度量结果的概率的情况下，技术详细信息设置为，以避免异常。

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

现在，我们从驱动程序运行量程算法，如下所示。

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