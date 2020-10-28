---
uid: Microsoft.Quantum.Canon.ApproximatelyMultiplexZ
title: ApproximatelyMultiplexZ 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximatelyMultiplexZ
qsharp.summary: Applies a Pauli Z rotation conditioned on an array of qubits, truncating small rotation angles according to a given tolerance.
ms.openlocfilehash: ac5195b8b3afaad4d41fe50d45652644e2397e1b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696143"
---
# <a name="approximatelymultiplexz-operation"></a>ApproximatelyMultiplexZ 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


对 qubits 数组应用 Pauli Z 旋转，根据给定的公差截断小旋转角度。

```qsharp
operation ApproximatelyMultiplexZ (tolerance : Double, coefficients : Double[], control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit
```


## <a name="description"></a>说明

这将应用按角度 $ \ theta_j $ 来执行循环的多次控制的单一操作，该操作将由 $n $-qubit 号 state $ \ket{j} $ 控制，按角度 $ \ qubit Pauli operator $Z $ 进行旋转。
具体而言，此操作可由单一

$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j} \otimes e ^ {i Z \ theta_j}。
\end{align} $ $

## <a name="input"></a>输入

### <a name="tolerance--double"></a>容差： [Double](xref:microsoft.quantum.lang-ref.double)

小于其小系数的公差将被截断。


### <a name="coefficients--double"></a>系数： [Double](xref:microsoft.quantum.lang-ref.double)[]

最多 $ 2 ^ n $ 系数 $ \ theta_j $ 的数组。 $J $ th 用于索引以小字节序格式编码的数字状态 $ \ket{j} $。


### <a name="control--littleendian"></a>控件： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n 以小字节序格式编码数字状态 $ \ket{j} $ 的 qubit 控制寄存器。


### <a name="target--qubit"></a>目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)

通过 $e ^ {i P \ theta_j} $ 旋转的单个 qubit 寄存器。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>注解

`coefficients` 如果指定少于 $ 2 ^ n $，则将用元素 $ \ theta_j = $0.0 填充。

## <a name="references"></a>参考

- 量程逻辑电路的合成 Vivek Shende、Stephen Bullock、Igor Markov https://arxiv.org/abs/quant-ph/0406176

## <a name="see-also"></a>另请参阅

- [Canon. MultiplexZ](xref:Microsoft.Quantum.Canon.MultiplexZ)