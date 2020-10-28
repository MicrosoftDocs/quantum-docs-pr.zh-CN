---
uid: Microsoft.Quantum.Arithmetic.FixedPoint
title: FixedPoint 用户定义的类型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: FixedPoint
qsharp.summary: Represents a register of qubits encoding a fixed-point number. Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.
ms.openlocfilehash: f1370cd2f8a7d6488ae0f6be841abd95e61f038e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699876"
---
# <a name="fixedpoint-user-defined-type"></a><span data-ttu-id="62805-102">FixedPoint 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="62805-102">FixedPoint user defined type</span></span>

<span data-ttu-id="62805-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="62805-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="62805-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="62805-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="62805-105">表示 qubits 编码固定点数字的寄存器。</span><span class="sxs-lookup"><span data-stu-id="62805-105">Represents a register of qubits encoding a fixed-point number.</span></span> <span data-ttu-id="62805-106">包含一个整数，该整数等于二进制点左侧的 qubits 数，即，qubits 权重大于或等于1，以及一个量程寄存器。</span><span class="sxs-lookup"><span data-stu-id="62805-106">Consists of an integer that is equal to the number of qubits to the left of the binary point, i.e., qubits of weight greater than or equal to 1, and a quantum register.</span></span>

```qsharp

newtype FixedPoint = (Int, Qubit[]);
```

