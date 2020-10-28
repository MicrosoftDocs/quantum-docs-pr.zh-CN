---
uid: Microsoft.Quantum.Random.DrawRandomInt
title: DrawRandomInt 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomInt
qsharp.summary: Draws a random integer in a given inclusive range.
ms.openlocfilehash: d9d8d9fbb25587ac5ccbd4edf0e555649380375f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700905"
---
# <a name="drawrandomint-operation"></a><span data-ttu-id="13691-102">DrawRandomInt 操作</span><span class="sxs-lookup"><span data-stu-id="13691-102">DrawRandomInt operation</span></span>

<span data-ttu-id="13691-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="13691-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="13691-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="13691-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="13691-105">绘制给定范围内的随机整数。</span><span class="sxs-lookup"><span data-stu-id="13691-105">Draws a random integer in a given inclusive range.</span></span>

```qsharp
operation DrawRandomInt (min : Int, max : Int) : Int
```


## <a name="input"></a><span data-ttu-id="13691-106">输入</span><span class="sxs-lookup"><span data-stu-id="13691-106">Input</span></span>

### <a name="min--int"></a><span data-ttu-id="13691-107">min： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="13691-107">min : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="13691-108">要绘制的最小整数。</span><span class="sxs-lookup"><span data-stu-id="13691-108">The smallest integer to be drawn.</span></span>


### <a name="max--int"></a><span data-ttu-id="13691-109">max： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="13691-109">max : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="13691-110">要绘制的最大整数。</span><span class="sxs-lookup"><span data-stu-id="13691-110">The largest integer to be drawn.</span></span>



## <a name="output--int"></a><span data-ttu-id="13691-111">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="13691-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="13691-112">中从到的一个整数，其值 `min` 为 `max` 统一的概率。</span><span class="sxs-lookup"><span data-stu-id="13691-112">An integer in the inclusive range from `min` to `max` with uniform probability.</span></span>

## <a name="remarks"></a><span data-ttu-id="13691-113">注解</span><span class="sxs-lookup"><span data-stu-id="13691-113">Remarks</span></span>

<span data-ttu-id="13691-114">如果为 `max <= min` ，则失败。</span><span class="sxs-lookup"><span data-stu-id="13691-114">Fails if `max <= min`.</span></span>

## <a name="see-also"></a><span data-ttu-id="13691-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="13691-115">See Also</span></span>

- [<span data-ttu-id="13691-116">DiscreteUniformDistribution</span><span class="sxs-lookup"><span data-stu-id="13691-116">Microsoft.Quantum.DiscreteUniformDistribution</span></span>](xref:Microsoft.Quantum.DiscreteUniformDistribution)