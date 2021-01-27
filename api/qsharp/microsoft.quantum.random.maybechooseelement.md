---
uid: Microsoft.Quantum.Random.MaybeChooseElement
title: MaybeChooseElement 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: MaybeChooseElement
qsharp.summary: Given an array of data and an a distribution over its indices, attempts to choose an element at random.
ms.openlocfilehash: 86a69110fc92a2b6238cc757c09185c9fbcdb035
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856115"
---
# <a name="maybechooseelement-operation"></a><span data-ttu-id="6bfb7-102">MaybeChooseElement 操作</span><span class="sxs-lookup"><span data-stu-id="6bfb7-102">MaybeChooseElement operation</span></span>

<span data-ttu-id="6bfb7-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="6bfb7-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="6bfb7-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="6bfb7-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="6bfb7-105">给定一个数据数组和一个针对其索引的分布，尝试随机选择一个元素。</span><span class="sxs-lookup"><span data-stu-id="6bfb7-105">Given an array of data and an a distribution over its indices, attempts to choose an element at random.</span></span>

```qsharp
operation MaybeChooseElement<'T> (data : 'T[], indexDistribution : Microsoft.Quantum.Random.DiscreteDistribution) : (Bool, 'T)
```


## <a name="input"></a><span data-ttu-id="6bfb7-106">输入</span><span class="sxs-lookup"><span data-stu-id="6bfb7-106">Input</span></span>

### <a name="data--t"></a><span data-ttu-id="6bfb7-107">数据： t []</span><span class="sxs-lookup"><span data-stu-id="6bfb7-107">data : 'T[]</span></span>

<span data-ttu-id="6bfb7-108">应从中选择元素的数组。</span><span class="sxs-lookup"><span data-stu-id="6bfb7-108">The array from which an element should be chosen.</span></span>


### <a name="indexdistribution--discretedistribution"></a><span data-ttu-id="6bfb7-109">indexDistribution： [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="6bfb7-109">indexDistribution : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="6bfb7-110">索引的分布 `data` 。</span><span class="sxs-lookup"><span data-stu-id="6bfb7-110">A distribution over the indices of `data`.</span></span>



## <a name="output--boolt"></a><span data-ttu-id="6bfb7-111">Output： ([Bool](xref:microsoft.quantum.lang-ref.bool)，不) </span><span class="sxs-lookup"><span data-stu-id="6bfb7-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6bfb7-112">类型参数</span><span class="sxs-lookup"><span data-stu-id="6bfb7-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6bfb7-113">找</span><span class="sxs-lookup"><span data-stu-id="6bfb7-113">'T</span></span>



## <a name="example"></a><span data-ttu-id="6bfb7-114">示例</span><span class="sxs-lookup"><span data-stu-id="6bfb7-114">Example</span></span>

<span data-ttu-id="6bfb7-115">以下 Q # 代码段从数组中随机选择一个元素：</span><span class="sxs-lookup"><span data-stu-id="6bfb7-115">The following Q# snippet chooses an element at random from an array:</span></span>

```qsharp
let (succeeded, element) = MaybeChooseElement(
    data,
    DiscreteUniformDistribution(0, Length(data) - 1)
);
Fact(succeeded, "Index chosen by MaybeChooseElement was not valid.");
```