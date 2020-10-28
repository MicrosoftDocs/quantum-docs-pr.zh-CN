---
uid: Microsoft.Quantum.Random.DrawCategorical
title: DrawCategorical 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawCategorical
qsharp.summary: Draws a random sample from a categorical distribution specified by a list of probablities.
ms.openlocfilehash: fdc5ae3a9341cb11e8fda129bdd030289b6c99c2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696691"
---
# <a name="drawcategorical-operation"></a><span data-ttu-id="cac06-102">DrawCategorical 操作</span><span class="sxs-lookup"><span data-stu-id="cac06-102">DrawCategorical operation</span></span>

<span data-ttu-id="cac06-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="cac06-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="cac06-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cac06-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cac06-105">使用 probablities 列表指定的分类分布绘制随机样本。</span><span class="sxs-lookup"><span data-stu-id="cac06-105">Draws a random sample from a categorical distribution specified by a list of probablities.</span></span>

```qsharp
operation DrawCategorical (probs : Double[]) : Int
```


## <a name="description"></a><span data-ttu-id="cac06-106">说明</span><span class="sxs-lookup"><span data-stu-id="cac06-106">Description</span></span>

<span data-ttu-id="cac06-107">选择特定索引的概率与该索引处数组元素的值成正比。</span><span class="sxs-lookup"><span data-stu-id="cac06-107">The probability of selecting a specific index is proportional to the value of the array element at that index.</span></span>
<span data-ttu-id="cac06-108">将忽略等于零的数组元素并从不返回它们的索引。</span><span class="sxs-lookup"><span data-stu-id="cac06-108">Array elements that are equal to zero are ignored and their indices are never returned.</span></span> <span data-ttu-id="cac06-109">如果任何数组元素小于0，或者如果没有数组元素大于零，则操作将失败。</span><span class="sxs-lookup"><span data-stu-id="cac06-109">If any array element is less than zero, or if no array element is greater than zero, then the operation fails.</span></span>

## <a name="input"></a><span data-ttu-id="cac06-110">输入</span><span class="sxs-lookup"><span data-stu-id="cac06-110">Input</span></span>

### <a name="probs--double"></a><span data-ttu-id="cac06-111">probs： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="cac06-111">probs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="cac06-112">浮点数的数组，与选择每个索引的概率成正比。</span><span class="sxs-lookup"><span data-stu-id="cac06-112">An array of floating-point numbers proportional to the probability of selecting each index.</span></span>



## <a name="output--int"></a><span data-ttu-id="cac06-113">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cac06-113">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cac06-114">一个整数 $i $ with probability $ \Pr (i) = p_i/\ sum_i p_i $，其中 $p _i $ 是的 $i $ th 元素 `probs` 。</span><span class="sxs-lookup"><span data-stu-id="cac06-114">An integer $i$ with probability $\Pr(i) = p_i / \sum_i p_i$, where $p_i$ is the $i$th element of `probs`.</span></span>

## <a name="see-also"></a><span data-ttu-id="cac06-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cac06-115">See Also</span></span>

- [<span data-ttu-id="cac06-116">CategoricalDistribution。</span><span class="sxs-lookup"><span data-stu-id="cac06-116">Microsoft.Quantum.Random.CategoricalDistribution</span></span>](xref:Microsoft.Quantum.Random.CategoricalDistribution)