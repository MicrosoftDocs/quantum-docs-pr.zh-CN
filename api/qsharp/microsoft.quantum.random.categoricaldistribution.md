---
uid: Microsoft.Quantum.Random.CategoricalDistribution
title: CategoricalDistribution 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: CategoricalDistribution
qsharp.summary: Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.
ms.openlocfilehash: 754ada71078bd5446f78885ace31d92dce6bf1a4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842351"
---
# <a name="categoricaldistribution-function"></a><span data-ttu-id="0527c-102">CategoricalDistribution 函数</span><span class="sxs-lookup"><span data-stu-id="0527c-102">CategoricalDistribution function</span></span>

<span data-ttu-id="0527c-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="0527c-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="0527c-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="0527c-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="0527c-105">返回一个离散分类分布，其中显式指定了给定结果的每个有限列表的概率。</span><span class="sxs-lookup"><span data-stu-id="0527c-105">Returns a discrete categorical distribution, in which the probability for each of a finite list of given outcomes is explicitly specified.</span></span>

```qsharp
function CategoricalDistribution (probs : Double[]) : Microsoft.Quantum.Random.DiscreteDistribution
```


## <a name="input"></a><span data-ttu-id="0527c-106">输入</span><span class="sxs-lookup"><span data-stu-id="0527c-106">Input</span></span>

### <a name="probs--double"></a><span data-ttu-id="0527c-107">probs： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="0527c-107">probs : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="0527c-108">分类分布中每个结果的概率。</span><span class="sxs-lookup"><span data-stu-id="0527c-108">The probabilities for each outcome from the categorical distribution.</span></span>
<span data-ttu-id="0527c-109">这些概率可能不会规范化，但必须全部为非负值。</span><span class="sxs-lookup"><span data-stu-id="0527c-109">These probabilities may not be normalized, but must all be non-negative.</span></span>



## <a name="output--discretedistribution"></a><span data-ttu-id="0527c-110">输出： [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="0527c-110">Output : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="0527c-111">`i`带有概率的索引 `probs[i] / sum` ，其中 `sum` 是给定的和的总和 `probs` `Fold(PlusD, 0.0, probs)` 。</span><span class="sxs-lookup"><span data-stu-id="0527c-111">The index `i` with probability `probs[i] / sum`, where `sum` is the sum of `probs` given by `Fold(PlusD, 0.0, probs)`.</span></span>

## <a name="example"></a><span data-ttu-id="0527c-112">示例</span><span class="sxs-lookup"><span data-stu-id="0527c-112">Example</span></span>

<span data-ttu-id="0527c-113">以下 Q # 代码将显示0，概率为30%，1的概率为70%：</span><span class="sxs-lookup"><span data-stu-id="0527c-113">The following Q# code will display 0 with probability 30% and 1 with probability 70%:</span></span>

```qsharp
let dist = CategoricalDistribution([0.3, 0.7]);
Message($"Got sample: {dist::Sample()}");
```