---
uid: Microsoft.Quantum.Simulation.InterpolatedEvolution
title: InterpolatedEvolution 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: InterpolatedEvolution
qsharp.summary: Interpolates between two generators with a uniform schedule, returning an operation that applies simulated evolution under the resulting time-dependent generator to a qubit register.
ms.openlocfilehash: 18026b9872f6a3344a1e5c2122f55927975ccb59
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695256"
---
# <a name="interpolatedevolution-function"></a>InterpolatedEvolution 函数

命名空间 [：](xref:Microsoft.Quantum.Simulation)

软件包 [](https://nuget.org/packages/)


使用统一的计划在两个生成器之间进行内插，返回一个操作，该操作在生成的时间依赖生成器下将模拟进化应用于 qubit 寄存器。

```qsharp
function InterpolatedEvolution (interpolationTime : Double, evolutionGeneratorStart : Microsoft.Quantum.Simulation.EvolutionGenerator, evolutionGeneratorEnd : Microsoft.Quantum.Simulation.EvolutionGenerator, timeDependentSimulationAlgorithm : Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a>输入

### <a name="interpolationtime--double"></a>interpolationTime： [Double](xref:microsoft.quantum.lang-ref.double)

执行内插的时间。


### <a name="evolutiongeneratorstart--evolutiongenerator"></a>evolutionGeneratorStart： [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)

用于模拟进化的初始生成器。


### <a name="evolutiongeneratorend--evolutiongenerator"></a>evolutionGeneratorEnd： [EvolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)

用于模拟进化的最终生成器。


### <a name="timedependentsimulationalgorithm--timedependentsimulationalgorithm"></a>timeDependentSimulationAlgorithm： [timeDependentSimulationAlgorithm](xref:Microsoft.Quantum.Simulation.TimeDependentSimulationAlgorithm)

一种依赖于时间的模拟算法，用于模拟统一内插计划期间的演变。



## <a name="output--qubit--unit-adj--ctl"></a>Output： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl



## <a name="remarks"></a>注解

如果选择了内插时间以满足 adiabatic 条件，则此函数将返回一个操作，该操作将为最后一个 dynamical 生成器执行 adiabatic 状态准备。