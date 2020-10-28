---
uid: Microsoft.Quantum.Intrinsic.Measure
title: 度量运算
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Measure
qsharp.summary: >-
  Performs a joint measurement of one or more qubits in the specified Pauli bases.

  The output result is given by the distribution: \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \frac12 \braket{ \psi \mid| \left( \boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_{N-1} \right) \mid| \psi }, \end{align} where $P_i$ is the $i$th element of `bases`, and where $N = \texttt{Length}(\texttt{bases})$. That is, measurement returns a `Result` $d$ such that the eigenvalue of the observed measurement effect is $(-1)^d$.
ms.openlocfilehash: 56ddfbe5e63692e477ad75bde6b1b16269ed20c0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695380"
---
# <a name="measure-operation"></a>度量运算

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)

软件包 [](https://nuget.org/packages/)


对指定的 Pauli 中的一个或多个 qubits 执行联合度量。

输出结果由分发提供： \begin{align} \Pr ( \texttt{Zero} |\ket{\psi} ) = \frac12 \braket{\psi \mid | \left ( \boldone + P_0 \otimes P_1 \otimes \cdots \otimes P_ {N-1} \right) \mid | \psi}，\end{align} 其中 $P _i $ 是的 $i $ th 元素 `bases` ，其中 $N = \texttt{Length} ( \texttt{bases} ) $。
也就是说，度量值返回 $d $，以使 `Result` 观察到的度量值的 eigenvalue 为 $ (-1) ^ d $。

```qsharp
operation Measure (bases : Pauli[], qubits : Qubit[]) : Result
```


## <a name="input"></a>输入

### <a name="bases--pauli"></a>基： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Qubit Pauli 值的数组，用于指示每个 qubit 上的 tensor 产品因素。


### <a name="qubits--qubit"></a>qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

注册要测量的 qubits。



## <a name="output--__invalidresult__"></a>输出： __无效 <Result>__

`Zero` 如果观察到 $ + $1 eigenvalue，并 `One` 观察到 $-$1 eigenvalue，则为。

## <a name="remarks"></a>注解

如果基础数组和 qubit 数组的长度不同，则操作将失败。