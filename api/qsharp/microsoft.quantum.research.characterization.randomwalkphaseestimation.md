---
uid: Microsoft.Quantum.Research.Characterization.RandomWalkPhaseEstimation
title: RandomWalkPhaseEstimation 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Characterization
qsharp.name: RandomWalkPhaseEstimation
qsharp.summary: Performs iterative phase estimation using a random walk to approximate Bayesian inference on the classical measurement results from a given oracle and eigenstate.
ms.openlocfilehash: 5e0c0871b916ff51b85dec8703111788b5204bc6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695298"
---
# <a name="randomwalkphaseestimation-operation"></a>RandomWalkPhaseEstimation 操作

命名空间 [： ...](xref:Microsoft.Quantum.Research.Characterization)

软件包 [](https://nuget.org/packages/)


执行迭代阶段估算，并使用随机遍历来估算给定 oracle 和 eigenstate 的传统测量结果中的 Bayesian 推理。

```qsharp
operation RandomWalkPhaseEstimation (initialMean : Double, initialStdDev : Double, nMeasurements : Int, maxMeasurements : Int, unwind : Int, oracle : Microsoft.Quantum.Oracles.ContinuousOracle, targetState : Qubit[]) : Double
```


## <a name="input"></a>输入

### <a name="initialmean--double"></a>initialMean： [Double](xref:microsoft.quantum.lang-ref.double)

$ \Phi $ 前面初始正常分布的平均值。


### <a name="initialstddev--double"></a>initialStdDev： [Double](xref:microsoft.quantum.lang-ref.double)

在 $ \phi $ 之前的初始正常之前的标准偏差。


### <a name="nmeasurements--int"></a>nMeasurements： [Int](xref:microsoft.quantum.lang-ref.int)

要接受到最终后验估计值的度量值的数量。


### <a name="maxmeasurements--int"></a>maxMeasurements： [Int](xref:microsoft.quantum.lang-ref.int)

在操作被视为失败之前可以执行的度量总数。


### <a name="unwind--int"></a>展开： [Int](xref:microsoft.quantum.lang-ref.int)

一致性检查失败时要记住的结果数。


### <a name="oracle--continuousoracle"></a>oracle： [ContinuousOracle](xref:Microsoft.Quantum.Oracles.ContinuousOracle)

表示单一 $U $ 的操作，$U (t) \ket{\phi} = e ^ {\phi}\ket{\phi} $ for eigenstates $ \ket{\phi} $，其中包含未知阶段 $ \phi \in \mathbb{R} ^ + $。


### <a name="targetstate--qubit"></a>targetState： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

$U $ 操作的寄存器。



## <a name="output--double"></a>输出： [Double](xref:microsoft.quantum.lang-ref.double)

最终的估计 $ \hat{\phi} \mathrel{： =} \expect [\phi] $，其中，假定所有接受的数据都超出了后验。

## <a name="remarks"></a>注解

### <a name="iterative-phase-estimation-and-eigenstates"></a>迭代阶段估计和 Eigenstates

通常，输入寄存器 `eigenstate` 不需要是 $U $ 的 eigenstate $ \ket{\phi} $，但可以是 eigenstates 上的 superposition。 假设输入状态由 \begin{align} \ket{\psi} & = \sum \_ {j} \alpha \_ j \ket{\phi \_ j}，\end{align}，其中 $ \{ \alpha \_ j \} $ 是复数系数，如 $ \sum \_ j | \alpha \_ j | ^ 2 = $1，其中 $U \ket{\phi \_ j} = \phi \_ j\ket {\ phi \_ j} $。

然后，执行迭代阶段估算最终将聚合到单个 eigenstate，如 [开发指南](xref:microsoft.quantum.libraries.characterization#iterative-phase-estimation-without-eigenstates)中所述。

### <a name="experiment-design"></a>试验设计

根据粒子推测试探法 $ \theta $ 传递到的度量 $t 时间 $ $ `oracle` ， *particle guess heuristic* \Begin{align} \theta \sim \Pr ( \phi) ，\quad t \approx \frac {1} {\variance{\phi}}。
\end{align} 这种试探的最佳做法是，在以前的假设条件下，使用迭代阶段估算来减少预期的后验方差。

### <a name="optimality"></a>最优性

此操作近似于阶段 $ \phi $ 的最佳估计器，因为使用二次丢失 $L ( \phi，\hat{\phi} ) \mathrel{： =} ( \phi-\hat{\phi} ) ^ $2。

有关迭代阶段估算统计信息的详细信息，请参阅 [Bayesian 阶段估算](xref:microsoft.quantum.libraries.characterization#bayesian-phase-estimation) 。

## <a name="references"></a>参考

- Ferrie *et al.* 2011 [doi>10.1145： 10/tfx-cli](https://doi.org/10.1007/s11128-012-0407-6)， [arXiv： 1110.3067](https://arxiv.org/abs/1110.3067)。
- Wiebe *et al.* 2013 [doi>10.1145： 10/tf3](https://doi.org/10.1103/PhysRevLett.112.190501)、 [arXiv： 1309.0876](https://arxiv.org/abs/1309.0876)
- Wiebe 和 Granade 2018 *(准备)* 。