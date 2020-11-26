---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyObliviousAmplitudeAmplification
title: ApplyObliviousAmplitudeAmplification 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyObliviousAmplitudeAmplification
qsharp.summary: Oblivious amplitude amplification by specifying partial reflections.
ms.openlocfilehash: 9b0060201bcdae02a207362a753a0a403cdbb896
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191510"
---
# <a name="applyobliviousamplitudeamplification-operation"></a>ApplyObliviousAmplitudeAmplification 操作

命名空间： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


通过指定部分反射来在意波幅放大。

```qsharp
operation ApplyObliviousAmplitudeAmplification (phases : Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases, startStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, targetStateReflection : Microsoft.Quantum.Oracles.ReflectionOracle, signalOracle : Microsoft.Quantum.Oracles.ObliviousOracle, auxiliaryRegister : Qubit[], systemRegister : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>输入

### <a name="phases--reflectionphases"></a>阶段： [ReflectionPhases](xref:Microsoft.Quantum.AmplitudeAmplification.ReflectionPhases)

部分反射的阶段


### <a name="startstatereflection--reflectionoracle"></a>startStateReflection： [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

有关辅助寄存器开始状态的反射运算符


### <a name="targetstatereflection--reflectionoracle"></a>targetStateReflection： [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

有关辅助寄存器的目标状态的反射运算符


### <a name="signaloracle--obliviousoracle"></a>signalOracle： [ObliviousOracle](xref:Microsoft.Quantum.Oracles.ObliviousOracle)

单一 oracle $O 类型 `ObliviousOracle` ，它在辅助和系统寄存器上共同操作。


### <a name="auxiliaryregister--qubit"></a>auxiliaryRegister： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

辅助寄存器


### <a name="systemregister--qubit"></a>systemRegister： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

系统注册



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>备注

在给定的特定辅助启动状态 $ \ket{\text{start}} $ \_ 、特定辅助目标状态 $ \ket{\text{target}} \_ a $ 和任何系统状态 $ \ket{\psi} \_ s $ 中，假设 \begin{align} O\ket {\ text {start}} \_ a\ket {\ psi} \_ s = \lambda\ket{\text{target}} \_ a U \ket{\psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket{\text{target} ^ \perp} a\cdots \end{align} \_ 用于某些单一 $U $。
通过一系列反射，可以反映辅助寄存器上的起始和目标状态 `signalOracle` 以及其 adjoint 的应用程序，因此可能会更改应用 U 的成功概率。

在大多数情况下， `auxiliaryRegister` 在状态 $ \ket{\text{start}} 中进行初始化 \_ 。

## <a name="references"></a>参考

查看

- [ *D.W. Berry，am Childs，Cleve，Kothari，R.D. Somma，*](https://arxiv.org/abs/1312.1414) 适用于标准版。
  查看
- [ *G.H. Low、I.L. 语*](https://arxiv.org/abs/1610.06546) for 通用化 to partial 反射。