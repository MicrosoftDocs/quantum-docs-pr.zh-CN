---
uid: Microsoft.Quantum.Intrinsic.ExpFrac
title: ExpFrac 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: ExpFrac
qsharp.summary: >-
  Applies the exponential of a multi-qubit Pauli operator with an argument given by a dyadic fraction.

  \begin{align} e^{i \pi k [P_0 \otimes P_1 \cdots P_{N-1}] / 2^n}, \end{align} where $P_i$ is the $i$th element of `paulis`, and where $N = $`Length(paulis)`.
ms.openlocfilehash: 6634caff164c841876fb53e79c3f93254a7d624c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849421"
---
# <a name="expfrac-operation"></a>ExpFrac 操作

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)

包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


使用由 dyadic 分式给定的自变量对 qubit Pauli 运算符应用指数。

\begin{align} e ^ {i \pi k [P_0 \otimes P_1 \cdots P_ {N-1}]/2 ^ N}，\end{align} 其中 $P _i $ 是的 $i $ th 元素 `paulis` ，其中 $N = $ `Length(paulis)` 。

```qsharp
operation ExpFrac (paulis : Pauli[], numerator : Int, power : Int, qubits : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>输入

### <a name="paulis--pauli"></a>paulis： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Qubit Pauli 值的数组，用于指示每个 qubit 上的 tensor 产品因素。


### <a name="numerator--int"></a>分子： [Int](xref:microsoft.quantum.lang-ref.int)

分子 ($k $) ，该角度表示 qubit 寄存器要旋转的角度。


### <a name="power--int"></a>幂： [Int](xref:microsoft.quantum.lang-ref.int)

两个 (的幂 $n $) 指定 qubit 寄存器旋转角度的分母。


### <a name="qubits--qubit"></a>qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

注册以应用给定的旋转。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)

