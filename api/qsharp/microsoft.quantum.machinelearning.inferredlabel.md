---
uid: Microsoft.Quantum.MachineLearning.InferredLabel
title: InferredLabel 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabel
qsharp.summary: Given a of classification probability and a bias, returns the label inferred from that probability.
ms.openlocfilehash: b64bb1ec52d2456ee1b627b920890223d173533b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211774"
---
# <a name="inferredlabel-function"></a><span data-ttu-id="8dfbe-102">InferredLabel 函数</span><span class="sxs-lookup"><span data-stu-id="8dfbe-102">InferredLabel function</span></span>

<span data-ttu-id="8dfbe-103">命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="8dfbe-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="8dfbe-104">Package： [default-machinelearning-southcentralus](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="8dfbe-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="8dfbe-105">给定一个分类概率和一个偏差，返回从该概率推导出的标签。</span><span class="sxs-lookup"><span data-stu-id="8dfbe-105">Given a of classification probability and a bias, returns the label inferred from that probability.</span></span>

```qsharp
function InferredLabel (bias : Double, probability : Double) : Int
```


## <a name="input"></a><span data-ttu-id="8dfbe-106">输入</span><span class="sxs-lookup"><span data-stu-id="8dfbe-106">Input</span></span>

### <a name="bias--double"></a><span data-ttu-id="8dfbe-107">偏置： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8dfbe-107">bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8dfbe-108">两个类之间的偏移，通常是定型分类器的结果。</span><span class="sxs-lookup"><span data-stu-id="8dfbe-108">The bias between two classes, typically the result of training a classifier.</span></span>


### <a name="probability--double"></a><span data-ttu-id="8dfbe-109">概率： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="8dfbe-109">probability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="8dfbe-110">特定示例的分类概率，通常是从估算其分类频率得出的。</span><span class="sxs-lookup"><span data-stu-id="8dfbe-110">A classification probabilities for a particular sample, typically resulting from estimating its classification frequency.</span></span>



## <a name="output--int"></a><span data-ttu-id="8dfbe-111">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8dfbe-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8dfbe-112">从给定分类概率中推断出的标签。</span><span class="sxs-lookup"><span data-stu-id="8dfbe-112">The label inferred from the given classification probability.</span></span>