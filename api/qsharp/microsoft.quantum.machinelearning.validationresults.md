---
uid: Microsoft.Quantum.MachineLearning.ValidationResults
title: ValidationResults 用户定义的类型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ValidationResults
qsharp.summary: The results from having validated a classifier against a set of samples.
ms.openlocfilehash: 42bfab7fd1f9372d9394f2eaf2d698b39b4307e1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211485"
---
# <a name="validationresults-user-defined-type"></a><span data-ttu-id="62ff6-102">ValidationResults 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="62ff6-102">ValidationResults user defined type</span></span>

<span data-ttu-id="62ff6-103">命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="62ff6-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="62ff6-104">Package： [default-machinelearning-southcentralus](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="62ff6-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="62ff6-105">根据一组示例验证了分类器后得到的结果。</span><span class="sxs-lookup"><span data-stu-id="62ff6-105">The results from having validated a classifier against a set of samples.</span></span>

```qsharp

newtype ValidationResults = (NMisclassifications : Int, NValidationSamples : Int);
```



## <a name="named-items"></a><span data-ttu-id="62ff6-106">命名项</span><span class="sxs-lookup"><span data-stu-id="62ff6-106">Named Items</span></span>

### <a name="nmisclassifications--int"></a><span data-ttu-id="62ff6-107">NMisclassifications： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="62ff6-107">NMisclassifications : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="62ff6-108">验证期间观察到的 misclassifications 的数目。</span><span class="sxs-lookup"><span data-stu-id="62ff6-108">The number of misclassifications observed during validation.</span></span>
### <a name="nvalidationsamples--int"></a><span data-ttu-id="62ff6-109">NValidationSamples： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="62ff6-109">NValidationSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

