---
uid: Microsoft.Quantum.Canon.ApproximatelyMultiplexPauli
title: ApproximatelyMultiplexPauli 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximatelyMultiplexPauli
qsharp.summary: Applies a Pauli rotation conditioned on an array of qubits, truncating small rotation angles according to a given tolerance.
ms.openlocfilehash: 1fc8a8857b6b37d4c3e812a3c4cb2941b9238800
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844576"
---
# <a name="approximatelymultiplexpauli-operation"></a>ApproximatelyMultiplexPauli 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


应用对 qubits 数组使用的 Pauli 旋转，根据给定的公差截断小旋转角度。

```qsharp
operation ApproximatelyMultiplexPauli (tolerance : Double, coefficients : Double[], pauli : Pauli, control : Microsoft.Quantum.Arithmetic.LittleEndian, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>说明

这会应用一次受控的单一操作，该操作会按角度 $ theta_j \ qubit Pauli operator $P $ （由 $n $-qubit 号 state $ \ket{j} $ 控制）执行旋转。
特别是，此操作的操作由单一

$ $ \begin{align} U = \sum ^ {2 ^ n-1} _ {j = 0} \ket{j}\bra{j} \otimes e ^ {i P \ theta_j}。
\end{align}

##

## <a name="input"></a>输入

### <a name="tolerance--double"></a>容差： [Double](xref:microsoft.quantum.lang-ref.double)

小于其小系数的公差将被截断。


### <a name="coefficients--double"></a>系数： [Double](xref:microsoft.quantum.lang-ref.double)[]

最多 $ 2 ^ n $ 系数 $ \ theta_j $ 的数组。 $J $ th 用于索引以小字节序格式编码的数字状态 $ \ket{j} $。


### <a name="pauli--pauli"></a>pauli： [pauli](xref:microsoft.quantum.lang-ref.pauli)

Pauli 运算符 $P $，它确定旋转的轴。


### <a name="control--littleendian"></a>控件： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n 以小字节序格式编码数字状态 $ \ket{j} $ 的 qubit 控制寄存器。


### <a name="target--qubit"></a>目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)

通过 $e ^ {i P \ theta_j} $ 旋转的单个 qubit 寄存器。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>备注

`coefficients` 如果指定少于 $ 2 ^ n $，则将用元素 $ \ theta_j = $0.0 填充。

## <a name="see-also"></a>另请参阅

- [Canon. MultiplexPauli](xref:Microsoft.Quantum.Canon.MultiplexPauli)