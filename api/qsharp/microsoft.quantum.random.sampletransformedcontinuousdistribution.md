---
uid: Microsoft.Quantum.Random.SampleTransformedContinuousDistribution
title: SampleTransformedContinuousDistribution 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: SampleTransformedContinuousDistribution
qsharp.summary: Internal-only operation for sampling from transformed distributions. Should only be used via partial application.
ms.openlocfilehash: f9f2b3cbbb4423f267758976cd066abbfec93a77
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192683"
---
# <a name="sampletransformedcontinuousdistribution-operation"></a><span data-ttu-id="206d4-102">SampleTransformedContinuousDistribution 操作</span><span class="sxs-lookup"><span data-stu-id="206d4-102">SampleTransformedContinuousDistribution operation</span></span>

<span data-ttu-id="206d4-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="206d4-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="206d4-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="206d4-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="206d4-105">从转换后的分发进行采样的仅限内部操作。</span><span class="sxs-lookup"><span data-stu-id="206d4-105">Internal-only operation for sampling from transformed distributions.</span></span>
<span data-ttu-id="206d4-106">只应通过部分应用程序使用。</span><span class="sxs-lookup"><span data-stu-id="206d4-106">Should only be used via partial application.</span></span>

```qsharp
operation SampleTransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Double
```


## <a name="input"></a><span data-ttu-id="206d4-107">输入</span><span class="sxs-lookup"><span data-stu-id="206d4-107">Input</span></span>

### <a name="transform--double---double"></a><span data-ttu-id="206d4-108">转换： [双](xref:microsoft.quantum.lang-ref.double) -> [双精度](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="206d4-108">transform : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>




### <a name="distribution--continuousdistribution"></a><span data-ttu-id="206d4-109">分发： [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="206d4-109">distribution : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>





## <a name="output--double"></a><span data-ttu-id="206d4-110">输出： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="206d4-110">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

