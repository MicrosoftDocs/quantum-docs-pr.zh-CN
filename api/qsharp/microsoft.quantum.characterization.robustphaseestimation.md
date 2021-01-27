---
uid: Microsoft.Quantum.Characterization.RobustPhaseEstimation
title: RobustPhaseEstimation 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: RobustPhaseEstimation
qsharp.summary: Performs the robust non-iterative quantum phase estimation algorithm for a given oracle `U` and eigenstate, and provides a single real-valued estimate of the phase with variance scaling at the Heisenberg limit.
ms.openlocfilehash: 4b37c8275a5b2aee8534bacc5831281aa498b57d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851797"
---
# <a name="robustphaseestimation-operation"></a>RobustPhaseEstimation 操作

命名空间 [：](xref:Microsoft.Quantum.Characterization)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


为给定的 oracle 和 eigenstate 执行强健的非迭代量程阶段估算算法 `U` ，并提供针对海森堡限制处的变化缩放阶段的单个实际值估算。

```qsharp
operation RobustPhaseEstimation (bitsPrecision : Int, oracle : Microsoft.Quantum.Oracles.DiscreteOracle, targetState : Qubit[]) : Double
```


## <a name="input"></a>输入

### <a name="bitsprecision--int"></a>bitsPrecision： [Int](xref:microsoft.quantum.lang-ref.int)

这将使用标准偏差 $ \sigma \le 2 \ pi/2 ^ \text{bitsPrecision} $ （如 $ \sigma \le 10.7 \pi/\text{# of 查询} $）来估计 $ \phi $ with


### <a name="oracle--discreteoracle"></a>oracle： [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

为给定整数幂运算实现 $U ^ m $ $m $ 的操作。


### <a name="targetstate--qubit"></a>targetState： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

$U $ 作用于的量程寄存器。 如果它存储 $U $ 的 eigenstate $ \ket{\phi} $，则 $U \ket{\phi} = e ^ {i\phi} \ket{\phi} $ for $ \phi\in (-\pi，\pi] $ 未知阶段。



## <a name="output--double"></a>输出： [Double](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>备注

在大量查询的限制中，$ \phi $ 满足 $ \sigma \ge 2 \pi/\text{# of 查询} $ 的估计值的标准偏差 Cramer-Rao 下限。

## <a name="references"></a>参考

- 通过 Shelby Kimmel、Guang 脱离 Hao Low、Theodore Yoder 对通用 Single-Qubit Gate-Set 进行可靠的校准 https://arxiv.org/abs/1502.02677