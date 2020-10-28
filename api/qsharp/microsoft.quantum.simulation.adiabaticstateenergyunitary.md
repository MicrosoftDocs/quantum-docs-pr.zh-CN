---
uid: Microsoft.Quantum.Simulation.AdiabaticStateEnergyUnitary
title: AdiabaticStateEnergyUnitary 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: AdiabaticStateEnergyUnitary
qsharp.summary: Performs state preparation by applying a `statePrepUnitary` on the input state, followed by adiabatic state preparation using a `adiabaticUnitary`, and finally phase estimation with respect to `qpeUnitary`on the resulting state using a `phaseEstAlgorithm`.
ms.openlocfilehash: 642f6a0af76b3b2d0703f0377c379abf33ecee71
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700365"
---
# <a name="adiabaticstateenergyunitary-operation"></a>AdiabaticStateEnergyUnitary 操作

命名空间 [：](xref:Microsoft.Quantum.Simulation)

软件包 [](https://nuget.org/packages/)


通过 `statePrepUnitary` 对输入状态应用，然后使用 adiabatic 状态准备来执行状态准备， `adiabaticUnitary` 并最终使用相对于产生状态的阶段估算 `qpeUnitary` `phaseEstAlgorithm` 。

```qsharp
operation AdiabaticStateEnergyUnitary (statePrepUnitary : (Qubit[] => Unit), adiabaticUnitary : (Qubit[] => Unit), qpeUnitary : (Qubit[] => Unit is Adj + Ctl), phaseEstAlgorithm : ((Microsoft.Quantum.Oracles.DiscreteOracle, Qubit[]) => Double), qubits : Qubit[]) : Double
```


## <a name="input"></a>输入

### <a name="stateprepunitary--qubit--unit"></a>statePrepUnitary： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单元](xref:microsoft.quantum.lang-ref.unit) 

Oracle 表示初始 dynamical 生成器的状态准备。


### <a name="adiabaticunitary--qubit--unit"></a>adiabaticUnitary： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单元](xref:microsoft.quantum.lang-ref.unit) 

Oracle，表示要用于实现到算法最终状态的扫描的 adiabatic 进化算法。


### <a name="qpeunitary--qubit--unit-adj--ctl"></a>qpeUnitary： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl

一种 oracle，表示单一操作员 $U $，表示 dynamical 发电机下的时间 $ \ket{\phi} $ 和接地状态 $E 能量为的演变 \\ 。


### <a name="phaseestalgorithm--discreteoraclequbit--double"></a>phaseEstAlgorithm： ([DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)，[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] ) => [Double](xref:microsoft.quantum.lang-ref.double) 

对给定的单一操作执行阶段估计的操作。
有关更多详细信息，请参阅 [迭代阶段估算](/quantum/libraries/characterization#iterative-phase-estimation) 。


### <a name="qubits--qubit"></a>qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

用于执行模拟的 qubits 寄存器。



## <a name="output--double"></a>输出： [Double](xref:microsoft.quantum.lang-ref.double)

由 $U $ 表示的生成器的 "估计 $ \hat{\phi} $"。