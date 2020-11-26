---
uid: Microsoft.Quantum.Random.MaybeChooseElement
title: MaybeChooseElement 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: MaybeChooseElement
qsharp.summary: Given an array of data and an a distribution over its indices, attempts to choose an element at random.
ms.openlocfilehash: 1a69c8d5a6ae022ceda9269e17434b740809b107
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192853"
---
# <a name="maybechooseelement-operation"></a><span data-ttu-id="160ff-102">MaybeChooseElement 操作</span><span class="sxs-lookup"><span data-stu-id="160ff-102">MaybeChooseElement operation</span></span>

<span data-ttu-id="160ff-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="160ff-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="160ff-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="160ff-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="160ff-105">给定一个数据数组和一个针对其索引的分布，尝试随机选择一个元素。</span><span class="sxs-lookup"><span data-stu-id="160ff-105">Given an array of data and an a distribution over its indices, attempts to choose an element at random.</span></span>

```qsharp
operation MaybeChooseElement<'T> (data : 'T[], indexDistribution : Microsoft.Quantum.Random.DiscreteDistribution) : (Bool, 'T)
```


## <a name="input"></a><span data-ttu-id="160ff-106">输入</span><span class="sxs-lookup"><span data-stu-id="160ff-106">Input</span></span>

### <a name="data--t"></a><span data-ttu-id="160ff-107">数据： t []</span><span class="sxs-lookup"><span data-stu-id="160ff-107">data : 'T[]</span></span>

<span data-ttu-id="160ff-108">应从中选择元素的数组。</span><span class="sxs-lookup"><span data-stu-id="160ff-108">The array from which an element should be chosen.</span></span>


### <a name="indexdistribution--discretedistribution"></a><span data-ttu-id="160ff-109">indexDistribution： [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="160ff-109">indexDistribution : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="160ff-110">索引的分布 `data` 。</span><span class="sxs-lookup"><span data-stu-id="160ff-110">A distribution over the indices of `data`.</span></span>



## <a name="output--boolt"></a><span data-ttu-id="160ff-111">Output： ([Bool](xref:microsoft.quantum.lang-ref.bool)，不) </span><span class="sxs-lookup"><span data-stu-id="160ff-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="160ff-112">类型参数</span><span class="sxs-lookup"><span data-stu-id="160ff-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="160ff-113">找</span><span class="sxs-lookup"><span data-stu-id="160ff-113">'T</span></span>

