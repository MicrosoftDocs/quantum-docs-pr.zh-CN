---
uid: Microsoft.Quantum.Math.BigFraction
title: BigFraction 用户定义的类型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BigFraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: a8daa54947097b95040a2dfa7a4d1b90bfaff856
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700492"
---
# <a name="bigfraction-user-defined-type"></a><span data-ttu-id="c2a99-102">BigFraction 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="c2a99-102">BigFraction user defined type</span></span>

<span data-ttu-id="c2a99-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="c2a99-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="c2a99-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c2a99-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c2a99-105">表示形式的有理数 `p/q` 。</span><span class="sxs-lookup"><span data-stu-id="c2a99-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="c2a99-106">整数 `p` 是元组的第一个元素， `q` 是元组的第二个元素。</span><span class="sxs-lookup"><span data-stu-id="c2a99-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype BigFraction = (Numerator : BigInt, Denominator : BigInt);
```



## <a name="named-items"></a><span data-ttu-id="c2a99-107">命名项</span><span class="sxs-lookup"><span data-stu-id="c2a99-107">Named Items</span></span>

### <a name="numerator--bigint"></a><span data-ttu-id="c2a99-108">分子： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="c2a99-108">Numerator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="c2a99-109">分数的分子。</span><span class="sxs-lookup"><span data-stu-id="c2a99-109">Numerator of the fraction.</span></span>
### <a name="denominator--bigint"></a><span data-ttu-id="c2a99-110">分母： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="c2a99-110">Denominator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="c2a99-111">分数的分母/</span><span class="sxs-lookup"><span data-stu-id="c2a99-111">Denominator of the fraction/</span></span>