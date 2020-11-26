---
uid: Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromPartialReflections
title: AmplitudeAmplificationFromPartialReflections 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmplitudeAmplificationFromPartialReflections
qsharp.summary: Amplitude amplification by partial reflections.
ms.openlocfilehash: 8fa6db7d5616f8c561191e3da00a69b05041b279
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191679"
---
# <a name="amplitudeamplificationfrompartialreflections-function"></a>AmplitudeAmplificationFromPartialReflections 函数

命名空间： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


通过部分反射放大幅度。

```qsharp
function AmplitudeAmplificationFromPartialReflections (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a>输入

### <a name="phases--reflectionphases"></a>阶段： [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

部分反射的阶段


### <a name="startstatereflection--reflectionoracle"></a>startStateReflection： [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

关于开始状态的反射运算符


### <a name="targetstatereflection--reflectionoracle"></a>targetStateReflection： [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

有关目标状态的反射运算符



## <a name="output--qubit--unit--is-adj--ctl"></a>Output： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl

通过部分反射实现波幅放大的操作。

## <a name="remarks"></a>备注

振幅放大是一种特殊的在意波幅放大，其中没有系统 qubits，而在意 oracle 设置为 identity。
在大多数情况下， `startQubits` 在状态 $ \ket{\text{start}} $1 中初始化， \_ 后者是的 $-$1 eigenstate `startStateReflection` 。