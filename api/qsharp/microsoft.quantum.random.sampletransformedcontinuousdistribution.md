---
uid: Microsoft.Quantum.Random.SampleTransformedContinuousDistribution
title: SampleTransformedContinuousDistribution 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: SampleTransformedContinuousDistribution
qsharp.summary: Internal-only operation for sampling from transformed distributions. Should only be used via partial application.
ms.openlocfilehash: dc93022e53199cd8ef794da9c1590d6997a0fda1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700709"
---
# <a name="sampletransformedcontinuousdistribution-operation"></a><span data-ttu-id="27d08-102">SampleTransformedContinuousDistribution 操作</span><span class="sxs-lookup"><span data-stu-id="27d08-102">SampleTransformedContinuousDistribution operation</span></span>

<span data-ttu-id="27d08-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="27d08-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="27d08-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="27d08-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="27d08-105">从转换后的分发进行采样的仅限内部操作。</span><span class="sxs-lookup"><span data-stu-id="27d08-105">Internal-only operation for sampling from transformed distributions.</span></span>
<span data-ttu-id="27d08-106">只应通过部分应用程序使用。</span><span class="sxs-lookup"><span data-stu-id="27d08-106">Should only be used via partial application.</span></span>

```qsharp
operation SampleTransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Double
```


## <a name="input"></a><span data-ttu-id="27d08-107">输入</span><span class="sxs-lookup"><span data-stu-id="27d08-107">Input</span></span>

### <a name="transform--double---double"></a><span data-ttu-id="27d08-108">转换： [双](xref:microsoft.quantum.lang-ref.double) -> [双精度](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="27d08-108">transform : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>




### <a name="distribution--continuousdistribution"></a><span data-ttu-id="27d08-109">分发： [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="27d08-109">distribution : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>





## <a name="output--double"></a><span data-ttu-id="27d08-110">输出： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="27d08-110">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

