---
uid: Microsoft.Quantum.MachineLearning.LabeledSample
title: LabeledSample 用户定义的类型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LabeledSample
qsharp.summary: A sample, labeled with a class to which that sample belongs.
ms.openlocfilehash: b357aae20b5bddb968ce1906fed3c1001efbfde7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846975"
---
# <a name="labeledsample-user-defined-type"></a><span data-ttu-id="b1fed-102">LabeledSample 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="b1fed-102">LabeledSample user defined type</span></span>

<span data-ttu-id="b1fed-103">命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="b1fed-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="b1fed-104">Package： [default-machinelearning-southcentralus](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="b1fed-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="b1fed-105">一个示例，使用该示例所属的类进行标记。</span><span class="sxs-lookup"><span data-stu-id="b1fed-105">A sample, labeled with a class to which that sample belongs.</span></span>

```qsharp

newtype LabeledSample = (Features : Double[], Label : Int);
```



## <a name="named-items"></a><span data-ttu-id="b1fed-106">命名项</span><span class="sxs-lookup"><span data-stu-id="b1fed-106">Named Items</span></span>

### <a name="features--double"></a><span data-ttu-id="b1fed-107">功能： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="b1fed-107">Features : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="b1fed-108">给定示例的功能矢量。</span><span class="sxs-lookup"><span data-stu-id="b1fed-108">A vector of features for the given sample.</span></span>
### <a name="label--int"></a><span data-ttu-id="b1fed-109">标签： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b1fed-109">Label : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b1fed-110">此示例所属类的整数标签。</span><span class="sxs-lookup"><span data-stu-id="b1fed-110">An integer label for the class to which this sample belongs.</span></span>