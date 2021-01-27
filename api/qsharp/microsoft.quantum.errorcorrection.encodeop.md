---
uid: Microsoft.Quantum.ErrorCorrection.EncodeOp
title: EncodeOp 用户定义的类型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeOp
qsharp.summary: >-
  Represents an operation which encodes a physical register into a logical register, using the provided scratch qubits.

  The first argument is taken to be the physical register that will be encoded, while the second argument is taken to be the scratch register that will be used.
ms.openlocfilehash: c9959f1afbd44df974c06b79f73eccd090b17985
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98826180"
---
# <a name="encodeop-user-defined-type"></a>EncodeOp 用户定义的类型

命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


表示一个操作，该操作使用提供的草稿 qubits 将物理寄存器编码为逻辑寄存器。

第一个参数被视为将进行编码的物理寄存器，而第二个参数被视为将使用的暂存寄存器。

```qsharp

newtype EncodeOp = (((Qubit[], Qubit[]) => Microsoft.Quantum.ErrorCorrection.LogicalRegister));
```

