---
uid: Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates
title: EstimateImagOverlapBetweenStates 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateImagOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the imaginary part of the overlap between the states prepared by each operation.
ms.openlocfilehash: 8b73115c3243c594897ac4b309ec52d5e9863d26
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695893"
---
# <a name="estimateimagoverlapbetweenstates-operation"></a>EstimateImagOverlapBetweenStates 操作

命名空间 [：](xref:Microsoft.Quantum.Characterization)

软件包 [](https://nuget.org/packages/)


假设每个操作都准备好状态的副本，并估计每个操作准备的状态之间重叠部分的虚部。

```qsharp
operation EstimateImagOverlapBetweenStates (commonPreparation : (Qubit[] => Unit is Adj), preparation1 : (Qubit[] => Unit is Adj + Ctl), preparation2 : (Qubit[] => Unit is Adj + Ctl), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a>输入

### <a name="commonpreparation--qubit--unit-adj"></a>commonPreparation： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit) 形容词

准备固定输入状态的操作。


### <a name="preparation1--qubit--unit-adj--ctl"></a>preparation1： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl

要进行比较的两个状态准备操作中的第一个。


### <a name="preparation2--qubit--unit-adj--ctl"></a>preparation2： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl

要进行比较的两个状态准备操作的第二个。


### <a name="nqubits--int"></a>nQubits： [Int](xref:microsoft.quantum.lang-ref.int)

对其执行、和的 qubits 的数目 `commonPreparation` `preparation1` `preparation2` 。


### <a name="nmeasurements--int"></a>nMeasurements： [Int](xref:microsoft.quantum.lang-ref.int)

要在估计重叠时使用的度量值的数量。



## <a name="output--double"></a>输出： [Double](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>注解

此操作使用 Hadamard 测试查找 $ $ \begin{align} \braket{\psi 的虚部 |V ^ {\dagger} U |\psi} \end{align} $ $ 其中 $ \ket{\psi} $ 是准备的状态 `commonPreparation` ，$U $ 是的操作的单一表示形式 `preparation1` ，其中 $V $ 对应于 `preparation2` 。

## <a name="references"></a>参考

- Aharonov *et* [quant/0511096](https://arxiv.org/abs/quant-ph/0511096)。

## <a name="see-also"></a>另请参阅

- [EstimateRealOverlapBetweenStates。](xref:Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates)
- [EstimateOverlapBetweenStates。](xref:Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates)