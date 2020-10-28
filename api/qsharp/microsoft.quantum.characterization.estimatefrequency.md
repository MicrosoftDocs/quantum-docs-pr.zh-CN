---
uid: Microsoft.Quantum.Characterization.EstimateFrequency
title: EstimateFrequency 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: EstimateFrequency
qsharp.summary: Given a preparation and measurement, estimates the frequency with which that measurement succeeds (returns `Zero`) by performing a given number of trials.
ms.openlocfilehash: 83589637a7bfa328812207271844411f57d42097
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695899"
---
# <a name="estimatefrequency-operation"></a>EstimateFrequency 操作

命名空间 [：](xref:Microsoft.Quantum.Characterization)

软件包 [](https://nuget.org/packages/)


考虑到准备和度量， `Zero` 通过执行给定数量的试验，估算量化指标成功 (返回) 的频率。

```qsharp
operation EstimateFrequency (preparation : (Qubit[] => Unit), measurement : (Qubit[] => Result), nQubits : Int, nMeasurements : Int) : Double
```


## <a name="input"></a>输入

### <a name="preparation--qubit--unit"></a>准备： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单元](xref:microsoft.quantum.lang-ref.unit) 

操作 $P $，该操作在其输入寄存器上准备给定状态 $ \rho $。


### <a name="measurement--qubit--__invalidresult__"></a>度量： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => __无效 <Result>__ 

操作 $M $ 表示感兴趣的度量。


### <a name="nqubits--int"></a>nQubits： [Int](xref:microsoft.quantum.lang-ref.int)

准备和测量每个操作的 qubits 数目。


### <a name="nmeasurements--int"></a>nMeasurements： [Int](xref:microsoft.quantum.lang-ref.int)

为了估计感兴趣的频率，应执行度量的次数。



## <a name="output--double"></a>输出： [Double](xref:microsoft.quantum.lang-ref.double)

估计 $ \hat{p} $ of $M (P ( \ket{00 \cdots 0} \bra{00 \cdots 0} ) # B3 $ 返回的频率 `Zero` ，使用无偏差二项式估计器 $ \hat{p} = n \_ {\uparrow}/n \_ {\text{measurements}} $，其中 $n \_ {\uparrow} $ 是 `Zero` 观察到的结果数。

这对于遵守物理限制的目标计算机尤其重要，因此无法衡量概率。