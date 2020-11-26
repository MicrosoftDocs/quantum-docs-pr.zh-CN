---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: LabeledSample 用户定义的类型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: a7c7dae5cd9e82d66bb98313f4200838006ca291
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196321"
---
# <a name="labeledsample-user-defined-type"></a><span data-ttu-id="a6d66-102">LabeledSample 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="a6d66-102">LabeledSample user defined type</span></span>

<span data-ttu-id="a6d66-103">命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="a6d66-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="a6d66-104">Package： [default-machinelearning-southcentralus](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="a6d66-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="a6d66-105">一个示例，使用该示例所属的类进行标记。</span><span class="sxs-lookup"><span data-stu-id="a6d66-105">A sample, labeled with a class to which that sample belongs.</span></span>

```qsharp

newtype LabeledSample = (Features : Double[], Label : Int);
```



## <a name="named-items"></a><span data-ttu-id="a6d66-106">命名项</span><span class="sxs-lookup"><span data-stu-id="a6d66-106">Named Items</span></span>

### <a name="features--double"></a><span data-ttu-id="a6d66-107">功能： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="a6d66-107">Features : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="a6d66-108">给定示例的功能矢量。</span><span class="sxs-lookup"><span data-stu-id="a6d66-108">A vector of features for the given sample.</span></span>
### <a name="label--int"></a><span data-ttu-id="a6d66-109">标签： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a6d66-109">Label : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a6d66-110">此示例所属类的整数标签。</span><span class="sxs-lookup"><span data-stu-id="a6d66-110">An integer label for the class to which this sample belongs.</span></span>