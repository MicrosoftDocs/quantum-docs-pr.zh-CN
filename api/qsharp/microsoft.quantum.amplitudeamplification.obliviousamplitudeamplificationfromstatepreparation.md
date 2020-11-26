---
uid: Microsoft.Quantum.AmplitudeAmplification.ObliviousAmplitudeAmplificationFromStatePreparation
title: ObliviousAmplitudeAmplificationFromStatePreparation 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ObliviousAmplitudeAmplificationFromStatePreparation
qsharp.summary: Oblivious amplitude amplification by oracles for partial reflections.
ms.openlocfilehash: 44bb394b0eb4ec98fd47fd1b156410b7a33903f1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191289"
---
# <a name="obliviousamplitudeamplificationfromstatepreparation-function"></a>ObliviousAmplitudeAmplificationFromStatePreparation 函数

命名空间： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


用于部分反射的在意波幅按 oracles 放大。

```qsharp
function ObliviousAmplitudeAmplificationFromStatePreparation (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle, idxFlagQubit : Int) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="input"></a>输入

### <a name="phases--reflectionphases"></a>阶段： [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

部分反射的阶段


### <a name="startstateoracle--deterministicstateoracle"></a>startStateOracle： [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)

准备辅助启动状态的单一 oracle $A $


### <a name="signaloracle--obliviousoracle"></a>signalOracle： [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)

单一 oracle $O 类型 `ObliviousOracle` ，它在辅助和系统寄存器上共同操作


### <a name="idxflagqubit--int"></a>idxFlagQubit： [Int](xref:microsoft.quantum.lang-ref.int)

Qubit 标志注册的索引



## <a name="output--qubitqubit--unit--is-adj--ctl"></a>Output： ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[]，[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] ) => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl

基于部分反射实现在意波幅放大的操作。

## <a name="remarks"></a>备注

这会对辅助启动和目标状态的形式施加更严格的条件，而不是在中 `AmpAmpObliviousByReflectionPhases` 。
假定 $A \ket {0} \_ f\ket {0} \_ A = \ket{\text{start}} \_ {fa} $ 为 \_ 计算基础 $ \ket {0} \_ f\ket $ 准备辅助开始状态 $ \ket{\text{start}} {fa} $ {0} 。
假定目标状态标有 $ \ket {1} \_ f $。
假设 \begin{align} O\ket {\ text {start}} \_ {fa} \ket{\psi} \_ s = \lambda\ket {1} \_ f\ket {\ text {任何}} \_ a\ket {\ text {target}} \_ s U \ket{\psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots，\end{align} 用于某些单一 $U $。