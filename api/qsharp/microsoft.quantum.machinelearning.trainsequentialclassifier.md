---
uid: Microsoft.Quantum.MachineLearning.TrainSequentialClassifier
title: TrainSequentialClassifier 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainSequentialClassifier
qsharp.summary: Given the structure of a sequential classifier, trains the classifier on a given labeled training set.
ms.openlocfilehash: 12c4df59941b682d9de798e6585b59d1c34924dc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695359"
---
# <a name="trainsequentialclassifier-operation"></a><span data-ttu-id="b3f50-102">TrainSequentialClassifier 操作</span><span class="sxs-lookup"><span data-stu-id="b3f50-102">TrainSequentialClassifier operation</span></span>

<span data-ttu-id="b3f50-103">命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="b3f50-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="b3f50-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b3f50-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b3f50-105">给定顺序分类器的结构，训练给定标记定型集上的分类器。</span><span class="sxs-lookup"><span data-stu-id="b3f50-105">Given the structure of a sequential classifier, trains the classifier on a given labeled training set.</span></span>

```qsharp
operation TrainSequentialClassifier (models : Microsoft.Quantum.MachineLearning.SequentialModel[], samples : Microsoft.Quantum.MachineLearning.LabeledSample[], options : Microsoft.Quantum.MachineLearning.TrainingOptions, trainingSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, validationSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : (Microsoft.Quantum.MachineLearning.SequentialModel, Int)
```


## <a name="input"></a><span data-ttu-id="b3f50-106">输入</span><span class="sxs-lookup"><span data-stu-id="b3f50-106">Input</span></span>

### <a name="models--sequentialmodel"></a><span data-ttu-id="b3f50-107">模型： [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)[]</span><span class="sxs-lookup"><span data-stu-id="b3f50-107">models : [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)[]</span></span>

<span data-ttu-id="b3f50-108">在定型过程中用作起点的模型的数组。</span><span class="sxs-lookup"><span data-stu-id="b3f50-108">An array of models to be used as starting points during training.</span></span>


### <a name="samples--labeledsample"></a><span data-ttu-id="b3f50-109">示例： [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]</span><span class="sxs-lookup"><span data-stu-id="b3f50-109">samples : [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]</span></span>

<span data-ttu-id="b3f50-110">一组用于执行定型的标记定型数据。</span><span class="sxs-lookup"><span data-stu-id="b3f50-110">A set of labeled training data that will be used to perform training.</span></span>


### <a name="options--trainingoptions"></a><span data-ttu-id="b3f50-111">选项： [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span><span class="sxs-lookup"><span data-stu-id="b3f50-111">options : [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)</span></span>

<span data-ttu-id="b3f50-112">训练时要使用的配置; @"microsoft.quantum.machinelearning.trainingoptions" @"microsoft.quantum.machinelearning.defaulttrainingoptions" 有关更多详细信息，请参阅和。</span><span class="sxs-lookup"><span data-stu-id="b3f50-112">Configuration to be used when training; see @"microsoft.quantum.machinelearning.trainingoptions" and @"microsoft.quantum.machinelearning.defaulttrainingoptions" for more details.</span></span>


### <a name="trainingschedule--samplingschedule"></a><span data-ttu-id="b3f50-113">trainingSchedule： [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="b3f50-113">trainingSchedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="b3f50-114">在定型步骤中从定型数据中选择样本时要使用的采样计划。</span><span class="sxs-lookup"><span data-stu-id="b3f50-114">A sampling schedule to use when selecting samples from the training data during training steps.</span></span>


### <a name="validationschedule--samplingschedule"></a><span data-ttu-id="b3f50-115">validationSchedule： [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span><span class="sxs-lookup"><span data-stu-id="b3f50-115">validationSchedule : [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)</span></span>

<span data-ttu-id="b3f50-116">当选择从定型数据中选择样本时，如果选择哪个起点导致最佳分类器分数，则使用采样计划。</span><span class="sxs-lookup"><span data-stu-id="b3f50-116">A sampling schedule to use when selecting samples from the training data when selecting which start point resulted in the best classifier score.</span></span>



## <a name="output--sequentialmodelint"></a><span data-ttu-id="b3f50-117">输出： ([SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)，[Int](xref:microsoft.quantum.lang-ref.int)) </span><span class="sxs-lookup"><span data-stu-id="b3f50-117">Output : ([SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel),[Int](xref:microsoft.quantum.lang-ref.int))</span></span>

- <span data-ttu-id="b3f50-118">给定分类器的参数化和两个类之间的偏移，同时对应于每个给定起点的最佳结果。</span><span class="sxs-lookup"><span data-stu-id="b3f50-118">A parameterization of the given classifier and a bias between the two classes, together corresponding to the best result from each of the given start points.</span></span>
- <span data-ttu-id="b3f50-119">在最佳分类器模型中观测到的未命中次数。</span><span class="sxs-lookup"><span data-stu-id="b3f50-119">The number of misses observed at the best classifier model.</span></span>

## <a name="see-also"></a><span data-ttu-id="b3f50-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b3f50-120">See Also</span></span>

- [<span data-ttu-id="b3f50-121">Default-machinelearning-southcentralus. TrainSequentialClassifierAtModel</span><span class="sxs-lookup"><span data-stu-id="b3f50-121">Microsoft.Quantum.MachineLearning.TrainSequentialClassifierAtModel</span></span>](xref:Microsoft.Quantum.MachineLearning.TrainSequentialClassifierAtModel)
- [<span data-ttu-id="b3f50-122">Default-machinelearning-southcentralus. ValidateSequentialClassifier</span><span class="sxs-lookup"><span data-stu-id="b3f50-122">Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier</span></span>](xref:Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier)