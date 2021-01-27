---
uid: Microsoft.Quantum.Random.DiscreteUniformDistribution
title: DiscreteUniformDistribution 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DiscreteUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive range.
ms.openlocfilehash: f909e7def5439ec0feef4ca4dc0cf8ed12374dfe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853721"
---
# <a name="discreteuniformdistribution-function"></a><span data-ttu-id="1d441-102">DiscreteUniformDistribution 函数</span><span class="sxs-lookup"><span data-stu-id="1d441-102">DiscreteUniformDistribution function</span></span>

<span data-ttu-id="1d441-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="1d441-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="1d441-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="1d441-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="1d441-105">返回在给定的非独占范围内的统一分布。</span><span class="sxs-lookup"><span data-stu-id="1d441-105">Returns a uniform distribution over a given inclusive range.</span></span>

```qsharp
function DiscreteUniformDistribution (min : Int, max : Int) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a><span data-ttu-id="1d441-106">输入</span><span class="sxs-lookup"><span data-stu-id="1d441-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="1d441-107">min： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1d441-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1d441-108">要绘制的最小整数。</span><span class="sxs-lookup"><span data-stu-id="1d441-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="1d441-109">max： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1d441-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1d441-110">要绘制的最大整数。</span><span class="sxs-lookup"><span data-stu-id="1d441-110">The largest integer to be drawn.</span></span>



## <a name="output--discretedistribution"></a><span data-ttu-id="1d441-111">输出： [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="1d441-111">Output : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="1d441-112">一种分布，其随机 variates 是从到的非独占概率中的整数 `min` `max` 。</span><span class="sxs-lookup"><span data-stu-id="1d441-112">A distribution whose random variates are integers in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="example"></a><span data-ttu-id="1d441-113">示例</span><span class="sxs-lookup"><span data-stu-id="1d441-113">Example</span></span>

<span data-ttu-id="1d441-114">以下 Q # 代码段随机滚动六面骰子：</span><span class="sxs-lookup"><span data-stu-id="1d441-114">The following Q# snippet randomly rolls a six-sided die:</span></span>

```qsharp
let dieDistribution = DiscreteUniformDistribution(1, 6);
let dieRoll = dieDistribution::Sample();
```

## <a name="remarks"></a><span data-ttu-id="1d441-115">备注</span><span class="sxs-lookup"><span data-stu-id="1d441-115">Remarks</span></span>

<span data-ttu-id="1d441-116">如果为 `max <= min` ，则失败。</span><span class="sxs-lookup"><span data-stu-id="1d441-116">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="1d441-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1d441-117">See Also</span></span>

- [<span data-ttu-id="1d441-118">DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="1d441-118">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)