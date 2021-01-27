---
uid: Microsoft.Quantum.Math.BigFraction
title: BigFraction 用户定义的类型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BigFraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: bfbf49e7a3d060417e506a1977c20adc08b81f0e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846902"
---
# <a name="bigfraction-user-defined-type"></a><span data-ttu-id="05303-102">BigFraction 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="05303-102">BigFraction user defined type</span></span>

<span data-ttu-id="05303-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="05303-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="05303-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="05303-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="05303-105">表示形式的有理数 `p/q` 。</span><span class="sxs-lookup"><span data-stu-id="05303-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="05303-106">整数 `p` 是元组的第一个元素， `q` 是元组的第二个元素。</span><span class="sxs-lookup"><span data-stu-id="05303-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype BigFraction = (Numerator : BigInt, Denominator : BigInt);
```



## <a name="named-items"></a><span data-ttu-id="05303-107">命名项</span><span class="sxs-lookup"><span data-stu-id="05303-107">Named Items</span></span>

### <a name="numerator--bigint"></a><span data-ttu-id="05303-108">分子： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="05303-108">Numerator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="05303-109">分数的分子。</span><span class="sxs-lookup"><span data-stu-id="05303-109">Numerator of the fraction.</span></span>
### <a name="denominator--bigint"></a><span data-ttu-id="05303-110">分母： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="05303-110">Denominator : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="05303-111">分数的分母/</span><span class="sxs-lookup"><span data-stu-id="05303-111">Denominator of the fraction/</span></span>