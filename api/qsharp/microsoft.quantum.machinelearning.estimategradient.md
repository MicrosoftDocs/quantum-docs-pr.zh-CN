---
uid: Microsoft.Quantum.MachineLearning.EstimateGradient
title: EstimateGradient 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateGradient
qsharp.summary: Estimates the training gradient for a sequential classifier at a particular model and for a given encoded input.
ms.openlocfilehash: f42cc30c98346a25f584d7527227a95cb413c32b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696639"
---
# <a name="estimategradient-operation"></a><span data-ttu-id="ec3e9-102">EstimateGradient 操作</span><span class="sxs-lookup"><span data-stu-id="ec3e9-102">EstimateGradient operation</span></span>

<span data-ttu-id="ec3e9-103">命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="ec3e9-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="ec3e9-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ec3e9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ec3e9-105">估算特定模型和给定编码输入的顺序分类器的定型渐变。</span><span class="sxs-lookup"><span data-stu-id="ec3e9-105">Estimates the training gradient for a sequential classifier at a particular model and for a given encoded input.</span></span>

```qsharp
operation EstimateGradient (model : Microsoft.Quantum.MachineLearning.SequentialModel, encodedInput : Microsoft.Quantum.MachineLearning.StateGenerator, nMeasurements : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="ec3e9-106">输入</span><span class="sxs-lookup"><span data-stu-id="ec3e9-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="ec3e9-107">模型： [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="ec3e9-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="ec3e9-108">要估计其渐变的顺序模型。</span><span class="sxs-lookup"><span data-stu-id="ec3e9-108">The sequential model whose gradient is to be estimated.</span></span>


### <a name="encodedinput--stategenerator"></a><span data-ttu-id="ec3e9-109">encodedInput： [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span><span class="sxs-lookup"><span data-stu-id="ec3e9-109">encodedInput : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)</span></span>

<span data-ttu-id="ec3e9-110">对顺序分类器的输入，编码为状态准备操作。</span><span class="sxs-lookup"><span data-stu-id="ec3e9-110">An input to the sequential classifier, encoded into a state preparation operation.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="ec3e9-111">nMeasurements： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ec3e9-111">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ec3e9-112">要在估计渐变时使用的度量值的数量。</span><span class="sxs-lookup"><span data-stu-id="ec3e9-112">The number of measurements to use in estimating the gradient.</span></span>



## <a name="output--double"></a><span data-ttu-id="ec3e9-113">输出： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="ec3e9-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="ec3e9-114">给定输入和模型参数的定型渐变的估计值。</span><span class="sxs-lookup"><span data-stu-id="ec3e9-114">An estimate of the training gradient at the given input and model parameters.</span></span>

## <a name="remarks"></a><span data-ttu-id="ec3e9-115">注解</span><span class="sxs-lookup"><span data-stu-id="ec3e9-115">Remarks</span></span>

<span data-ttu-id="ec3e9-116">此操作使用 Hadamard 测试和参数移位技术来估算渐变。</span><span class="sxs-lookup"><span data-stu-id="ec3e9-116">This operation uses a Hadamard test and the parameter shift technique together to estimate the gradient.</span></span>