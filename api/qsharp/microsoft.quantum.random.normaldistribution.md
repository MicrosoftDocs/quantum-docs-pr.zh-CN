---
uid: Microsoft.Quantum.Random.NormalDistribution
title: NormalDistribution 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: NormalDistribution
qsharp.summary: Returns a normal distribution with a given mean and variance.
ms.openlocfilehash: 733a2763dca6d75f81d538f63c3084331a8e1d51
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814189"
---
# <a name="normaldistribution-function"></a><span data-ttu-id="0c8de-102">NormalDistribution 函数</span><span class="sxs-lookup"><span data-stu-id="0c8de-102">NormalDistribution function</span></span>

<span data-ttu-id="0c8de-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="0c8de-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="0c8de-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="0c8de-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="0c8de-105">返回具有给定平均值和方差的正态分布。</span><span class="sxs-lookup"><span data-stu-id="0c8de-105">Returns a normal distribution with a given mean and variance.</span></span>

```qsharp
function NormalDistribution (mean : Double, variance : Double) : Microsoft.Quantum.Random.ContinuousDistribution
```


## <a name="input"></a><span data-ttu-id="0c8de-106">输入</span><span class="sxs-lookup"><span data-stu-id="0c8de-106">Input</span></span>

### <a name="mean--double"></a><span data-ttu-id="0c8de-107">均值： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0c8de-107">mean : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>




### <a name="variance--double"></a><span data-ttu-id="0c8de-108">变体： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0c8de-108">variance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>





## <a name="output--continuousdistribution"></a><span data-ttu-id="0c8de-109">输出： [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="0c8de-109">Output : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>



## <a name="example"></a><span data-ttu-id="0c8de-110">示例</span><span class="sxs-lookup"><span data-stu-id="0c8de-110">Example</span></span>

<span data-ttu-id="0c8de-111">下面的示例从正态分布（2和标准偏差为0.1）中提取了10个样本：</span><span class="sxs-lookup"><span data-stu-id="0c8de-111">The following draws 10 samples from the normal distribution with mean 2 and standard deviation 0.1:</span></span>

```qsharp
let samples = DrawMany(
    (NormalDistribution(2.0, PowD(0.1, 2.0)))::Sample,
    10, ()
);
```

## <a name="see-also"></a><span data-ttu-id="0c8de-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0c8de-112">See Also</span></span>

- [<span data-ttu-id="0c8de-113">StandardNormalDistribution。</span><span class="sxs-lookup"><span data-stu-id="0c8de-113">Microsoft.Quantum.Random.StandardNormalDistribution</span></span>](xref:Microsoft.Quantum.Random.StandardNormalDistribution)