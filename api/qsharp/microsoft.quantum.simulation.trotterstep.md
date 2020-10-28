---
uid: Microsoft.Quantum.Simulation.TrotterStep
title: TrotterStep 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: TrotterStep
qsharp.summary: Implements a single time-step of time-evolution by the system described in an `EvolutionGenerator` using a Trotter–Suzuki decomposition.
ms.openlocfilehash: 7a1a27ba4dc4b8b7bbc4da6a378d4a1494bc9415
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701104"
---
# <a name="trotterstep-function"></a>TrotterStep 函数

命名空间 [：](xref:Microsoft.Quantum.Simulation)

软件包 [](https://nuget.org/packages/)


使用 Trotter – Suzuki 分解中所述的系统实现一次时间演变 `EvolutionGenerator` 。

```qsharp
function TrotterStep (evolutionGenerator : Microsoft.Quantum.Simulation.EvolutionGenerator, trotterOrder : Int, trotterStepSize : Double) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a>输入

### <a name="evolutiongenerator--evolutiongenerator"></a>evolutionGenerator： [evolutionGenerator](xref:Microsoft.Quantum.Simulation.EvolutionGenerator)

要模拟的系统的完整说明。


### <a name="trotterorder--int"></a>trotterOrder： [Int](xref:microsoft.quantum.lang-ref.int)

Trotter 集成器的顺序。 此值必须是1或偶数。


### <a name="trotterstepsize--double"></a>trotterStepSize： [Double](xref:microsoft.quantum.lang-ref.double)

单个 Trotter 步骤中模拟时间演化的持续时间。



## <a name="output--qubit--unit-adj--ctl"></a>Output： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl

一项操作，该操作约为持续时间演化的单个步骤 `trotterStepSize` 。

## <a name="remarks"></a>注解

有关 Trotter – Suzuki 分解的详细信息，请参阅 [按时间排序的组合](/quantum/libraries/control-flow#time-ordered-composition)。