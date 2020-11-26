---
uid: Microsoft.Quantum.Random.DiscreteUniformDistribution
title: DiscreteUniformDistribution 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive range.
ms.openlocfilehash: 08a62805f59df339ef6b91dff802c40c407808f4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193006"
---
# <a name="discreteuniformdistribution-function"></a><span data-ttu-id="185f5-102">DiscreteUniformDistribution 函数</span><span class="sxs-lookup"><span data-stu-id="185f5-102">DiscreteUniformDistribution function</span></span>

<span data-ttu-id="185f5-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="185f5-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="185f5-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="185f5-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="185f5-105">返回在给定的非独占范围内的统一分布。</span><span class="sxs-lookup"><span data-stu-id="185f5-105">Returns a uniform distribution over a given inclusive range.</span></span>

```qsharp
function DiscreteUniformDistribution (min : Int, max : Int) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a><span data-ttu-id="185f5-106">输入</span><span class="sxs-lookup"><span data-stu-id="185f5-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="185f5-107">min： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="185f5-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="185f5-108">要绘制的最小整数。</span><span class="sxs-lookup"><span data-stu-id="185f5-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="185f5-109">max： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="185f5-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="185f5-110">要绘制的最大整数。</span><span class="sxs-lookup"><span data-stu-id="185f5-110">The largest integer to be drawn.</span></span>



## <a name="output--discretedistribution"></a><span data-ttu-id="185f5-111">输出： [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="185f5-111">Output : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="185f5-112">一种分布，其随机 variates 是从到的非独占概率中的整数 `min` `max` 。</span><span class="sxs-lookup"><span data-stu-id="185f5-112">A distribution whose random variates are integers in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="185f5-113">备注</span><span class="sxs-lookup"><span data-stu-id="185f5-113">Remarks</span></span>

<span data-ttu-id="185f5-114">如果为 `max <= min` ，则失败。</span><span class="sxs-lookup"><span data-stu-id="185f5-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="185f5-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="185f5-115">See Also</span></span>

- [<span data-ttu-id="185f5-116">DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="185f5-116">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)