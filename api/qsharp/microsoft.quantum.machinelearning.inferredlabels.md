---
uid: Microsoft.Quantum.MachineLearning.InferredLabels
title: InferredLabels 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabels
qsharp.summary: Given an array of classification probabilities and a bias, returns the label inferred from each probability.
ms.openlocfilehash: 874d1a2f7cc6d67567e0d2baa70b0d26b639a029
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700284"
---
# <a name="inferredlabels-function"></a><span data-ttu-id="cf86c-102">InferredLabels 函数</span><span class="sxs-lookup"><span data-stu-id="cf86c-102">InferredLabels function</span></span>

<span data-ttu-id="cf86c-103">命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="cf86c-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="cf86c-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cf86c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cf86c-105">给定一组分类概率和一个偏差，返回从每个概率推导出的标签。</span><span class="sxs-lookup"><span data-stu-id="cf86c-105">Given an array of classification probabilities and a bias, returns the label inferred from each probability.</span></span>

```qsharp
function InferredLabels (bias : Double, probabilities : Double[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="cf86c-106">输入</span><span class="sxs-lookup"><span data-stu-id="cf86c-106">Input</span></span>

### <a name="bias--double"></a><span data-ttu-id="cf86c-107">偏置： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="cf86c-107">bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="cf86c-108">两个类之间的偏移，通常是定型分类器的结果。</span><span class="sxs-lookup"><span data-stu-id="cf86c-108">The bias between two classes, typically the result of training a classifier.</span></span>


### <a name="probabilities--double"></a><span data-ttu-id="cf86c-109">概率： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="cf86c-109">probabilities : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="cf86c-110">一组样本的分类概率数组，通常由估计分类频率引起。</span><span class="sxs-lookup"><span data-stu-id="cf86c-110">An array of classification probabilities for a set of samples, typically resulting from estimating classification frequencies.</span></span>



## <a name="output--int"></a><span data-ttu-id="cf86c-111">输出： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="cf86c-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="cf86c-112">从每个分类概率中推断出的标签。</span><span class="sxs-lookup"><span data-stu-id="cf86c-112">The label inferred from each classification probability.</span></span>