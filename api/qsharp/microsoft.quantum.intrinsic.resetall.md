---
uid: Microsoft.Quantum.Intrinsic.ResetAll
title: ResetAll 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: ResetAll
qsharp.summary: Given an array of qubits, measure them and ensure they are in the |0⟩ state such that they can be safely released.
ms.openlocfilehash: 2b8e7fc0e7881d8c1bd6f14c150476262b7a2b19
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849319"
---
# <a name="resetall-operation"></a>ResetAll 操作

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)

包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


给定一个 qubits 数组，对其进行度量，确保它们处于 | 0 ⟩状态，以便可以安全地释放它们。

```qsharp
operation ResetAll (qubits : Qubit[]) : Unit
```


## <a name="input"></a>输入

### <a name="qubits--qubit"></a>qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

其状态将重置为 $ \ket $ 的 qubits 的数组 {0} 。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)

