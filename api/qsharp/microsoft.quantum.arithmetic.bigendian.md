---
uid: Microsoft.Quantum.Arithmetic.BigEndian
title: BigEndian 用户定义的类型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: BigEndian
qsharp.summary: Register that encodes an unsigned integer in big-endian order. The qubit with index `0` encodes the highest bit of an unsigned integer.
ms.openlocfilehash: 2f6ec9f83ac124ce9b06c278f8fda820c35c23aa
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843393"
---
# <a name="bigendian-user-defined-type"></a><span data-ttu-id="ef53f-102">BigEndian 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="ef53f-102">BigEndian user defined type</span></span>

<span data-ttu-id="ef53f-103">命名空间 [：](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="ef53f-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="ef53f-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ef53f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ef53f-105">注册以大字节序顺序编码无符号整数。</span><span class="sxs-lookup"><span data-stu-id="ef53f-105">Register that encodes an unsigned integer in big-endian order.</span></span> <span data-ttu-id="ef53f-106">带有索引的 qubit 对 `0` 无符号整数的最高位进行编码。</span><span class="sxs-lookup"><span data-stu-id="ef53f-106">The qubit with index `0` encodes the highest bit of an unsigned integer.</span></span>

```qsharp

newtype BigEndian = (Qubit[]);
```



## <a name="remarks"></a><span data-ttu-id="ef53f-107">备注</span><span class="sxs-lookup"><span data-stu-id="ef53f-107">Remarks</span></span>

<span data-ttu-id="ef53f-108">`BigEndian`与 `BE` 文档中的缩写相同。</span><span class="sxs-lookup"><span data-stu-id="ef53f-108">We abbreviate `BigEndian` as `BE` in the documentation.</span></span>