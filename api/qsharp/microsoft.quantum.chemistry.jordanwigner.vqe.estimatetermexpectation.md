---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateTermExpectation
title: EstimateTermExpectation 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateTermExpectation
qsharp.summary: Computes the energy associated to a given Jordan-Wigner Hamiltonian term
ms.openlocfilehash: 3f0ff5037b1424abb6fb318bd49ffd89f545822d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224643"
---
# <a name="estimatetermexpectation-operation"></a>EstimateTermExpectation 操作

命名空间： [JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


计算与给定 Jordan-Wigner Hamiltonian 术语关联的能量

```qsharp
operation EstimateTermExpectation (inputStateUnitary : (Qubit[] => Unit is Adj), ops : Pauli[][], coeffs : Double[], nQubits : Int, nSamples : Int) : Double
```


## <a name="description"></a>描述

此操作估算与每个度量运算符关联的预期值，并使用采样将其与相应的系数相乘。
结果聚合到一个变量中，该变量包含 Jordan-Wigner 术语的能量。

## <a name="input"></a>输入

### <a name="inputstateunitary--qubit--unit--is-adj"></a>inputStateUnitary： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词

用于状态准备的单一。


### <a name="ops--pauli"></a>ops： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[] []

Jordan-Wigner 术语的度量运算符。


### <a name="coeffs--double"></a>coeffs： [Double](xref:microsoft.quantum.lang-ref.double)[]

Jordan-Wigner 项的系数。


### <a name="nqubits--int"></a>nQubits： [Int](xref:microsoft.quantum.lang-ref.int)

模拟分子系统所需的 qubits 数。


### <a name="nsamples--int"></a>nSamples： [Int](xref:microsoft.quantum.lang-ref.int)

要用于预计字词预计的样本数。



## <a name="output--double"></a>输出： [Double](xref:microsoft.quantum.lang-ref.double)

与 Jordan-Wigner 术语关联的能量。