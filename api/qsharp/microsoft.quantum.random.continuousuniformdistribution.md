---
uid: Microsoft.Quantum.Random.ContinuousUniformDistribution
title: ContinuousUniformDistribution 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive interval.
ms.openlocfilehash: 74300efb10ba7b5aa006f0b1b6aafde0da840f00
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695091"
---
# <a name="continuousuniformdistribution-function"></a><span data-ttu-id="3b76c-102">ContinuousUniformDistribution 函数</span><span class="sxs-lookup"><span data-stu-id="3b76c-102">ContinuousUniformDistribution function</span></span>

<span data-ttu-id="3b76c-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="3b76c-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="3b76c-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3b76c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3b76c-105">返回在给定的非独占时间间隔内的统一分布。</span><span class="sxs-lookup"><span data-stu-id="3b76c-105">Returns a uniform distribution over a given inclusive interval.</span></span>

```qsharp
function ContinuousUniformDistribution (min : Double, max : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="3b76c-106">输入</span><span class="sxs-lookup"><span data-stu-id="3b76c-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="3b76c-107">min： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3b76c-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3b76c-108">要绘制的最小实数。</span><span class="sxs-lookup"><span data-stu-id="3b76c-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="3b76c-109">max： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="3b76c-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="3b76c-110">要绘制的最大实数。</span><span class="sxs-lookup"><span data-stu-id="3b76c-110">The largest real number to be drawn.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="3b76c-111">输出： [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="3b76c-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="3b76c-112">一个分布，其随机 variates 是从到的非独占时间间隔中的实数 `min` `max` 。</span><span class="sxs-lookup"><span data-stu-id="3b76c-112">A distribution whose random variates are real numbers in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="3b76c-113">注解</span><span class="sxs-lookup"><span data-stu-id="3b76c-113">Remarks</span></span>

<span data-ttu-id="3b76c-114">如果为 `max <= min` ，则失败。</span><span class="sxs-lookup"><span data-stu-id="3b76c-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="3b76c-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3b76c-115">See Also</span></span>

- [<span data-ttu-id="3b76c-116">DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="3b76c-116">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)