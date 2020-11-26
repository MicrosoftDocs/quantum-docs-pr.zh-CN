---
uid: Microsoft.Quantum.Characterization.EstimateFrequencyA
title: EstimateFrequencyA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateFrequencyA
qsharp.summary: Given a preparation that is adjointable and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.
ms.openlocfilehash: f12fc150de5bcea3d53ce88003c71976d8f2467f
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204345"
---
# <a name="estimatefrequencya-operation"></a>EstimateFrequencyA 操作

命名空间 [：](xref:Microsoft.Quantum.Characterization)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


对于 adjointable 和度量值的准备， `Zero` 通过执行给定数量的试验来估算度量成功 (返回) 的频率。

```qsharp
operation EstimateFrequencyA (preparation : (Qubit[] => Unit is Adj), measurement : (Qubit[] => Result), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a>输入

### <a name="preparation--qubit--unit--is-adj"></a>准备： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词

Adjointable 操作 $P $，该操作在其输入寄存器上准备给定状态 $ \rho $。


### <a name="measurement--qubit--__invalidresult__"></a>度量： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] =>__无效 <Result>__ 

操作 $M $ 表示感兴趣的度量。


### <a name="nqubits--int"></a>nQubits： [Int](xref:microsoft.quantum.lang-ref.int)

准备和测量每个操作的 qubits 数目。


### <a name="nmeasurements--int"></a>nMeasurements： [Int](xref:microsoft.quantum.lang-ref.int)

为了估计感兴趣的频率，应执行度量的次数。



## <a name="output--double"></a>输出： [Double](xref:microsoft.quantum.lang-ref.double)

估计 $ \hat{p} $ of $M (P ( \ket{00 \cdots 0} \bra{00 \cdots 0} ) # B3 $ 返回的频率 `Zero` ，使用无偏差二项式估计器 $ \hat{p} = n \_ {\uparrow}/n \_ {\text{measurements}} $，其中 $n \_ {\uparrow} $ 是 `Zero` 观察到的结果数。

## <a name="remarks"></a>备注

对于 adjointable 操作，可以执行某些假设，如调用操作时，会将 qubits 的状态准备为完全相同的状态，从而使目标计算机能够进行某种性能优化。