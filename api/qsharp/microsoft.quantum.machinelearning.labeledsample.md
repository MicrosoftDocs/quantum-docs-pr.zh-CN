---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: LabeledSample 用户定义的类型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: 8b4afa1eaf7ca69938b2606163cd1ec17a1ad80f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695363"
---
# <a name="labeledsample-user-defined-type"></a><span data-ttu-id="81f33-102">LabeledSample 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="81f33-102">LabeledSample user defined type</span></span>

<span data-ttu-id="81f33-103">命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="81f33-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="81f33-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="81f33-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="81f33-105">一个示例，使用该示例所属的类进行标记。</span><span class="sxs-lookup"><span data-stu-id="81f33-105">A sample, labeled with a class to which that sample belongs.</span></span>

```qsharp

newtype LabeledSample = (Features : Double[], Label : Int);
```



## <a name="named-items"></a><span data-ttu-id="81f33-106">命名项</span><span class="sxs-lookup"><span data-stu-id="81f33-106">Named Items</span></span>

### <a name="features--double"></a><span data-ttu-id="81f33-107">功能： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="81f33-107">Features : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="81f33-108">给定示例的功能矢量。</span><span class="sxs-lookup"><span data-stu-id="81f33-108">A vector of features for the given sample.</span></span>
### <a name="label--int"></a><span data-ttu-id="81f33-109">标签： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="81f33-109">Label : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="81f33-110">此示例所属类的整数标签。</span><span class="sxs-lookup"><span data-stu-id="81f33-110">An integer label for the class to which this sample belongs.</span></span>