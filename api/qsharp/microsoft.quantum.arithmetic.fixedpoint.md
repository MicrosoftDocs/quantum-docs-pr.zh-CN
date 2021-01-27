---
uid: Microsoft.Quantum.Arithmetic.FixedPoint
title: FixedPoint 用户定义的类型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: FixedPoint
qsharp.summary: Represents a register of qubits encoding a fixed-point number. Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.
ms.openlocfilehash: 18e85120647c5a1f41ccab5fbfb27ea602a279af
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843204"
---
# <a name="fixedpoint-user-defined-type"></a><span data-ttu-id="54b17-102">FixedPoint 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="54b17-102">FixedPoint user defined type</span></span>

<span data-ttu-id="54b17-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="54b17-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="54b17-104">包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span><span class="sxs-lookup"><span data-stu-id="54b17-104">Package: [Microsoft.Quantum.Numerics](https://nuget.org/packages/Microsoft.Quantum.Numerics)</span></span>


<span data-ttu-id="54b17-105">表示 qubits 编码固定点数字的寄存器。</span><span class="sxs-lookup"><span data-stu-id="54b17-105">Represents a register of qubits encoding a fixed-point number.</span></span> <span data-ttu-id="54b17-106">包含一个整数，该整数等于二进制点左侧的 qubits 数，即，qubits 权重大于或等于1，以及一个量程寄存器。</span><span class="sxs-lookup"><span data-stu-id="54b17-106">Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.</span></span>

```qsharp

newtype FixedPoint = (Int, Qubit[]);
```

