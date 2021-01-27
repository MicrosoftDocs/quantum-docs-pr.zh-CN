---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: DrawRandomDouble 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: 792e9c714b761b48618aec2091e167a359c2b522
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847623"
---
# <a name="drawrandomdouble-operation"></a><span data-ttu-id="65905-102">DrawRandomDouble 操作</span><span class="sxs-lookup"><span data-stu-id="65905-102">DrawRandomDouble operation</span></span>

<span data-ttu-id="65905-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="65905-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="65905-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="65905-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="65905-105">以给定的非独占间隔绘制随机实数。</span><span class="sxs-lookup"><span data-stu-id="65905-105">Draws a random real number in a given inclusive interval.</span></span>

```qsharp
operation DrawRandomDouble (min : Double, max : Double) : Double
```


## <a name="input"></a><span data-ttu-id="65905-106">输入</span><span class="sxs-lookup"><span data-stu-id="65905-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="65905-107">min： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="65905-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="65905-108">要绘制的最小实数。</span><span class="sxs-lookup"><span data-stu-id="65905-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="65905-109">max： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="65905-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="65905-110">要绘制的最大实数。</span><span class="sxs-lookup"><span data-stu-id="65905-110">The largest real number to be drawn.</span></span>



## <a name="output--double"></a><span data-ttu-id="65905-111">输出： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="65905-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="65905-112">从到的非独占时间间隔内的随机实数 `min` `max` ，采用统一的概率。</span><span class="sxs-lookup"><span data-stu-id="65905-112">A random real number in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="example"></a><span data-ttu-id="65905-113">示例</span><span class="sxs-lookup"><span data-stu-id="65905-113">Example</span></span>

<span data-ttu-id="65905-114">以下 Q # 代码段随机绘制 $0 $ 和 $2 \pi $ 之间的角度：</span><span class="sxs-lookup"><span data-stu-id="65905-114">The following Q# snippet randomly draws an angle between $0$ and $2 \pi$:</span></span>

```qsharp
let angle = DrawRandomDouble(0.0, 2.0 * PI());
```

## <a name="remarks"></a><span data-ttu-id="65905-115">备注</span><span class="sxs-lookup"><span data-stu-id="65905-115">Remarks</span></span>

<span data-ttu-id="65905-116">如果为 `max <= min` ，则失败。</span><span class="sxs-lookup"><span data-stu-id="65905-116">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="65905-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="65905-117">See Also</span></span>

- [<span data-ttu-id="65905-118">ContinuousUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="65905-118">Microsoft.Quantum.ContinuousUniformDistribution</span></span>](xref:Microsoft.Quantum.ContinuousUniformDistribution)