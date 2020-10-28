---
uid: Microsoft.Quantum.Random.TransformedContinuousDistribution
title: TransformedContinuousDistribution 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: TransformedContinuousDistribution
qsharp.summary: Given a continuous distribution, returns a new distribution that transforms the original by a given function.
ms.openlocfilehash: 6a6e0c26bd650fd4c05208197ff23f951d1c3b5c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695307"
---
# <a name="transformedcontinuousdistribution-function"></a><span data-ttu-id="08529-102">TransformedContinuousDistribution 函数</span><span class="sxs-lookup"><span data-stu-id="08529-102">TransformedContinuousDistribution function</span></span>

<span data-ttu-id="08529-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="08529-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="08529-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="08529-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="08529-105">给定连续分布时，将返回一个新的分布，该分布通过给定函数转换原始。</span><span class="sxs-lookup"><span data-stu-id="08529-105">Given a continuous distribution, returns a new distribution that transforms the original by a given function.</span></span>

```qsharp
function TransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="08529-106">输入</span><span class="sxs-lookup"><span data-stu-id="08529-106">Input</span></span>

### <a name="transform--double---double"></a><span data-ttu-id="08529-107">转换： [双](xref:microsoft.quantum.lang-ref.double) -> [双精度](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="08529-107">transform : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="08529-108">将原始分布的 variates 转换为转换后的分布的函数。</span><span class="sxs-lookup"><span data-stu-id="08529-108">A function that transforms variates of the original distribution to the transformed distribution.</span></span>


### <a name="distribution--continuousdistribution"></a><span data-ttu-id="08529-109">分发： [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="08529-109">distribution : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="08529-110">要转换的原始分布。</span><span class="sxs-lookup"><span data-stu-id="08529-110">The original distribution to be transformed.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="08529-111">输出： [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="08529-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="08529-112">由提供的转换与关联的新分布 `distribution` `transform` 。</span><span class="sxs-lookup"><span data-stu-id="08529-112">A new distribution related to `distribution` by the transformation given by `transform`.</span></span>