---
uid: Microsoft.Quantum.ErrorCorrection.DecodeOp
title: DecodeOp 用户定义的类型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: DecodeOp
qsharp.summary: >-
  Represents an operation which decodes an encoded register into a physical register and the scratch qubits used to record a syndrome.

  The argument to a DecodeOp is the same as the return from an EncodeOp, and vice versa.
ms.openlocfilehash: 0733ec016e50a320b162b111c7d87c32140fdacb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695517"
---
# <a name="decodeop-user-defined-type"></a><span data-ttu-id="5e291-102">DecodeOp 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="5e291-102">DecodeOp user defined type</span></span>

<span data-ttu-id="5e291-103">命名空间： [ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="5e291-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="5e291-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5e291-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5e291-105">表示一个操作，该操作将编码的寄存器解码为物理寄存器，并使用 qubits 来记录一个症状。</span><span class="sxs-lookup"><span data-stu-id="5e291-105">Represents an operation which decodes an encoded register into a physical register and the scratch qubits used to record a syndrome.</span></span>

<span data-ttu-id="5e291-106">DecodeOp 的参数与从 EncodeOp 返回的参数相同，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="5e291-106">The argument to a DecodeOp is the same as the return from an EncodeOp, and vice versa.</span></span>

```qsharp

newtype DecodeOp = ((Microsoft.Quantum.ErrorCorrection.LogicalRegister => (Qubit[], Qubit[])));
```
