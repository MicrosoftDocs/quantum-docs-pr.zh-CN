---
uid: Microsoft.Quantum.Math.Fraction
title: 分式用户定义类型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: 350d470c374fc8e0a3f4c4a9a68ad8566ab88727
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700620"
---
# <a name="fraction-user-defined-type"></a><span data-ttu-id="863ea-102">分式用户定义类型</span><span class="sxs-lookup"><span data-stu-id="863ea-102">Fraction user defined type</span></span>

<span data-ttu-id="863ea-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="863ea-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="863ea-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="863ea-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="863ea-105">表示形式的有理数 `p/q` 。</span><span class="sxs-lookup"><span data-stu-id="863ea-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="863ea-106">整数 `p` 是元组的第一个元素， `q` 是元组的第二个元素。</span><span class="sxs-lookup"><span data-stu-id="863ea-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype Fraction = (Numerator : Int, Denominator : Int);
```



## <a name="named-items"></a><span data-ttu-id="863ea-107">命名项</span><span class="sxs-lookup"><span data-stu-id="863ea-107">Named Items</span></span>

### <a name="numerator--int"></a><span data-ttu-id="863ea-108">分子： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="863ea-108">Numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="863ea-109">分数的分子。</span><span class="sxs-lookup"><span data-stu-id="863ea-109">Numerator of the fraction.</span></span>
### <a name="denominator--int"></a><span data-ttu-id="863ea-110">分母： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="863ea-110">Denominator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="863ea-111">分数的分母/</span><span class="sxs-lookup"><span data-stu-id="863ea-111">Denominator of the fraction/</span></span>