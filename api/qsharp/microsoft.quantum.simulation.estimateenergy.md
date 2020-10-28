---
uid: Microsoft.Quantum.Simulation.EstimateEnergy
title: EstimateEnergy 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: EstimateEnergy
qsharp.summary: Performs state preparation by applying a `statePrepUnitary` on an automatically allocated input state phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.
ms.openlocfilehash: ba4a5372aaf092c3ac3a1302f9715ca643be8436
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700161"
---
# <a name="estimateenergy-operation"></a>EstimateEnergy 操作

命名空间 [：](xref:Microsoft.Quantum.Simulation)

软件包 [](https://nuget.org/packages/)


通过对 `statePrepUnitary` 使用生成的状态的自动分配的输入状态阶段估算应用，来执行状态准备 `qpeUnitary` `phaseEstAlgorithm` 。

```qsharp
operation EstimateEnergy (nQubits : Int, statePrepUnitary : (Qubit[] => Unit), qpeUnitary : (Qubit[] => Unit is Adj + Ctl), phaseEstAlgorithm : ((Microsoft.Quantum.Oracles.DiscreteOracle, Qubit[]) => Double)) : Double
```


## <a name="input"></a>输入

### <a name="nqubits--int"></a>nQubits： [Int](xref:microsoft.quantum.lang-ref.int)

用于执行模拟的 qubits 的数目。


### <a name="stateprepunitary--qubit--unit"></a>statePrepUnitary： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单元](xref:microsoft.quantum.lang-ref.unit) 

Oracle 表示初始 dynamical 生成器的状态准备。


### <a name="qpeunitary--qubit--unit-adj--ctl"></a>qpeUnitary： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl

一种 oracle，表示单一操作员 $U $，表示 dynamical 发电机下的时间 $ \ket{\phi} $ 和接地状态 $E 能量为的演变 \\ 。


### <a name="phaseestalgorithm--discreteoraclequbit--double"></a>phaseEstAlgorithm： ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)，[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] ) => [Double](xref:microsoft.quantum.lang-ref.double) 

对给定的单一操作执行阶段估计的操作。
有关更多详细信息，请参阅 [迭代阶段估算](/quantum/libraries/characterization#iterative-phase-estimation) 。



## <a name="output--double"></a>输出： [Double](xref:microsoft.quantum.lang-ref.double)

由 $U $ 表示的生成器的基本状态能量 $ \phi $ 的估计 $ \hat{\phi} $。