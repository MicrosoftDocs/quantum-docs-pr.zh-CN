---
uid: Microsoft.Quantum.Random.TransformedContinuousDistribution
title: TransformedContinuousDistribution 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: TransformedContinuousDistribution
qsharp.summary: Given a continuous distribution, returns a new distribution that transforms the original by a given function.
ms.openlocfilehash: b317eaaa0ff0180ea5d240464c96d1c6b59c9c70
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226258"
---
# <a name="transformedcontinuousdistribution-function"></a><span data-ttu-id="f6c80-102">TransformedContinuousDistribution 函数</span><span class="sxs-lookup"><span data-stu-id="f6c80-102">TransformedContinuousDistribution function</span></span>

<span data-ttu-id="f6c80-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="f6c80-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="f6c80-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="f6c80-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="f6c80-105">给定连续分布时，将返回一个新的分布，该分布通过给定函数转换原始。</span><span class="sxs-lookup"><span data-stu-id="f6c80-105">Given a continuous distribution, returns a new distribution that transforms the original by a given function.</span></span>

```qsharp
function TransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="f6c80-106">输入</span><span class="sxs-lookup"><span data-stu-id="f6c80-106">Input</span></span>

### <a name="transform--double---double"></a><span data-ttu-id="f6c80-107">转换： [双](xref:microsoft.quantum.lang-ref.double) -> [双精度](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f6c80-107">transform : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f6c80-108">将原始分布的 variates 转换为转换后的分布的函数。</span><span class="sxs-lookup"><span data-stu-id="f6c80-108">A function that transforms variates of the original distribution to the transformed distribution.</span></span>


### <a name="distribution--continuousdistribution"></a><span data-ttu-id="f6c80-109">分发： [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="f6c80-109">distribution : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="f6c80-110">要转换的原始分布。</span><span class="sxs-lookup"><span data-stu-id="f6c80-110">The original distribution to be transformed.</span></span>



## <a name="output--continuousdistribution"></a><span data-ttu-id="f6c80-111">输出： [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="f6c80-111">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>

<span data-ttu-id="f6c80-112">由提供的转换与关联的新分布 `distribution` `transform` 。</span><span class="sxs-lookup"><span data-stu-id="f6c80-112">A new distribution related to `distribution` by the transformation given by `transform`.</span></span>