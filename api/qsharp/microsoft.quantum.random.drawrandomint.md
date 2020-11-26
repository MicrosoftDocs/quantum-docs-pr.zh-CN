---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: DrawRandomInt 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: f7b6cb75f761e4c45295245ed4bd4fb82c592809
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192904"
---
# <a name="drawrandomint-operation"></a><span data-ttu-id="ed2c0-102">DrawRandomInt 操作</span><span class="sxs-lookup"><span data-stu-id="ed2c0-102">DrawRandomInt operation</span></span>

<span data-ttu-id="ed2c0-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="ed2c0-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="ed2c0-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="ed2c0-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="ed2c0-105">绘制给定范围内的随机整数。</span><span class="sxs-lookup"><span data-stu-id="ed2c0-105">Draws a random integer in a given inclusive range.</span></span>

```qsharp
operation DrawRandomInt (min : Int, max : Int) : Int
```


## <a name="input"></a><span data-ttu-id="ed2c0-106">输入</span><span class="sxs-lookup"><span data-stu-id="ed2c0-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="ed2c0-107">min： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ed2c0-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ed2c0-108">要绘制的最小整数。</span><span class="sxs-lookup"><span data-stu-id="ed2c0-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="ed2c0-109">max： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ed2c0-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ed2c0-110">要绘制的最大整数。</span><span class="sxs-lookup"><span data-stu-id="ed2c0-110">The largest integer to be drawn.</span></span>



## <a name="output--int"></a><span data-ttu-id="ed2c0-111">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ed2c0-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ed2c0-112">中从到的一个整数，其值 `min` 为 `max` 统一的概率。</span><span class="sxs-lookup"><span data-stu-id="ed2c0-112">An integer in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="ed2c0-113">备注</span><span class="sxs-lookup"><span data-stu-id="ed2c0-113">Remarks</span></span>

<span data-ttu-id="ed2c0-114">如果为 `max <= min` ，则失败。</span><span class="sxs-lookup"><span data-stu-id="ed2c0-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="ed2c0-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ed2c0-115">See Also</span></span>

- [<span data-ttu-id="ed2c0-116">DiscreteUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="ed2c0-116">Microsoft.Quantum.DiscreteUniformDistribution</span></span>](xref:Microsoft.Quantum.DiscreteUniformDistribution)