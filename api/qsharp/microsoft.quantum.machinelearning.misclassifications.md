---
uid: Microsoft.Quantum.MachineLearning.Misclassifications
title: Misclassifications 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Misclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.
ms.openlocfilehash: 3913395fbd9f7cf96732c17ca0c726289e5087ed
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853927"
---
# <a name="misclassifications-function"></a><span data-ttu-id="b65a9-102">Misclassifications 函数</span><span class="sxs-lookup"><span data-stu-id="b65a9-102">Misclassifications function</span></span>

<span data-ttu-id="b65a9-103">命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="b65a9-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="b65a9-104">Package： [default-machinelearning-southcentralus](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="b65a9-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="b65a9-105">给定一组推断标签和一组正确标签，返回每组标签不同的位置的索引。</span><span class="sxs-lookup"><span data-stu-id="b65a9-105">Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.</span></span>

```qsharp
function Misclassifications (inferredLabels : Int[], actualLabels : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="b65a9-106">输入</span><span class="sxs-lookup"><span data-stu-id="b65a9-106">Input</span></span>

### <a name="inferredlabels--int"></a><span data-ttu-id="b65a9-107">inferredLabels： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="b65a9-107">inferredLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="b65a9-108">为给定定型集或验证集推理出的标签。</span><span class="sxs-lookup"><span data-stu-id="b65a9-108">The labels inferred for a given training or validation set.</span></span>


### <a name="actuallabels--int"></a><span data-ttu-id="b65a9-109">actualLabels： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="b65a9-109">actualLabels : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="b65a9-110">给定定型集或验证集的 true 标签。</span><span class="sxs-lookup"><span data-stu-id="b65a9-110">The true labels for a given training or validation set.</span></span>



## <a name="output--int"></a><span data-ttu-id="b65a9-111">输出： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="b65a9-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="b65a9-112">索引的数组 `idx` ，例如 `inferredLabels[idx] != actualLabels[idx]` 。</span><span class="sxs-lookup"><span data-stu-id="b65a9-112">An array of indices `idx` such that `inferredLabels[idx] != actualLabels[idx]`.</span></span>

## <a name="example"></a><span data-ttu-id="b65a9-113">示例</span><span class="sxs-lookup"><span data-stu-id="b65a9-113">Example</span></span>

```qsharp
let misclassifications = Misclassifications([0, 1, 0, 0], [0, 1, 1, 0]);
Message($"{misclassifications}"); // Will print [2].
```