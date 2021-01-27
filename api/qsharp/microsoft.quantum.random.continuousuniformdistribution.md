---
uid: Microsoft.Quantum.Random.ContinuousUniformDistribution
title: ContinuousUniformDistribution 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: ContinuousUniformDistribution
qsharp.summary: Returns a uniform distribution over a given inclusive interval.
ms.openlocfilehash: c81eb433f50277c677756ee70d916f4856260c6d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842317"
---
# <a name="continuousuniformdistribution-function"></a><span data-ttu-id="92774-102">ContinuousUniformDistribution 函数</span><span class="sxs-lookup"><span data-stu-id="92774-102">ContinuousUniformDistribution function</span></span>

<span data-ttu-id="92774-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="92774-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="92774-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="92774-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="92774-105">返回在给定的非独占时间间隔内的统一分布。</span><span class="sxs-lookup"><span data-stu-id="92774-105">Returns a uniform distribution over a given inclusive interval.</span></span>

```qsharp
function ContinuousUniformDistribution (min : Double, max : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="92774-106">输入</span><span class="sxs-lookup"><span data-stu-id="92774-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="92774-107">min： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="92774-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="92774-108">要绘制的最小实数。</span><span class="sxs-lookup"><span data-stu-id="92774-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="92774-109">max： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="92774-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="92774-110">要绘制的最大实数。</span><span class="sxs-lookup"><span data-stu-id="92774-110">The largest real number to be drawn.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="92774-111">输出： [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="92774-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="92774-112">一个分布，其随机 variates 是从到的非独占时间间隔中的实数 `min` `max` 。</span><span class="sxs-lookup"><span data-stu-id="92774-112">A distribution whose random variates are real numbers in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="example"></a><span data-ttu-id="92774-113">示例</span><span class="sxs-lookup"><span data-stu-id="92774-113">Example</span></span>

<span data-ttu-id="92774-114">以下 Q # 代码段随机绘制 $0 $ 和 $2 \pi $ 之间的角度：</span><span class="sxs-lookup"><span data-stu-id="92774-114">The following Q# snippet randomly draws an angle between $0$ and $2 \pi$:</span></span>

```qsharp
let angleDistribution = ContinuousUniformDistribution(0.0, 2.0 * PI());
let angle = angleDistribution::Sample();
```

## <a name="remarks"></a><span data-ttu-id="92774-115">备注</span><span class="sxs-lookup"><span data-stu-id="92774-115">Remarks</span></span>

<span data-ttu-id="92774-116">如果为 `max <= min` ，则失败。</span><span class="sxs-lookup"><span data-stu-id="92774-116">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="92774-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="92774-117">See Also</span></span>

- [<span data-ttu-id="92774-118">DrawRandomDouble</span><span class="sxs-lookup"><span data-stu-id="92774-118">Microsoft.Quantum.DrawRandomDouble</span></span>](xref:Microsoft.Quantum.DrawRandomDouble)