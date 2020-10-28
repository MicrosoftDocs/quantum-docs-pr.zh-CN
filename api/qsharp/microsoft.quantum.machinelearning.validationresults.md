---
uid: Microsoft.Quantum.MachineLearning.ValidationResults
title: ValidationResults 用户定义的类型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ValidationResults
qsharp.summary: The results from having validated a classifier against a set of samples.
ms.openlocfilehash: 1e54a5a086035f5f8d36d777badb306156d99600
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696715"
---
# <a name="validationresults-user-defined-type"></a><span data-ttu-id="114ce-102">ValidationResults 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="114ce-102">ValidationResults user defined type</span></span>

<span data-ttu-id="114ce-103">命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="114ce-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="114ce-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="114ce-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="114ce-105">根据一组示例验证了分类器后得到的结果。</span><span class="sxs-lookup"><span data-stu-id="114ce-105">The results from having validated a classifier against a set of samples.</span></span>

```qsharp

newtype ValidationResults = (NMisclassifications : Int, NValidationSamples : Int);
```



## <a name="named-items"></a><span data-ttu-id="114ce-106">命名项</span><span class="sxs-lookup"><span data-stu-id="114ce-106">Named Items</span></span>

### <a name="nmisclassifications--int"></a><span data-ttu-id="114ce-107">NMisclassifications： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="114ce-107">NMisclassifications : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="114ce-108">验证期间观察到的 misclassifications 的数目。</span><span class="sxs-lookup"><span data-stu-id="114ce-108">The number of misclassifications observed during validation.</span></span>
### <a name="nvalidationsamples--int"></a><span data-ttu-id="114ce-109">NValidationSamples： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="114ce-109">NValidationSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

