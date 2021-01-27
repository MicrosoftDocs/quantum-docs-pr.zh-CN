---
uid: Microsoft.Quantum.MachineLearning.InferredLabel
title: InferredLabel 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabel
qsharp.summary: Given a of classification probability and a bias, returns the label inferred from that probability.
ms.openlocfilehash: 46b24c283a01e6ac1c959ee4a6899591ee708ff7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848421"
---
# <a name="inferredlabel-function"></a><span data-ttu-id="21ea2-102">InferredLabel 函数</span><span class="sxs-lookup"><span data-stu-id="21ea2-102">InferredLabel function</span></span>

<span data-ttu-id="21ea2-103">命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="21ea2-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="21ea2-104">Package： [default-machinelearning-southcentralus](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="21ea2-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="21ea2-105">给定一个分类概率和一个偏差，返回从该概率推导出的标签。</span><span class="sxs-lookup"><span data-stu-id="21ea2-105">Given a of classification probability and a bias, returns the label inferred from that probability.</span></span>

```qsharp
function InferredLabel (bias : Double, probability : Double) : Int
```


## <a name="input"></a><span data-ttu-id="21ea2-106">输入</span><span class="sxs-lookup"><span data-stu-id="21ea2-106">Input</span></span>

### <a name="bias--double"></a><span data-ttu-id="21ea2-107">偏置： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="21ea2-107">bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="21ea2-108">两个类之间的偏移，通常是定型分类器的结果。</span><span class="sxs-lookup"><span data-stu-id="21ea2-108">The bias between two classes, typically the result of training a classifier.</span></span>


### <a name="probability--double"></a><span data-ttu-id="21ea2-109">概率： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="21ea2-109">probability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="21ea2-110">特定示例的分类概率，通常是从估算其分类频率得出的。</span><span class="sxs-lookup"><span data-stu-id="21ea2-110">A classification probabilities for a particular sample, typically resulting from estimating its classification frequency.</span></span>



## <a name="output--int"></a><span data-ttu-id="21ea2-111">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="21ea2-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="21ea2-112">从给定分类概率中推断出的标签。</span><span class="sxs-lookup"><span data-stu-id="21ea2-112">The label inferred from the given classification probability.</span></span>