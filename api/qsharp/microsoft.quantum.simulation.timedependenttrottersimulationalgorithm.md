---
uid: Microsoft.Quantum.Simulation.TimeDependentTrotterSimulationAlgorithm
title: TimeDependentTrotterSimulationAlgorithm 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TimeDependentTrotterSimulationAlgorithm
qsharp.summary: '`TimeDependentSimulationAlgorithm` function that uses a Trotter–Suzuki decomposition to approximate a unitary operator that solves the time-dependent Schrodinger equation.'
ms.openlocfilehash: 6129d768276b5c9d96a1b1ed9cd5a6a22d28e286
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696622"
---
# <a name="timedependenttrottersimulationalgorithm-function"></a>TimeDependentTrotterSimulationAlgorithm 函数

命名空间 [：](xref:Microsoft.Quantum.Simulation)

软件包 [](https://nuget.org/packages/)


`TimeDependentSimulationAlgorithm` 使用 Trotter – Suzuki 分解来估算求解依赖于时间的 Schrodinger 公式的单一运算符的函数。

```qsharp
function TimeDependentTrotterSimulationAlgorithm (trotterStepSize : Double, trotterOrder : Int) : Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm
```


## <a name="input"></a>输入

### <a name="trotterstepsize--double"></a>trotterStepSize： [Double](xref:microsoft.quantum.lang-ref.double)

单个 Trotter 步骤中模拟时间演化的持续时间。


### <a name="trotterorder--int"></a>trotterOrder： [Int](xref:microsoft.quantum.lang-ref.int)

Trotter 集成器的顺序。 此值必须是1或偶数。



## <a name="output--timedependentsimulationalgorithm"></a>输出： [TimeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)

`TimeDependentSimulationAlgorithm` 类型。