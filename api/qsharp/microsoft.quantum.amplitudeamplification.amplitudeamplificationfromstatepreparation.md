---
uid: Microsoft.Quantum.AmplitudeAmplification.AmplitudeAmplificationFromStatePreparation
title: AmplitudeAmplificationFromStatePreparation 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: AmplitudeAmplificationFromStatePreparation
qsharp.summary: Amplitude amplification by oracles for partial reflections.
ms.openlocfilehash: 30e1cf6e353b8a4491e13a9e2f588ec9cc103cb4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191595"
---
# <a name="amplitudeamplificationfromstatepreparation-function"></a>AmplitudeAmplificationFromStatePreparation 函数

命名空间： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


用于部分反射的 oracles 放大幅度。

```qsharp
function AmplitudeAmplificationFromStatePreparation (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, stateOracle : Microsoft.Quantum.Oracles.StateOracle, idxFlagQubit : Int) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a>输入

### <a name="phases--reflectionphases"></a>阶段： [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

部分反射的阶段


### <a name="stateoracle--stateoracle"></a>stateOracle： [stateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)

准备开始状态的单一 oracle $A $


### <a name="idxflagqubit--int"></a>idxFlagQubit： [Int](xref:microsoft.quantum.lang-ref.int)

用于标记 qubit 的索引



## <a name="output--qubit--unit--is-adj--ctl"></a>Output： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl

实现由部分反射实现的 oracles 放大幅度的操作。

## <a name="remarks"></a>备注

这会在开始和目标状态的形式上强制实施更严格的条件，而不是在中 `AmpAmpByReflectionPhases` 。
假定目标状态标有 $ \ket {1} \_ f $。
假设在 {0} \_ 大多数情况下，\begin{align} A\ket {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ text {target}} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots，\end{align} 在 `flagQubit` `auxiliaryRegister` 状态 $ \ket {0} \_ {f} \ket {0} \_ s $ 中进行初始化。