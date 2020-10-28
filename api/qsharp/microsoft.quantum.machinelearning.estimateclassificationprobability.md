---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbability
title: EstimateClassificationProbability 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbability
qsharp.summary: Given a sample and a sequential classifier, estimates the classification probability for that sample by repeatedly measuring the output of the classifier on the given sample.
ms.openlocfilehash: 79e40bc4bc0954dc6742307122609950bf22ec71
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695140"
---
# <a name="estimateclassificationprobability-operation"></a><span data-ttu-id="4c70d-102">EstimateClassificationProbability 操作</span><span class="sxs-lookup"><span data-stu-id="4c70d-102">EstimateClassificationProbability operation</span></span>

<span data-ttu-id="4c70d-103">命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="4c70d-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="4c70d-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4c70d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4c70d-105">给定一个示例和顺序分类器，通过反复测量给定示例中分类器的输出来估计该样本的分类概率。</span><span class="sxs-lookup"><span data-stu-id="4c70d-105">Given a sample and a sequential classifier, estimates the classification probability for that sample by repeatedly measuring the output of the classifier on the given sample.</span></span>

```qsharp
operation EstimateClassificationProbability (tolerance : Double, model : Microsoft.Quantum.MachineLearning.SequentialModel, sample : Double[], nMeasurements : Int) : Double
```


## <a name="input"></a><span data-ttu-id="4c70d-106">输入</span><span class="sxs-lookup"><span data-stu-id="4c70d-106">Input</span></span>

### <a name="tolerance--double"></a><span data-ttu-id="4c70d-107">容差： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4c70d-107">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4c70d-108">在将示例编码为状态准备操作时允许的容差。</span><span class="sxs-lookup"><span data-stu-id="4c70d-108">The tolerance to allow in encoding the sample into a state preparation operation.</span></span>


### <a name="model--sequentialmodel"></a><span data-ttu-id="4c70d-109">模型： [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="4c70d-109">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="4c70d-110">用于估算给定示例的分类概率的顺序模型。</span><span class="sxs-lookup"><span data-stu-id="4c70d-110">The sequential model to be used to estimate the classification probability for the given sample.</span></span>


### <a name="sample--double"></a><span data-ttu-id="4c70d-111">示例： [Double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="4c70d-111">sample : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="4c70d-112">要分类的示例的功能向量。</span><span class="sxs-lookup"><span data-stu-id="4c70d-112">The feature vector for the sample to be classified.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="4c70d-113">nMeasurements： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4c70d-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4c70d-114">要在估计分类概率时使用的度量值的数量。</span><span class="sxs-lookup"><span data-stu-id="4c70d-114">The number of measurements to use in estimating the classification probability.</span></span>



## <a name="output--double"></a><span data-ttu-id="4c70d-115">输出： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="4c70d-115">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="4c70d-116">给定样本的分类概率的估计值。</span><span class="sxs-lookup"><span data-stu-id="4c70d-116">An estimate of the classification probability for the given sample.</span></span>