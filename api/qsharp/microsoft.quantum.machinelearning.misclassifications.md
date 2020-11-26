---
uid: Microsoft.Quantum.MachineLearning.Misclassifications
title: Misclassifications 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Misclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.
ms.openlocfilehash: e13a9b9b65931678d5d87878e81fa172329a28ea
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211672"
---
# <a name="misclassifications-function"></a><span data-ttu-id="586d1-102">Misclassifications 函数</span><span class="sxs-lookup"><span data-stu-id="586d1-102">Misclassifications function</span></span>

<span data-ttu-id="586d1-103">命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="586d1-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="586d1-104">Package： [default-machinelearning-southcentralus](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="586d1-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="586d1-105">给定一组推断标签和一组正确标签，返回每组标签不同的位置的索引。</span><span class="sxs-lookup"><span data-stu-id="586d1-105">Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.</span></span>

```qsharp
function Misclassifications (inferredLabels : Int[], actualLabels : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="586d1-106">输入</span><span class="sxs-lookup"><span data-stu-id="586d1-106">Input</span></span>

### <a name="inferredlabels--int"></a><span data-ttu-id="586d1-107">inferredLabels： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="586d1-107">inferredLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="586d1-108">为给定定型集或验证集推理出的标签。</span><span class="sxs-lookup"><span data-stu-id="586d1-108">The labels inferred for a given training or validation set.</span></span>


### <a name="actuallabels--int"></a><span data-ttu-id="586d1-109">actualLabels： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="586d1-109">actualLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="586d1-110">给定定型集或验证集的 true 标签。</span><span class="sxs-lookup"><span data-stu-id="586d1-110">The true labels for a given training or validation set.</span></span>



## <a name="output--int"></a><span data-ttu-id="586d1-111">输出： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="586d1-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="586d1-112">索引的数组 `idx` ，例如 `inferredLabels[idx] != actualLabels[idx]` 。</span><span class="sxs-lookup"><span data-stu-id="586d1-112">An array of indices `idx` such that `inferredLabels[idx] != actualLabels[idx]`.</span></span>