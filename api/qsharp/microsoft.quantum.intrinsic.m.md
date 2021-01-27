---
uid: Microsoft.Quantum.Intrinsic.M
title: M 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: M
qsharp.summary: >-
  Performs a measurement of a single qubit in the Pauli $Z$ basis.

  The output result is given by the distribution \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}. \end{align}
ms.openlocfilehash: 0037d7f5ad060857c6ca2c863b1d24aca3e338cf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818878"
---
# <a name="m-operation"></a>M 操作

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)

包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


对 Pauli $Z $ basis 中的单个 qubit 进行度量。

输出结果由分发 \begin{align} \Pr ( \texttt{Zero} 提供\ket{\psi} ) = \braket{\psi | 0} \braket{0 | \psi}。
\end{align}

```qsharp
operation M (qubit : Qubit) : Result
```


## <a name="input"></a>输入

### <a name="qubit--qubit"></a>qubit： [qubit](xref:microsoft.quantum.lang-ref.qubit)

要测量的 Qubit。



## <a name="output--__invalidresult__"></a>输出：__无效 <Result>__

`Zero` 如果观察到 $ + $1 eigenvalue，并 `One` 观察到 $-$1 eigenvalue，则为。

## <a name="remarks"></a>备注

等效于：

```qsharp
Measure([PauliZ], [qubit]);
```