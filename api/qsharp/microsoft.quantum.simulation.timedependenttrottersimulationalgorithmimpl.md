---
uid: Microsoft.Quantum.Simulation.TimeDependentTrotterSimulationAlgorithmImpl
title: TimeDependentTrotterSimulationAlgorithmImpl 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentTrotterSimulationAlgorithmImpl
qsharp.summary: Implementation of multiple Trotter steps to approximate a unitary operator that solves the time-dependent Schrödinger equation.
ms.openlocfilehash: c6d1c976d29c69d3ac14d9a2be09826602c8cc1d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696620"
---
# <a name="timedependenttrottersimulationalgorithmimpl-operation"></a>TimeDependentTrotterSimulationAlgorithmImpl 操作

命名空间 [：](xref:Microsoft.Quantum.Simulation)

软件包 [](https://nuget.org/packages/)


实现多个 Trotter 步骤，以近似求解依赖于时间的 Schrödinger 公式的单一运算符。

```qsharp
operation TimeDependentTrotterSimulationAlgorithmImpl (trotterStepSize : Double, trotterOrder : Int, maxTime : Double, evolutionSchedule : Microsoft.Quantum.Simulation.EvolutionSchedule, qubits : Qubit[]) : Unit
```


## <a name="input"></a>输入

### <a name="trotterstepsize--double"></a>trotterStepSize： [Double](xref:microsoft.quantum.lang-ref.double)

单个 Trotter 步骤中模拟时间演化的持续时间。


### <a name="trotterorder--int"></a>trotterOrder： [Int](xref:microsoft.quantum.lang-ref.int)

Trotter 集成器的顺序。 此值必须是1或偶数。


### <a name="maxtime--double"></a>maxTime： [Double](xref:microsoft.quantum.lang-ref.double)

模拟 $t $ 的总持续时间。


### <a name="evolutionschedule--evolutionschedule"></a>evolutionSchedule： [evolutionSchedule](xref:Microsoft.Quantum.Simulation.EvolutionSchedule)

要模拟的与时间相关的系统的完整说明。


### <a name="qubits--qubit"></a>qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubits 由模拟处理。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)

