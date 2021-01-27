---
uid: Microsoft.Quantum.Arithmetic.LittleEndian
title: LittleEndian 用户定义的类型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: LittleEndian
qsharp.summary: Register that encodes an unsigned integer in little-endian order. The qubit with index `0` encodes the lowest bit of an unsigned integer.
ms.openlocfilehash: 12bc4dbf830e426365545826575d66a9683cb694
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846568"
---
# <a name="littleendian-user-defined-type"></a><span data-ttu-id="4832d-102">LittleEndian 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="4832d-102">LittleEndian user defined type</span></span>

<span data-ttu-id="4832d-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="4832d-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="4832d-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4832d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4832d-105">注册以小字节序顺序编码无符号整数。</span><span class="sxs-lookup"><span data-stu-id="4832d-105">Register that encodes an unsigned integer in little-endian order.</span></span> <span data-ttu-id="4832d-106">带有索引的 qubit 对 `0` 无符号整数的最小位进行编码。</span><span class="sxs-lookup"><span data-stu-id="4832d-106">The qubit with index `0` encodes the lowest bit of an unsigned integer.</span></span>

```qsharp

newtype LittleEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="4832d-107">备注</span><span class="sxs-lookup"><span data-stu-id="4832d-107">Remarks</span></span>

<span data-ttu-id="4832d-108">`LittleEndian`与 `LE` 文档中的缩写相同。</span><span class="sxs-lookup"><span data-stu-id="4832d-108">We abbreviate `LittleEndian` as `LE` in the documentation.</span></span>