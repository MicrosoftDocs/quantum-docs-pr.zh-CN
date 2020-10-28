---
uid: Microsoft.Quantum.Random.CategoricalDistribution
title: CategoricalDistribution 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: CategoricalDistribution
qsharp.summary: Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.
ms.openlocfilehash: 756e9e95cac5554ab8f885dab7c47ac1b174c0f3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700380"
---
# <a name="categoricaldistribution-function"></a><span data-ttu-id="a6580-102">CategoricalDistribution 函数</span><span class="sxs-lookup"><span data-stu-id="a6580-102">CategoricalDistribution function</span></span>

<span data-ttu-id="a6580-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="a6580-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="a6580-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a6580-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a6580-105">返回一个离散分类分布，其中显式指定了给定结果的每个有限列表的概率。</span><span class="sxs-lookup"><span data-stu-id="a6580-105">Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.</span></span>

```qsharp
function CategoricalDistribution (probs : Double[]) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a><span data-ttu-id="a6580-106">输入</span><span class="sxs-lookup"><span data-stu-id="a6580-106">Input</span></span>

### <a name="probs--double"></a><span data-ttu-id="a6580-107">probs： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="a6580-107">probs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="a6580-108">分类分布中每个结果的概率。</span><span class="sxs-lookup"><span data-stu-id="a6580-108">The probabilities for each outcome from the categorical distribution.</span></span>
<span data-ttu-id="a6580-109">这些概率可能不会规范化，但必须全部为非负值。</span><span class="sxs-lookup"><span data-stu-id="a6580-109">These probabilities may not be normalized, but must all be non-negative.</span></span>



## <a name="output--discretedistribution"></a><span data-ttu-id="a6580-110">输出： [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="a6580-110">Output : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="a6580-111">`i`带有概率的索引 `probs[i] / sum` ，其中 `sum` 是给定的和的总和 `probs` `Fold(PlusD, 0.0, probs)` 。</span><span class="sxs-lookup"><span data-stu-id="a6580-111">The index `i` with probability `probs[i] / sum`, where `sum` is the sum of `probs` given by `Fold(PlusD, 0.0, probs)`.</span></span>