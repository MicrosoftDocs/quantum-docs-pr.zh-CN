---
uid: Microsoft.Quantum.MachineLearning.Misclassifications
title: Misclassifications 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Misclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.
ms.openlocfilehash: 500c2910f7c5616c88ff6c70ab3cc16680e199fb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700597"
---
# <a name="misclassifications-function"></a><span data-ttu-id="48365-102">Misclassifications 函数</span><span class="sxs-lookup"><span data-stu-id="48365-102">Misclassifications function</span></span>

<span data-ttu-id="48365-103">命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="48365-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="48365-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="48365-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="48365-105">给定一组推断标签和一组正确标签，返回每组标签不同的位置的索引。</span><span class="sxs-lookup"><span data-stu-id="48365-105">Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.</span></span>

```qsharp
function Misclassifications (inferredLabels : Int[], actualLabels : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="48365-106">输入</span><span class="sxs-lookup"><span data-stu-id="48365-106">Input</span></span>

### <a name="inferredlabels--int"></a><span data-ttu-id="48365-107">inferredLabels： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="48365-107">inferredLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="48365-108">为给定定型集或验证集推理出的标签。</span><span class="sxs-lookup"><span data-stu-id="48365-108">The labels inferred for a given training or validation set.</span></span>


### <a name="actuallabels--int"></a><span data-ttu-id="48365-109">actualLabels： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="48365-109">actualLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="48365-110">给定定型集或验证集的 true 标签。</span><span class="sxs-lookup"><span data-stu-id="48365-110">The true labels for a given training or validation set.</span></span>



## <a name="output--int"></a><span data-ttu-id="48365-111">输出： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="48365-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="48365-112">索引的数组 `idx` ，例如 `inferredLabels[idx] != actualLabels[idx]` 。</span><span class="sxs-lookup"><span data-stu-id="48365-112">An array of indices `idx` such that `inferredLabels[idx] != actualLabels[idx]`.</span></span>