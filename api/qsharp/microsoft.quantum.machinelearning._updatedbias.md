---
uid: Microsoft.Quantum.MachineLearning._UpdatedBias
title: _UpdatedBias 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: _UpdatedBias
qsharp.summary: Returns a bias value that leads to near-minimum misclassification score.
ms.openlocfilehash: 141edf6e425a060a995bfc181aefb1bcffdb128b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196695"
---
# <a name="_updatedbias-function"></a><span data-ttu-id="fa0e0-102">_UpdatedBias 函数</span><span class="sxs-lookup"><span data-stu-id="fa0e0-102">_UpdatedBias function</span></span>

<span data-ttu-id="fa0e0-103">命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="fa0e0-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="fa0e0-104">Package： [default-machinelearning-southcentralus](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="fa0e0-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="fa0e0-105">返回导致最小错误分类分数的偏差值。</span><span class="sxs-lookup"><span data-stu-id="fa0e0-105">Returns a bias value that leads to near-minimum misclassification score.</span></span>

```qsharp
function _UpdatedBias (labeledProbabilities : (Double, Int)[], bias : Double, tolerance : Double) : Double
```


## <a name="input"></a><span data-ttu-id="fa0e0-106">输入</span><span class="sxs-lookup"><span data-stu-id="fa0e0-106">Input</span></span>

### <a name="labeledprobabilities--doubleint"></a><span data-ttu-id="fa0e0-107">labeledProbabilities： ([Double](xref:microsoft.quantum.lang-ref.double)，[Int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="fa0e0-107">labeledProbabilities : ([Double](xref:microsoft.quantum.lang-ref.double),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>




### <a name="bias--double"></a><span data-ttu-id="fa0e0-108">偏置： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fa0e0-108">bias : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>




### <a name="tolerance--double"></a><span data-ttu-id="fa0e0-109">容差： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fa0e0-109">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>





## <a name="output--double"></a><span data-ttu-id="fa0e0-110">输出： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="fa0e0-110">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

