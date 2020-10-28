---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbabilities
title: EstimateClassificationProbabilities 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbabilities
qsharp.summary: Given a set of samples and a sequential classifier, estimates the classification probability for those samples by repeatedly measuring the output of the classifier on each sample.
ms.openlocfilehash: 2b7845d39256f718cc3e415207b8a47b24620bdb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695142"
---
# <a name="estimateclassificationprobabilities-operation"></a><span data-ttu-id="01337-102">EstimateClassificationProbabilities 操作</span><span class="sxs-lookup"><span data-stu-id="01337-102">EstimateClassificationProbabilities operation</span></span>

<span data-ttu-id="01337-103">命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="01337-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="01337-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="01337-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="01337-105">给定一组示例和顺序分类器，通过反复测量每个样本上分类器的输出来估算这些样本的分类概率。</span><span class="sxs-lookup"><span data-stu-id="01337-105">Given a set of samples and a sequential classifier, estimates the classification probability for those samples by repeatedly measuring the output of the classifier on each sample.</span></span>

```qsharp
operation EstimateClassificationProbabilities (tolerance : Double, model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Double[][], nMeasurements : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="01337-106">输入</span><span class="sxs-lookup"><span data-stu-id="01337-106">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="01337-107">容差： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="01337-107">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="01337-108">在将示例编码为状态准备操作时允许的容差。</span><span class="sxs-lookup"><span data-stu-id="01337-108">The tolerance to allow in encoding the sample into a state preparation operation.</span></span>


### <a name="model--sequentialmodel"></a><span data-ttu-id="01337-109">模型： [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="01337-109">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="01337-110">用于估算给定样本的分类概率的顺序模型。</span><span class="sxs-lookup"><span data-stu-id="01337-110">The sequential model to be used to estimate the classification probabilities for the given samples.</span></span>


### <a name="samples--double"></a><span data-ttu-id="01337-111">示例： [Double](xref:microsoft.quantum.lang-ref.double)[] []</span><span class="sxs-lookup"><span data-stu-id="01337-111">samples : [Double](xref:microsoft.quantum.lang-ref.double)[][]</span></span>

<span data-ttu-id="01337-112">要分类的每个样本的特性向量数组。</span><span class="sxs-lookup"><span data-stu-id="01337-112">An array of feature vectors for each sample to be classified.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="01337-113">nMeasurements： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="01337-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="01337-114">要在估计分类概率时使用的度量值的数量。</span><span class="sxs-lookup"><span data-stu-id="01337-114">The number of measurements to use in estimating the classification probability.</span></span>



## <a name="output--double"></a><span data-ttu-id="01337-115">输出： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="01337-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="01337-116">计算每个给定样本的分类概率的数组。</span><span class="sxs-lookup"><span data-stu-id="01337-116">An array of estimates of the classification probability for each given sample.</span></span>