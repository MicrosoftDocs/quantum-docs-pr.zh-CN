---
uid: Microsoft.Quantum.Arithmetic.LittleEndian
title: LittleEndian 用户定义的类型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: LittleEndian
qsharp.summary: Register that encodes an unsigned integer in little-endian order. The qubit with index `0` encodes the lowest bit of an unsigned integer.
ms.openlocfilehash: 2a00e499bf59e6d22a774706331737461e8e95e1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96222773"
---
# <a name="littleendian-user-defined-type"></a><span data-ttu-id="24c66-102">LittleEndian 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="24c66-102">LittleEndian user defined type</span></span>

<span data-ttu-id="24c66-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="24c66-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="24c66-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="24c66-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="24c66-105">注册以小字节序顺序编码无符号整数。</span><span class="sxs-lookup"><span data-stu-id="24c66-105">Register that encodes an unsigned integer in little-endian order.</span></span> <span data-ttu-id="24c66-106">带有索引的 qubit 对 `0` 无符号整数的最小位进行编码。</span><span class="sxs-lookup"><span data-stu-id="24c66-106">The qubit with index `0` encodes the lowest bit of an unsigned integer.</span></span>

```qsharp

newtype LittleEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="24c66-107">备注</span><span class="sxs-lookup"><span data-stu-id="24c66-107">Remarks</span></span>

<span data-ttu-id="24c66-108">`LittleEndian`与 `LE` 文档中的缩写相同。</span><span class="sxs-lookup"><span data-stu-id="24c66-108">We abbreviate `LittleEndian` as `LE` in the documentation.</span></span>