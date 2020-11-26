---
uid: Microsoft.Quantum.Random.DrawRandomDouble
title: DrawRandomDouble 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomDouble
qsharp.summary: Draws a random real number in a given inclusive interval.
ms.openlocfilehash: d62416f4a222716edb9393fe4f43731d0e8aa9d3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192938"
---
# <a name="drawrandomdouble-operation"></a><span data-ttu-id="ee0f5-102">DrawRandomDouble 操作</span><span class="sxs-lookup"><span data-stu-id="ee0f5-102">DrawRandomDouble operation</span></span>

<span data-ttu-id="ee0f5-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="ee0f5-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="ee0f5-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="ee0f5-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="ee0f5-105">以给定的非独占间隔绘制随机实数。</span><span class="sxs-lookup"><span data-stu-id="ee0f5-105">Draws a random real number in a given inclusive interval.</span></span>

```qsharp
operation DrawRandomDouble (min : Double, max : Double) : Double
```


## <a name="input"></a><span data-ttu-id="ee0f5-106">输入</span><span class="sxs-lookup"><span data-stu-id="ee0f5-106">Input</span></span>

### <a name="min--double"></a><span data-ttu-id="ee0f5-107">min： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ee0f5-107">min : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ee0f5-108">要绘制的最小实数。</span><span class="sxs-lookup"><span data-stu-id="ee0f5-108">The smallest real number to be drawn.</span></span>


### <a name="max--double"></a><span data-ttu-id="ee0f5-109">max： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ee0f5-109">max : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ee0f5-110">要绘制的最大实数。</span><span class="sxs-lookup"><span data-stu-id="ee0f5-110">The largest real number to be drawn.</span></span>



## <a name="output--double"></a><span data-ttu-id="ee0f5-111">输出： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ee0f5-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ee0f5-112">从到的非独占时间间隔内的随机实数 `min` `max` ，采用统一的概率。</span><span class="sxs-lookup"><span data-stu-id="ee0f5-112">A random real number in the inclusive interval from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="ee0f5-113">备注</span><span class="sxs-lookup"><span data-stu-id="ee0f5-113">Remarks</span></span>

<span data-ttu-id="ee0f5-114">如果为 `max <= min` ，则失败。</span><span class="sxs-lookup"><span data-stu-id="ee0f5-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="ee0f5-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ee0f5-115">See Also</span></span>

- [<span data-ttu-id="ee0f5-116">ContinuousUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="ee0f5-116">Microsoft.Quantum.ContinuousUniformDistribution</span></span>](xref:Microsoft.Quantum.ContinuousUniformDistribution)