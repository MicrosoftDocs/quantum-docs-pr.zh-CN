---
uid: Microsoft.Quantum.Simulation.TrotterStepImpl
title: TrotterStepImpl 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterStepImpl
qsharp.summary: Implements time-evolution by a term contained in a `GeneratorSystem`.
ms.openlocfilehash: 1ddd7ab33df243d729b5b48cba393d976bfd3640
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701096"
---
# <a name="trotterstepimpl-operation"></a>TrotterStepImpl 操作

命名空间 [：](xref:Microsoft.Quantum.Simulation)

软件包 [](https://nuget.org/packages/)


通过中包含的术语实现时间演变 `GeneratorSystem` 。

```qsharp
operation TrotterStepImpl (evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, idx : Int, stepsize : Double, qubits : Qubit[]) : Unit
```


## <a name="input"></a>输入

### <a name="evolutiongenerator--evolutiongenerator"></a>evolutionGenerator： [evolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)

要模拟的系统的完整说明。


### <a name="idx--int"></a>idx： [Int](xref:microsoft.quantum.lang-ref.int)

所述系统中某个术语的整数索引。


### <a name="stepsize--double"></a>stepsize： [Double](xref:microsoft.quantum.lang-ref.double)

按术语编制索引的按时间推移的持续时间的乘数 `idx` 。


### <a name="qubits--qubit"></a>qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubits 由模拟处理。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)

