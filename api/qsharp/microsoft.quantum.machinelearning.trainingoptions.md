---
uid: Microsoft.Quantum.MachineLearning.TrainingOptions
title: TrainingOptions 用户定义的类型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainingOptions
qsharp.summary: A collection of options to be used in training quantum classifiers.
ms.openlocfilehash: 5ecc2b5175a4e8db78f72311ac1d5ff964bae811
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700253"
---
# <a name="trainingoptions-user-defined-type"></a><span data-ttu-id="09056-102">TrainingOptions 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="09056-102">TrainingOptions user defined type</span></span>

<span data-ttu-id="09056-103">命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="09056-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="09056-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="09056-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="09056-105">用于训练量子分类器的选项的集合。</span><span class="sxs-lookup"><span data-stu-id="09056-105">A collection of options to be used in training quantum classifiers.</span></span>

```qsharp

newtype TrainingOptions = (LearningRate : Double, Tolerance : Double, MinibatchSize : Int, NMeasurements : Int, MaxEpochs : Int, MaxStalls : Int, StochasticRescaleFactor : Double, ScoringPeriod : Int, VerboseMessage : (String -> Unit));
```



## <a name="named-items"></a><span data-ttu-id="09056-106">命名项</span><span class="sxs-lookup"><span data-stu-id="09056-106">Named Items</span></span>

### <a name="learningrate--double"></a><span data-ttu-id="09056-107">Learningrate 超出： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="09056-107">LearningRate : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="09056-108">在定型步骤中更新模型参数时，重新缩放渐变应使用的学习速率。</span><span class="sxs-lookup"><span data-stu-id="09056-108">The learning rate by which gradients should be rescaled when updating model parameters during training steps.</span></span>
### <a name="tolerance--double"></a><span data-ttu-id="09056-109">容差： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="09056-109">Tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="09056-110">准备作为量程状态的示例时要使用的近似值。</span><span class="sxs-lookup"><span data-stu-id="09056-110">The approximation tolerance to use when preparing samples as quantum states.</span></span>
### <a name="minibatchsize--int"></a><span data-ttu-id="09056-111">MinibatchSize： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="09056-111">MinibatchSize : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="09056-112">每个定型 minibatch 中要使用的样本数。</span><span class="sxs-lookup"><span data-stu-id="09056-112">The number of samples to use in each training minibatch.</span></span>
### <a name="nmeasurements--int"></a><span data-ttu-id="09056-113">NMeasurements： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="09056-113">NMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="09056-114">测量每个分类结果以便估算分类概率的次数。</span><span class="sxs-lookup"><span data-stu-id="09056-114">The number of times to measure each classification result in order to estimate the classification probability.</span></span>
### <a name="maxepochs--int"></a><span data-ttu-id="09056-115">MaxEpochs： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="09056-115">MaxEpochs : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="09056-116">要为每个模型定型的最大时期数。</span><span class="sxs-lookup"><span data-stu-id="09056-116">The maximum number of epochs to train each model for.</span></span>
### <a name="maxstalls--int"></a><span data-ttu-id="09056-117">MaxStalls： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="09056-117">MaxStalls : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="09056-118">允许定型 epoch 延迟的最大次数 (在发生故障之前约) 的渐变。</span><span class="sxs-lookup"><span data-stu-id="09056-118">The maximum number of times a training epoch is allowed to stall (approximately zero gradient) before failing.</span></span>
### <a name="stochasticrescalefactor--double"></a><span data-ttu-id="09056-119">StochasticRescaleFactor： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="09056-119">StochasticRescaleFactor : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="09056-120">重试更新前重新缩放已停止的模型的量。</span><span class="sxs-lookup"><span data-stu-id="09056-120">The amount to rescale stalled models by before retrying an update.</span></span>
### <a name="scoringperiod--int"></a><span data-ttu-id="09056-121">ScoringPeriod： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="09056-121">ScoringPeriod : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="09056-122">要在计分点之间执行的渐变步骤数。</span><span class="sxs-lookup"><span data-stu-id="09056-122">The number of gradient steps to be taken between scoring points.</span></span>
<span data-ttu-id="09056-123">为获得最佳准确性，请将设置为1。</span><span class="sxs-lookup"><span data-stu-id="09056-123">For best accuracy, set to 1.</span></span>
### <a name="verbosemessage--string---unit"></a><span data-ttu-id="09056-124">VerboseMessage： [String](xref:microsoft.quantum.lang-ref.string) -> [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="09056-124">VerboseMessage : [String](xref:microsoft.quantum.lang-ref.string) -> [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="09056-125">可用于提供详细反馈的函数。</span><span class="sxs-lookup"><span data-stu-id="09056-125">A function that can be used to provide verbose feedback.</span></span>

## <a name="remarks"></a><span data-ttu-id="09056-126">注解</span><span class="sxs-lookup"><span data-stu-id="09056-126">Remarks</span></span>

<span data-ttu-id="09056-127">不应直接创建此 UDT，而应通过调用 @"microsoft.quantum.machinelearning.defaulttrainingoptions" 并使用 `w/` 运算符重写不同的默认值来指定它。</span><span class="sxs-lookup"><span data-stu-id="09056-127">This UDT should not be created directly, but rather should be specified by calling @"microsoft.quantum.machinelearning.defaulttrainingoptions" and then using the `w/` operator to override different defaults.</span></span>

<span data-ttu-id="09056-128">例如，若要使用100000度量值和最多8个定型时期：</span><span class="sxs-lookup"><span data-stu-id="09056-128">For example, to use 100,000 measurements and at most 8 training epochs:</span></span>

```Q#
let options = DefaultTrainingOptions()
              w/ NMeasurements <- 100000
              w/ MaxEpochs <- 8;
```

## <a name="references"></a><span data-ttu-id="09056-129">参考</span><span class="sxs-lookup"><span data-stu-id="09056-129">References</span></span>

- [<span data-ttu-id="09056-130">arXiv:1804.00633</span><span class="sxs-lookup"><span data-stu-id="09056-130">arXiv:1804.00633</span></span>](https://arxiv.org/abs/1804.00633)