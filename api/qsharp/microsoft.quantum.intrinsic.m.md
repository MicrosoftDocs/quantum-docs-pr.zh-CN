---
uid: Microsoft.Quantum.Intrinsic.M
title: M 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: M
qsharp.summary: >-
  Performs a measurement of a single qubit in the Pauli $Z$ basis.

  The output result is given by the distribution \begin{align} \Pr(\texttt{Zero} | \ket{\psi}) = \braket{\psi | 0} \braket{0 | \psi}. \end{align}
ms.openlocfilehash: 8d4b120385bfc7086a7cb0e3f77034c760d78d92
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699805"
---
# <a name="m-operation"></a>M 操作

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)

软件包 [](https://nuget.org/packages/)


对 Pauli $Z $ basis 中的单个 qubit 进行度量。

输出结果由分发 \begin{align} \Pr ( \texttt{Zero} 提供\ket{\psi} ) = \braket{\psi | 0} \braket{0 | \psi}。
\end{align}

```qsharp
operation M (qubit : Qubit) : Result
```


## <a name="input"></a>输入

### <a name="qubit--qubit"></a>qubit： [qubit](xref:microsoft.quantum.lang-ref.qubit)

要测量的 Qubit。



## <a name="output--__invalidresult__"></a>输出： __无效 <Result>__

`Zero` 如果观察到 $ + $1 eigenvalue，并 `One` 观察到 $-$1 eigenvalue，则为。

## <a name="remarks"></a>注解

等效于：

```qsharp
Measure([PauliZ], [qubit]);
```