---
uid: Microsoft.Quantum.Math.Fraction
title: 分式用户定义类型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: a56d28e34938729a8e4ffda5f870e0b6a25be017
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857517"
---
# <a name="fraction-user-defined-type"></a><span data-ttu-id="90da2-102">分式用户定义类型</span><span class="sxs-lookup"><span data-stu-id="90da2-102">Fraction user defined type</span></span>

<span data-ttu-id="90da2-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="90da2-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="90da2-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="90da2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="90da2-105">表示形式的有理数 `p/q` 。</span><span class="sxs-lookup"><span data-stu-id="90da2-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="90da2-106">整数 `p` 是元组的第一个元素， `q` 是元组的第二个元素。</span><span class="sxs-lookup"><span data-stu-id="90da2-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype Fraction = (Numerator : Int, Denominator : Int);
```



## <a name="named-items"></a><span data-ttu-id="90da2-107">命名项</span><span class="sxs-lookup"><span data-stu-id="90da2-107">Named Items</span></span>

### <a name="numerator--int"></a><span data-ttu-id="90da2-108">分子： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="90da2-108">Numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="90da2-109">分数的分子。</span><span class="sxs-lookup"><span data-stu-id="90da2-109">Numerator of the fraction.</span></span>
### <a name="denominator--int"></a><span data-ttu-id="90da2-110">分母： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="90da2-110">Denominator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="90da2-111">分数的分母/</span><span class="sxs-lookup"><span data-stu-id="90da2-111">Denominator of the fraction/</span></span>