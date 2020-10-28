---
uid: Microsoft.Quantum.Random.DiscreteUniformDistribution
title: DiscreteUniformDistribution 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive range.
ms.openlocfilehash: 5e93c66d891d9b6aec548c0cf266df35e6090c92
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696693"
---
# <a name="discreteuniformdistribution-function"></a><span data-ttu-id="a1d65-102">DiscreteUniformDistribution 函数</span><span class="sxs-lookup"><span data-stu-id="a1d65-102">DiscreteUniformDistribution function</span></span>

<span data-ttu-id="a1d65-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="a1d65-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="a1d65-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a1d65-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a1d65-105">返回在给定的非独占范围内的统一分布。</span><span class="sxs-lookup"><span data-stu-id="a1d65-105">Returns a uniform distribution over a given inclusive range.</span></span>

```qsharp
function DiscreteUniformDistribution (min : Int, max : Int) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a><span data-ttu-id="a1d65-106">输入</span><span class="sxs-lookup"><span data-stu-id="a1d65-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="a1d65-107">min： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a1d65-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a1d65-108">要绘制的最小整数。</span><span class="sxs-lookup"><span data-stu-id="a1d65-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="a1d65-109">max： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a1d65-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a1d65-110">要绘制的最大整数。</span><span class="sxs-lookup"><span data-stu-id="a1d65-110">The largest integer to be drawn.</span></span>



## <a name="output--discretedistribution"></a><span data-ttu-id="a1d65-111">输出： [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="a1d65-111">Output : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="a1d65-112">一种分布，其随机 variates 是从到的非独占概率中的整数 `min` `max` 。</span><span class="sxs-lookup"><span data-stu-id="a1d65-112">A distribution whose random variates are integers in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="a1d65-113">注解</span><span class="sxs-lookup"><span data-stu-id="a1d65-113">Remarks</span></span>

<span data-ttu-id="a1d65-114">如果为 `max <= min` ，则失败。</span><span class="sxs-lookup"><span data-stu-id="a1d65-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="a1d65-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a1d65-115">See Also</span></span>

- [<span data-ttu-id="a1d65-116">DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="a1d65-116">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)