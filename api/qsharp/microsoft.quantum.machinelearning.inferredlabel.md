---
uid: Microsoft.Quantum.MachineLearning.InferredLabel
title: InferredLabel 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabel
qsharp.summary: Given a of classification probability and a bias, returns the label inferred from that probability.
ms.openlocfilehash: 1d6edec94f731fe96da797f0c3d77e6eba565149
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700293"
---
# <a name="inferredlabel-function"></a><span data-ttu-id="ae121-102">InferredLabel 函数</span><span class="sxs-lookup"><span data-stu-id="ae121-102">InferredLabel function</span></span>

<span data-ttu-id="ae121-103">命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="ae121-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="ae121-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ae121-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ae121-105">给定一个分类概率和一个偏差，返回从该概率推导出的标签。</span><span class="sxs-lookup"><span data-stu-id="ae121-105">Given a of classification probability and a bias, returns the label inferred from that probability.</span></span>

```qsharp
function InferredLabel (bias : Double, probability : Double) : Int
```


## <a name="input"></a><span data-ttu-id="ae121-106">输入</span><span class="sxs-lookup"><span data-stu-id="ae121-106">Input</span></span>

### <a name="bias--double"></a><span data-ttu-id="ae121-107">偏置： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ae121-107">bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ae121-108">两个类之间的偏移，通常是定型分类器的结果。</span><span class="sxs-lookup"><span data-stu-id="ae121-108">The bias between two classes, typically the result of training a classifier.</span></span>


### <a name="probability--double"></a><span data-ttu-id="ae121-109">概率： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="ae121-109">probability : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="ae121-110">特定示例的分类概率，通常是从估算其分类频率得出的。</span><span class="sxs-lookup"><span data-stu-id="ae121-110">A classification probabilities for a particular sample, typically resulting from estimating its classification frequency.</span></span>



## <a name="output--int"></a><span data-ttu-id="ae121-111">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ae121-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ae121-112">从给定分类概率中推断出的标签。</span><span class="sxs-lookup"><span data-stu-id="ae121-112">The label inferred from the given classification probability.</span></span>