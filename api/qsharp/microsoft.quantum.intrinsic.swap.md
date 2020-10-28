---
uid: Microsoft.Quantum.Intrinsic.SWAP
title: 交换操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: SWAP
qsharp.summary: >-
  Applies the SWAP gate to a pair of qubits.

  \begin{align} \operatorname{SWAP} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{bmatrix}, \end{align}

  where rows and columns are ordered as in the quantum concepts guide.
ms.openlocfilehash: 18b910741e9d0883fc5fcd025eb647407c823269
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696643"
---
# <a name="swap-operation"></a>交换操作

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)

软件包 [](https://nuget.org/packages/)


将交换入口应用于一对 qubits。

\begin{align} \operatorname{SWAP} \mathrel{： =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \end{bmatrix}，\end{align}

行和列的排序顺序，如量程概念指南中所示。

```qsharp
operation SWAP (qubit1 : Qubit, qubit2 : Qubit) : Unit
```


## <a name="input"></a>输入

### <a name="qubit1--qubit"></a>qubit1： [Qubit](xref:microsoft.quantum.lang-ref.qubit)

要交换的第一个 qubit。


### <a name="qubit2--qubit"></a>qubit2： [Qubit](xref:microsoft.quantum.lang-ref.qubit)

要交换的第二个 qubit。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>注解

等效于：

```qsharp
CNOT(qubit1, qubit2);
CNOT(qubit2, qubit1);
CNOT(qubit1, qubit2);
```