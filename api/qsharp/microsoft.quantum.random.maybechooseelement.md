---
uid: Microsoft.Quantum.Random.MaybeChooseElement
title: MaybeChooseElement 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: MaybeChooseElement
qsharp.summary: Given an array of data and an a distribution over its indices, attempts to choose an element at random.
ms.openlocfilehash: 12640d9dc3aad301146eff7bcbbaae33d3ccd420
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700193"
---
# <a name="maybechooseelement-operation"></a><span data-ttu-id="c9c1d-102">MaybeChooseElement 操作</span><span class="sxs-lookup"><span data-stu-id="c9c1d-102">MaybeChooseElement operation</span></span>

<span data-ttu-id="c9c1d-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="c9c1d-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="c9c1d-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c9c1d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c9c1d-105">给定一个数据数组和一个针对其索引的分布，尝试随机选择一个元素。</span><span class="sxs-lookup"><span data-stu-id="c9c1d-105">Given an array of data and an a distribution over its indices, attempts to choose an element at random.</span></span>

```qsharp
operation MaybeChooseElement<'T> (data : 'T[], indexDistribution : Microsoft.Quantum.Random.DiscreteDistribution) : (Bool, 'T)
```


## <a name="input"></a><span data-ttu-id="c9c1d-106">输入</span><span class="sxs-lookup"><span data-stu-id="c9c1d-106">Input</span></span>

### <a name="data--t"></a><span data-ttu-id="c9c1d-107">数据： t []</span><span class="sxs-lookup"><span data-stu-id="c9c1d-107">data : 'T[]</span></span>

<span data-ttu-id="c9c1d-108">应从中选择元素的数组。</span><span class="sxs-lookup"><span data-stu-id="c9c1d-108">The array from which an element should be chosen.</span></span>


### <a name="indexdistribution--discretedistribution"></a><span data-ttu-id="c9c1d-109">indexDistribution： [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span><span class="sxs-lookup"><span data-stu-id="c9c1d-109">indexDistribution : [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)</span></span>

<span data-ttu-id="c9c1d-110">索引的分布 `data` 。</span><span class="sxs-lookup"><span data-stu-id="c9c1d-110">A distribution over the indices of `data`.</span></span>



## <a name="output--boolt"></a><span data-ttu-id="c9c1d-111">Output： ([Bool](xref:microsoft.quantum.lang-ref.bool)，不) </span><span class="sxs-lookup"><span data-stu-id="c9c1d-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c9c1d-112">类型参数</span><span class="sxs-lookup"><span data-stu-id="c9c1d-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c9c1d-113">找</span><span class="sxs-lookup"><span data-stu-id="c9c1d-113">'T</span></span>

