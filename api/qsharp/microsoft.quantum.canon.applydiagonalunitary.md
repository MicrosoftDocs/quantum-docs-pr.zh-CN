---
uid: Microsoft.Quantum.Canon.ApplyDiagonalUnitary
title: ApplyDiagonalUnitary 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyDiagonalUnitary
qsharp.summary: Applies an array of complex phases to numeric basis states of a register of qubits.
ms.openlocfilehash: 6ecacf6e4fe2c505036de208c8aeb5350e479e3c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696358"
---
# <a name="applydiagonalunitary-operation"></a>ApplyDiagonalUnitary 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


将复杂阶段数组应用于 qubits 寄存器的数字基础状态。

```qsharp
operation ApplyDiagonalUnitary (coefficients : Double[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>说明

此操作实现在 $n $-qubit number state $ \ket{j} $ 上应用复杂阶段 $e ^ {i \ theta_j} $ 的对角线。
具体而言，此操作可由单一

$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} e ^ {i \ theta_j} \ket{j}\bra{j}。
\end{align} $ $

## <a name="input"></a>输入

### <a name="coefficients--double"></a>系数： [Double](xref:microsoft.quantum.lang-ref.double)[]

最多 $ 2 ^ n $ 系数 $ \ theta_j $ 的数组。 $J $ th 用于索引以小字节序格式编码的数字状态 $ \ket{j} $。


### <a name="qubits--littleendian"></a>qubits： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n 以小字节序格式编码数字状态 $ \ket{j} $ 的 qubit 控制寄存器。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>注解

`coefficients` 如果指定少于 $ 2 ^ n $，则将用元素 $ \ theta_j = $0.0 填充。

## <a name="references"></a>参考

- 量程逻辑电路的合成 Vivek Shende、Stephen Bullock、Igor Markov https://arxiv.org/abs/quant-ph/0406176

## <a name="see-also"></a>另请参阅

- [Canon. ApproximatelyApplyDiagonalUnitary](xref:Microsoft.Quantum.Canon.ApproximatelyApplyDiagonalUnitary)