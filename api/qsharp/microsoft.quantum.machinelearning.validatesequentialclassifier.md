---
uid: Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier
title: ValidateSequentialClassifier 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: ValidateSequentialClassifier
qsharp.summary: Validates a given sequential classifier against a given set of pre-labeled samples.
ms.openlocfilehash: 802f1045ea4086bd371d68018a481182cb75b209
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696718"
---
# <a name="validatesequentialclassifier-operation"></a><span data-ttu-id="a1b0c-102">ValidateSequentialClassifier 操作</span><span class="sxs-lookup"><span data-stu-id="a1b0c-102">ValidateSequentialClassifier operation</span></span>

<span data-ttu-id="a1b0c-103">命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="a1b0c-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="a1b0c-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a1b0c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a1b0c-105">针对给定的一组预标记的示例，对给定的顺序分类器进行验证。</span><span class="sxs-lookup"><span data-stu-id="a1b0c-105">Validates a given sequential classifier against a given set of pre-labeled samples.</span></span>

```qsharp
operation ValidateSequentialClassifier (model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Microsoft.Quantum.MachineLearning.LabeledSample[], tolerance : Double, nMeasurements : Int, validationSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : Microsoft.Quantum.MachineLearning.ValidationResults
```


## <a name="input"></a><span data-ttu-id="a1b0c-106">输入</span><span class="sxs-lookup"><span data-stu-id="a1b0c-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="a1b0c-107">模型： [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="a1b0c-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="a1b0c-108">要验证的顺序模型。</span><span class="sxs-lookup"><span data-stu-id="a1b0c-108">The sequential model to be validated.</span></span>


### <a name="samples--labeledsample"></a><span data-ttu-id="a1b0c-109">示例： [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]</span><span class="sxs-lookup"><span data-stu-id="a1b0c-109">samples : [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]</span></span>

<span data-ttu-id="a1b0c-110">要用于验证给定模型的示例。</span><span class="sxs-lookup"><span data-stu-id="a1b0c-110">The samples to be used to validate the given model.</span></span>


### <a name="tolerance--double"></a><span data-ttu-id="a1b0c-111">容差： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="a1b0c-111">tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="a1b0c-112">将每个样本编码为顺序分类器的输入时使用的近似值公差。</span><span class="sxs-lookup"><span data-stu-id="a1b0c-112">The approximation tolerance to use in encoding each sample as an input to the sequential classifier.</span></span>


### <a name="nmeasurements--int"></a><span data-ttu-id="a1b0c-113">nMeasurements： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a1b0c-113">nMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a1b0c-114">要用于对每个样本进行分类的度量值的数量。</span><span class="sxs-lookup"><span data-stu-id="a1b0c-114">The number of measurements to use in classifying each sample.</span></span>


### <a name="validationschedule--samplingschedule"></a><span data-ttu-id="a1b0c-115">validationSchedule： [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="a1b0c-115">validationSchedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="a1b0c-116">从验证集绘制样本的计划。</span><span class="sxs-lookup"><span data-stu-id="a1b0c-116">The schedule by which samples should be drawn from the validation set.</span></span>



## <a name="output--validationresults"></a><span data-ttu-id="a1b0c-117">输出： [ValidationResults](xref:Microsoft.Quantum.MachineLearning.ValidationResults)</span><span class="sxs-lookup"><span data-stu-id="a1b0c-117">Output : [ValidationResults](xref:Microsoft.Quantum.MachineLearning.ValidationResults)</span></span>

<span data-ttu-id="a1b0c-118">给定验证的结果。</span><span class="sxs-lookup"><span data-stu-id="a1b0c-118">The results of the given validation.</span></span>