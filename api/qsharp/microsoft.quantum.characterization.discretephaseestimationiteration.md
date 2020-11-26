---
uid: Microsoft.Quantum.Characterization.DiscretePhaseEstimationIteration
title: DiscretePhaseEstimationIteration 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: DiscretePhaseEstimationIteration
qsharp.summary: Performs a single iteration of an iterative (classically-controlled) phase estimation algorithm using integer powers of a unitary oracle.
ms.openlocfilehash: 8ce1e1a2bda6507285f055c87619a8760c891082
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204379"
---
# <a name="discretephaseestimationiteration-operation"></a>DiscretePhaseEstimationIteration 操作

命名空间 [：](xref:Microsoft.Quantum.Characterization)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


使用单一 oracle 的整数幂，对迭代 (经典控制的) 阶段估算算法执行单个迭代。

```qsharp
operation DiscretePhaseEstimationIteration (oracle : Microsoft.Quantum.Oracles.DiscreteOracle, power : Int, theta : Double, targetState : Qubit[], controlQubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>输入

### <a name="oracle--discreteoracle"></a>oracle： [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

对整数和寄存器进行操作，以便将 $U ^ m $ 应用于给定寄存器，其中 $U $ 是要估计其阶段的那个那个，其中 $m $ 是为 oracle 提供的整数幂


### <a name="power--int"></a>幂： [Int](xref:microsoft.quantum.lang-ref.int)

应用给定的单一 oracle 的次数。


### <a name="theta--double"></a>theta： [Double](xref:microsoft.quantum.lang-ref.double)

在操作目标状态之前，要将控制 qubit 上的阶段反转的角度。


### <a name="targetstate--qubit"></a>targetState： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

注册由给定的单一 oracle 处理的状态。


### <a name="controlqubit--qubit"></a>controlQubit： [Qubit](xref:microsoft.quantum.lang-ref.qubit)

用于控制给定 oracle 的应用程序的辅助 qubit。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)

