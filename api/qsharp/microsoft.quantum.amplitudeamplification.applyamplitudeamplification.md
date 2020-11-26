---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyAmplitudeAmplification
title: ApplyAmplitudeAmplification 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyAmplitudeAmplification
qsharp.summary: Applies amplitude amplification on a given register, using a given set of phases and oracles to reflect about the initial and final states.
ms.openlocfilehash: 0b40f94633bb43df5e64cd16d5ac8e12bcd1cc4a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191561"
---
# <a name="applyamplitudeamplification-operation"></a>ApplyAmplitudeAmplification 操作

命名空间： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


在给定寄存器上应用振幅放大，使用一组给定的阶段和 oracles 来反映初始状态和最终状态。

```qsharp
operation ApplyAmplitudeAmplification (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, target : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>输入

### <a name="phases--reflectionphases"></a>阶段： [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

描述振幅放大算法的每个步骤中的部分反射的一组阶段。 有关示例，请参见 @"microsoft.quantum.amplitudeamplification.standardreflectionphases"。


### <a name="startstatereflection--reflectionoracle"></a>startStateReflection： [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

反映初始状态的 oracle。


### <a name="targetstatereflection--reflectionoracle"></a>targetStateReflection： [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

反映所需最终状态的 oracle。


### <a name="target--qubit"></a>target： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

要对其执行振幅放大的寄存器。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)

