---
uid: Microsoft.Quantum.ErrorCorrection.EncodeOp
title: EncodeOp 用户定义的类型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: EncodeOp
qsharp.summary: >-
  Represents an operation which encodes a physical register into a logical register, using the provided scratch qubits.

  The first argument is taken to be the physical register that will be encoded, while the second argument is taken to be the scratch register that will be used.
ms.openlocfilehash: da947cdc25cb0edd3a4144022bbfc6ecb84c647f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695508"
---
# <a name="encodeop-user-defined-type"></a><span data-ttu-id="ebd05-102">EncodeOp 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="ebd05-102">EncodeOp user defined type</span></span>

<span data-ttu-id="ebd05-103">命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="ebd05-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="ebd05-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ebd05-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ebd05-105">表示一个操作，该操作使用提供的草稿 qubits 将物理寄存器编码为逻辑寄存器。</span><span class="sxs-lookup"><span data-stu-id="ebd05-105">Represents an operation which encodes a physical register into a logical register, using the provided scratch qubits.</span></span>

<span data-ttu-id="ebd05-106">第一个参数被视为将进行编码的物理寄存器，而第二个参数被视为将使用的暂存寄存器。</span><span class="sxs-lookup"><span data-stu-id="ebd05-106">The first argument is taken to be the physical register that will be encoded, while the second argument is taken to be the scratch register that will be used.</span></span>

```qsharp

newtype EncodeOp = (((Qubit[], Qubit[]) => Microsoft.Quantum.ErrorCorrection.LogicalRegister));
```
