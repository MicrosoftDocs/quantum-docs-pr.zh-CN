---
uid: Microsoft.Quantum.Characterization.EstimateOverlapBetweenStates
title: EstimateOverlapBetweenStates 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateOverlapBetweenStates
qsharp.summary: Given two operations which each prepare copies of a state, estimates the squared overlap between the states prepared by each operation.
ms.openlocfilehash: 07693ccf4b8e7bbde189674d9e6b2bf7f92222f6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204294"
---
# <a name="estimateoverlapbetweenstates-operation"></a>EstimateOverlapBetweenStates 操作

命名空间 [：](xref:Microsoft.Quantum.Characterization)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


给定两个操作，每个操作都准备状态的副本，并估计每个操作准备的状态之间的平方重叠。

```qsharp
operation EstimateOverlapBetweenStates (preparation1 : (Qubit[] => Unit is Adj), preparation2 : (Qubit[] => Unit is Adj), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a>输入

### <a name="preparation1--qubit--unit--is-adj"></a>preparation1： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词

要进行比较的两个状态准备操作中的第一个。


### <a name="preparation2--qubit--unit--is-adj"></a>preparation2： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词

要进行比较的两个状态准备操作的第二个。


### <a name="nqubits--int"></a>nQubits： [Int](xref:microsoft.quantum.lang-ref.int)

对其执行、和的 qubits 的数目 `commonPreparation` `preparation1` `preparation2` 。


### <a name="nmeasurements--int"></a>nMeasurements： [Int](xref:microsoft.quantum.lang-ref.int)

要在估计重叠时使用的度量值的数量。



## <a name="output--double"></a>输出： [Double](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>备注

此操作使用交换测试查找 $ $ \begin{align} \left |\braket{00\cdots 0 |V ^ {\dagger} U |00 \ cdots 0} \right | ^ 2 \end{align} $ $，其中 $U $ 是操作的单一表示形式 `preparation1` ，其中 $V $ 对应于 `preparation2` 。

## <a name="see-also"></a>另请参阅

- [EstimateRealOverlapBetweenStates。](xref:Microsoft.Quantum.Characterization.EstimateRealOverlapBetweenStates)
- [EstimateImagOverlapBetweenStates。](xref:Microsoft.Quantum.Characterization.EstimateImagOverlapBetweenStates)