---
uid: Microsoft.Quantum.Characterization.ContinuousPhaseEstimationIteration
title: ContinuousPhaseEstimationIteration 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: ContinuousPhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using arbitrary real powers of a unitary oracle.
ms.openlocfilehash: 3c0f6cf084311598346b25dd7028e290946cd87f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216279"
---
# <a name="continuousphaseestimationiteration-operation"></a>ContinuousPhaseEstimationIteration 操作

命名空间 [：](xref:Microsoft.Quantum.Characterization)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


使用单一 oracle 的任意实际幂，执行迭代 (经典控制的) 阶段估算算法的单个迭代。

```qsharp
operation ContinuousPhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.ContinuousOracle, time : Double, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>输入

### <a name="oracle--continuousoracle"></a>oracle： [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)

在双 $t $ 和 a 寄存器上操作的操作，因此 $U ^ t $ 应用于给定寄存器，其中 $U $ 是要估计其阶段的那个那个，其中 $t $ 是给定于 oracle 的整数幂


### <a name="time--double"></a>时间： [Double](xref:microsoft.quantum.lang-ref.double)

应用给定的单一 oracle 的次数。


### <a name="theta--double"></a>theta： [Double](xref:microsoft.quantum.lang-ref.double)

在操作目标状态之前，要将控制 qubit 上的阶段反转的角度。


### <a name="targetstate--qubit"></a>targetState： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

注册由给定的单一 oracle 处理的状态。


### <a name="controlqubit--qubit"></a>controlQubit： [Qubit](xref:microsoft.quantum.lang-ref.qubit)





## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)

