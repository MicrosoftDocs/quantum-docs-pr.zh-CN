---
uid: Microsoft.Quantum.Canon.ApplyCNOTChain
title: ApplyCNOTChain 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCNOTChain
qsharp.summary: Computes the parity of a register of qubits in-place.
ms.openlocfilehash: c98fe24ca352952162acb7a9c4fc93d5da4285b8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696373"
---
# <a name="applycnotchain-operation"></a>ApplyCNOTChain 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


计算 qubits 的寄存器的奇偶校验。

```qsharp
operation ApplyCNOTChain (qubits : Qubit[]) : Unit
```


## <a name="description"></a>说明

此操作将其输入的状态转换为 $ $ \begin{align} \ket{q_0} \ket{q_1} \cdots \ket{q_ {n-1}} & \mapsto \ket{q_0} \ket{q_0 \oplus q_1} \ket{q_0 \oplus q_1 \oplus q_2} \cdots \ket{q_0 \oplus \cdots \oplus q_ {n-1}}。
\end{align} $ $

## <a name="input"></a>输入

### <a name="qubits--qubit"></a>qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

要计算和存储其奇偶校验的 qubits 数组。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)

