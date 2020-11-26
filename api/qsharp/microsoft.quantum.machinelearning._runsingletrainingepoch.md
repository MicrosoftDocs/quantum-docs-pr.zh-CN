---
uid: Microsoft.Quantum.MachineLearning._RunSingleTrainingEpoch
title: _RunSingleTrainingEpoch 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: _RunSingleTrainingEpoch
qsharp.summary: Perform one epoch of sequential classifier training on a subset of data samples.
ms.openlocfilehash: 71780645a025972f11f32f8ba8fd94d098604f9e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196746"
---
# <a name="_runsingletrainingepoch-operation"></a><span data-ttu-id="733b3-102">_RunSingleTrainingEpoch 操作</span><span class="sxs-lookup"><span data-stu-id="733b3-102">_RunSingleTrainingEpoch operation</span></span>

<span data-ttu-id="733b3-103">命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="733b3-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="733b3-104">Package： [default-machinelearning-southcentralus](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="733b3-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="733b3-105">在部分数据示例中执行顺序分类器培训的一个时期。</span><span class="sxs-lookup"><span data-stu-id="733b3-105">Perform one epoch of sequential classifier training on a subset of data samples.</span></span>

```qsharp
operation _RunSingleTrainingEpoch (encodedSamples : (Microsoft.Quantum.MachineLearning.LabeledSample, Microsoft.Quantum.MachineLearning.StateGenerator)[], schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, periodScore : Int, options : Microsoft.Quantum.MachineLearning.TrainingOptions, model : Microsoft.Quantum.MachineLearning.SequentialModel, nPreviousBestMisses : Int) : (Int, Microsoft.Quantum.MachineLearning.SequentialModel)
```


## <a name="input"></a><span data-ttu-id="733b3-106">输入</span><span class="sxs-lookup"><span data-stu-id="733b3-106">Input</span></span>

### <a name="encodedsamples--labeledsamplestategenerator"></a><span data-ttu-id="733b3-107">encodedSamples： ([LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)，[StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)) []</span><span class="sxs-lookup"><span data-stu-id="733b3-107">encodedSamples : ([LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample),[StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator))[]</span></span>




### <a name="schedule--samplingschedule"></a><span data-ttu-id="733b3-108">计划： [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="733b3-108">schedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>




### <a name="periodscore--int"></a><span data-ttu-id="733b3-109">periodScore： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="733b3-109">periodScore : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="733b3-110">要在计分点之间执行的渐变步骤数。</span><span class="sxs-lookup"><span data-stu-id="733b3-110">The number of gradient steps to be taken between scoring points.</span></span>
<span data-ttu-id="733b3-111">为获得最佳准确性，请将设置为1。</span><span class="sxs-lookup"><span data-stu-id="733b3-111">For best accuracy, set to 1.</span></span>


### <a name="options--trainingoptions"></a><span data-ttu-id="733b3-112">选项： [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span><span class="sxs-lookup"><span data-stu-id="733b3-112">options : [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span></span>

<span data-ttu-id="733b3-113">要在定型中使用的选项。</span><span class="sxs-lookup"><span data-stu-id="733b3-113">Options to be used in training.</span></span>


### <a name="model--sequentialmodel"></a><span data-ttu-id="733b3-114">模型： [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="733b3-114">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="733b3-115">要定型的顺序模型。</span><span class="sxs-lookup"><span data-stu-id="733b3-115">The sequential model to be trained.</span></span>


### <a name="npreviousbestmisses--int"></a><span data-ttu-id="733b3-116">nPreviousBestMisses： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="733b3-116">nPreviousBestMisses : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="733b3-117">在以前的时期中观察到的 misclassifications 的最佳数量。</span><span class="sxs-lookup"><span data-stu-id="733b3-117">The best number of misclassifications observed in previous epochs.</span></span>



## <a name="output--intsequentialmodel"></a><span data-ttu-id="733b3-118">Output： ([Int](xref:microsoft.quantum.lang-ref.int)，[SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)) </span><span class="sxs-lookup"><span data-stu-id="733b3-118">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel))</span></span>

- <span data-ttu-id="733b3-119">观察到的 misclassifications 的最小数目。</span><span class="sxs-lookup"><span data-stu-id="733b3-119">The smallest number of misclassifications observed through to this epoch.</span></span>
- <span data-ttu-id="733b3-120">找到新的最佳顺序模型。</span><span class="sxs-lookup"><span data-stu-id="733b3-120">The new best sequential model found.</span></span>