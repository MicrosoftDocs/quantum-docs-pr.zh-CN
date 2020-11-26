---
uid: Microsoft.Quantum.MachineLearning.EstimateGradient
title: EstimateGradient 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateGradient
qsharp.summary: Estimates the training gradient for a sequential classifier at a particular model and for a given encoded input.
ms.openlocfilehash: 79f4abdf131509d4948a3c114e631118329f88d8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211842"
---
# <a name="estimategradient-operation"></a><span data-ttu-id="d1349-102">EstimateGradient 操作</span><span class="sxs-lookup"><span data-stu-id="d1349-102">EstimateGradient operation</span></span>

<span data-ttu-id="d1349-103">命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="d1349-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="d1349-104">Package： [default-machinelearning-southcentralus](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="d1349-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="d1349-105">估算特定模型和给定编码输入的顺序分类器的定型渐变。</span><span class="sxs-lookup"><span data-stu-id="d1349-105">Estimates the training gradient for a sequential classifier at a particular model and for a given encoded input.</span></span>

```qsharp
operation EstimateGradient (model : Microsoft.Quantum.MachineLearning.SequentialModel, encodedInput : Microsoft.Quantum.MachineLearning.StateGenerator, nMeasurements : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="d1349-106">输入</span><span class="sxs-lookup"><span data-stu-id="d1349-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="d1349-107">模型： [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="d1349-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="d1349-108">要估计其渐变的顺序模型。</span><span class="sxs-lookup"><span data-stu-id="d1349-108">The sequential model whose gradient is to be estimated.</span></span>


### <a name="encodedinput--stategenerator"></a><span data-ttu-id="d1349-109">encodedInput： [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span><span class="sxs-lookup"><span data-stu-id="d1349-109">encodedInput : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span></span>

<span data-ttu-id="d1349-110">对顺序分类器的输入，编码为状态准备操作。</span><span class="sxs-lookup"><span data-stu-id="d1349-110">An input to the sequential classifier, encoded into a state preparation operation.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="d1349-111">nMeasurements： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d1349-111">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d1349-112">要在估计渐变时使用的度量值的数量。</span><span class="sxs-lookup"><span data-stu-id="d1349-112">The number of measurements to use in estimating the gradient.</span></span>



## <a name="output--double"></a><span data-ttu-id="d1349-113">输出： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="d1349-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="d1349-114">给定输入和模型参数的定型渐变的估计值。</span><span class="sxs-lookup"><span data-stu-id="d1349-114">An estimate of the training gradient at the given input and model parameters.</span></span>

## <a name="remarks"></a><span data-ttu-id="d1349-115">备注</span><span class="sxs-lookup"><span data-stu-id="d1349-115">Remarks</span></span>

<span data-ttu-id="d1349-116">此操作使用 Hadamard 测试和参数移位技术来估算渐变。</span><span class="sxs-lookup"><span data-stu-id="d1349-116">This operation uses a Hadamard test and the parameter shift technique together to estimate the gradient.</span></span>