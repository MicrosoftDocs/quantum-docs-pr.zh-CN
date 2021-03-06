---
uid: Microsoft.Quantum.Intrinsic.Exp
title: Exp 运算
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Exp
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator.

  \begin{align} e^{i \theta [P_0 \otimes P_1 \cdots P_{N-1}]}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: 7aa6974e83e917125b63ef91fb5c3b1238f6e856
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98819011"
---
# <a name="exp-operation"></a>Exp 运算

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)

包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


应用多 qubit Pauli 运算符的幂。

\begin{align} e ^ {i \theta [P_0 \otimes P_1 \cdots P_ {N-1}]}，\end{align}，其中 $P _i $ 是的 $i $ th 元素 `paulis` ，其中 $N = $ `Length(paulis)` 。

```qsharp
operation Exp (paulis : Pauli[], theta : Double, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>输入

### <a name="paulis--pauli"></a>paulis： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Qubit Pauli 值的数组，用于指示每个 qubit 上的 tensor 产品因素。


### <a name="theta--double"></a>theta： [Double](xref:microsoft.quantum.lang-ref.double)

用于旋转目标寄存器的给定多 qubit Pauli 运算符的角度。


### <a name="qubits--qubit"></a>qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

注册以应用给定的旋转。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)

