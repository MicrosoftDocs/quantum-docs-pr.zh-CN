---
uid: Microsoft.Quantum.MachineLearning.InferredLabels
title: InferredLabels 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabels
qsharp.summary: Given an array of classification probabilities and a bias, returns the label inferred from each probability.
ms.openlocfilehash: 668ab89ed45c49d33ce50ff5d892f4d57246c12a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196355"
---
# <a name="inferredlabels-function"></a><span data-ttu-id="b3878-102">InferredLabels 函数</span><span class="sxs-lookup"><span data-stu-id="b3878-102">InferredLabels function</span></span>

<span data-ttu-id="b3878-103">命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="b3878-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="b3878-104">Package： [default-machinelearning-southcentralus](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="b3878-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="b3878-105">给定一组分类概率和一个偏差，返回从每个概率推导出的标签。</span><span class="sxs-lookup"><span data-stu-id="b3878-105">Given an array of classification probabilities and a bias, returns the label inferred from each probability.</span></span>

```qsharp
function InferredLabels (bias : Double, probabilities : Double[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="b3878-106">输入</span><span class="sxs-lookup"><span data-stu-id="b3878-106">Input</span></span>

### <a name="bias--double"></a><span data-ttu-id="b3878-107">偏置： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="b3878-107">bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="b3878-108">两个类之间的偏移，通常是定型分类器的结果。</span><span class="sxs-lookup"><span data-stu-id="b3878-108">The bias between two classes, typically the result of training a classifier.</span></span>


### <a name="probabilities--double"></a><span data-ttu-id="b3878-109">概率： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="b3878-109">probabilities : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="b3878-110">一组样本的分类概率数组，通常由估计分类频率引起。</span><span class="sxs-lookup"><span data-stu-id="b3878-110">An array of classification probabilities for a set of samples, typically resulting from estimating classification frequencies.</span></span>



## <a name="output--int"></a><span data-ttu-id="b3878-111">输出： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="b3878-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="b3878-112">从每个分类概率中推断出的标签。</span><span class="sxs-lookup"><span data-stu-id="b3878-112">The label inferred from each classification probability.</span></span>