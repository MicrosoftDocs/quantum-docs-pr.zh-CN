---
uid: Microsoft.Quantum.MachineLearning._UpdatedBias
title: _UpdatedBias 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: _UpdatedBias
qsharp.summary: Returns a bias value that leads to near-minimum misclassification score.
ms.openlocfilehash: 2704d08e4c1ce868e1fd9065c3cab0285d431094
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696738"
---
# <a name="_updatedbias-function"></a><span data-ttu-id="f3c65-102">_UpdatedBias 函数</span><span class="sxs-lookup"><span data-stu-id="f3c65-102">_UpdatedBias function</span></span>

<span data-ttu-id="f3c65-103">命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="f3c65-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="f3c65-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f3c65-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f3c65-105">返回导致最小错误分类分数的偏差值。</span><span class="sxs-lookup"><span data-stu-id="f3c65-105">Returns a bias value that leads to near-minimum misclassification score.</span></span>

```qsharp
function _UpdatedBias (labeledProbabilities : (Double, Int)[], bias : Double, tolerance : Double) : Double
```


## <a name="input"></a><span data-ttu-id="f3c65-106">输入</span><span class="sxs-lookup"><span data-stu-id="f3c65-106">Input</span></span>

### <a name="labeledprobabilities--doubleint"></a><span data-ttu-id="f3c65-107">labeledProbabilities： ([Double](xref:microsoft.quantum.lang-ref.double)，[Int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="f3c65-107">labeledProbabilities : ([Double](xref:microsoft.quantum.lang-ref.double),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>




### <a name="bias--double"></a><span data-ttu-id="f3c65-108">偏置： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f3c65-108">bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>




### <a name="tolerance--double"></a><span data-ttu-id="f3c65-109">容差： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f3c65-109">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>





## <a name="output--double"></a><span data-ttu-id="f3c65-110">输出： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f3c65-110">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

