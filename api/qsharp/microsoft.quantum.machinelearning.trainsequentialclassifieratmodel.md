---
uid: Microsoft.Quantum.MachineLearning.TrainSequentialClassifierAtModel
title: TrainSequentialClassifierAtModel 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainSequentialClassifierAtModel
qsharp.summary: Given the structure of a sequential classifier, trains the classifier on a given labeled training set, starting from a particular model.
ms.openlocfilehash: b9e30e4e5bc23f56d9119083045967caff28f13a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696720"
---
# <a name="trainsequentialclassifieratmodel-operation"></a><span data-ttu-id="c39f7-102">TrainSequentialClassifierAtModel 操作</span><span class="sxs-lookup"><span data-stu-id="c39f7-102">TrainSequentialClassifierAtModel operation</span></span>

<span data-ttu-id="c39f7-103">命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="c39f7-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="c39f7-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c39f7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c39f7-105">给定顺序分类器的结构，从特定模型开始训练给定标签定型集上的分类器。</span><span class="sxs-lookup"><span data-stu-id="c39f7-105">Given the structure of a sequential classifier, trains the classifier on a given labeled training set, starting from a particular model.</span></span>

```qsharp
operation TrainSequentialClassifierAtModel (model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Microsoft.Quantum.MachineLearning.LabeledSample[], options : Microsoft.Quantum.MachineLearning.TrainingOptions, trainingSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, validationSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : (Microsoft.Quantum.MachineLearning.SequentialModel, Int)
```


## <a name="input"></a><span data-ttu-id="c39f7-106">输入</span><span class="sxs-lookup"><span data-stu-id="c39f7-106">Input</span></span>

### <a name="model--sequentialmodel"></a><span data-ttu-id="c39f7-107">模型： [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span><span class="sxs-lookup"><span data-stu-id="c39f7-107">model : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)</span></span>

<span data-ttu-id="c39f7-108">要用作定型起点的顺序模型。</span><span class="sxs-lookup"><span data-stu-id="c39f7-108">The sequential model to be used as a starting point for training.</span></span>


### <a name="samples--labeledsample"></a><span data-ttu-id="c39f7-109">示例： [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]</span><span class="sxs-lookup"><span data-stu-id="c39f7-109">samples : [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]</span></span>

<span data-ttu-id="c39f7-110">一组用于执行定型的标记定型数据。</span><span class="sxs-lookup"><span data-stu-id="c39f7-110">A set of labeled training data that will be used to perform training.</span></span>


### <a name="options--trainingoptions"></a><span data-ttu-id="c39f7-111">选项： [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span><span class="sxs-lookup"><span data-stu-id="c39f7-111">options : [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span></span>

<span data-ttu-id="c39f7-112">训练时要使用的配置; @"microsoft.quantum.machinelearning.trainingoptions" @"microsoft.quantum.machinelearning.defaulttrainingoptions" 有关更多详细信息，请参阅和。</span><span class="sxs-lookup"><span data-stu-id="c39f7-112">Configuration to be used when training; see @"microsoft.quantum.machinelearning.trainingoptions" and @"microsoft.quantum.machinelearning.defaulttrainingoptions" for more details.</span></span>


### <a name="trainingschedule--samplingschedule"></a><span data-ttu-id="c39f7-113">trainingSchedule： [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="c39f7-113">trainingSchedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="c39f7-114">在定型步骤中从定型数据中选择样本时要使用的采样计划。</span><span class="sxs-lookup"><span data-stu-id="c39f7-114">A sampling schedule to use when selecting samples from the training data during training steps.</span></span>


### <a name="validationschedule--samplingschedule"></a><span data-ttu-id="c39f7-115">validationSchedule： [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="c39f7-115">validationSchedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="c39f7-116">当选择从定型数据中选择样本时，如果选择哪个起点导致最佳分类器分数，则使用采样计划。</span><span class="sxs-lookup"><span data-stu-id="c39f7-116">A sampling schedule to use when selecting samples from the training data when selecting which start point resulted in the best classifier score.</span></span>



## <a name="output--sequentialmodelint"></a><span data-ttu-id="c39f7-117">输出： ([SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)，[Int](xref:microsoft.quantum.lang-ref.int)) </span><span class="sxs-lookup"><span data-stu-id="c39f7-117">Output : ([SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel),[Int](xref:microsoft.quantum.lang-ref.int))</span></span>

- <span data-ttu-id="c39f7-118">给定分类器的参数化和两个类之间的偏移，同时对应于每个给定起点的最佳结果。</span><span class="sxs-lookup"><span data-stu-id="c39f7-118">A parameterization of the given classifier and a bias between the two classes, together corresponding to the best result from each of the given start points.</span></span>
- <span data-ttu-id="c39f7-119">在最佳分类器模型中观测到的未命中次数。</span><span class="sxs-lookup"><span data-stu-id="c39f7-119">The number of misses observed at the best classifier model.</span></span>

## <a name="see-also"></a><span data-ttu-id="c39f7-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c39f7-120">See Also</span></span>

- [<span data-ttu-id="c39f7-121">Default-machinelearning-southcentralus. TrainSequentialClassifier</span><span class="sxs-lookup"><span data-stu-id="c39f7-121">Microsoft.Quantum.MachineLearning.TrainSequentialClassifier</span></span>](xref:Microsoft.Quantum.MachineLearning.TrainSequentialClassifier)
- [<span data-ttu-id="c39f7-122">Default-machinelearning-southcentralus. ValidateSequentialClassifier</span><span class="sxs-lookup"><span data-stu-id="c39f7-122">Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier</span></span>](xref:Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier)