---
uid: Microsoft.Quantum.Math.BigFraction
title: BigFraction 用户定义的类型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BigFraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: 1c9b9e350c4fa3664b2c66da05149005b1170ec3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211077"
---
# <a name="bigfraction-user-defined-type"></a><span data-ttu-id="b14e2-102">BigFraction 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="b14e2-102">BigFraction user defined type</span></span>

<span data-ttu-id="b14e2-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="b14e2-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="b14e2-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b14e2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b14e2-105">表示形式的有理数 `p/q` 。</span><span class="sxs-lookup"><span data-stu-id="b14e2-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="b14e2-106">整数 `p` 是元组的第一个元素， `q` 是元组的第二个元素。</span><span class="sxs-lookup"><span data-stu-id="b14e2-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype BigFraction = (Numerator : BigInt, Denominator : BigInt);
```



## <a name="named-items"></a><span data-ttu-id="b14e2-107">命名项</span><span class="sxs-lookup"><span data-stu-id="b14e2-107">Named Items</span></span>

### <a name="numerator--bigint"></a><span data-ttu-id="b14e2-108">分子： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b14e2-108">Numerator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="b14e2-109">分数的分子。</span><span class="sxs-lookup"><span data-stu-id="b14e2-109">Numerator of the fraction.</span></span>
### <a name="denominator--bigint"></a><span data-ttu-id="b14e2-110">分母： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="b14e2-110">Denominator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="b14e2-111">分数的分母/</span><span class="sxs-lookup"><span data-stu-id="b14e2-111">Denominator of the fraction/</span></span>