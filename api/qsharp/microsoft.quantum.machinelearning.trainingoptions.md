---
uid: Microsoft.Quantum.MachineLearning.TrainingOptions
title: TrainingOptions 用户定义的类型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainingOptions
qsharp.summary: A collection of options to be used in training quantum classifiers.
ms.openlocfilehash: 762d6853910832c6d4cda522c0c5df706d1ed195
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842781"
---
# <a name="trainingoptions-user-defined-type"></a><span data-ttu-id="04ef2-102">TrainingOptions 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="04ef2-102">TrainingOptions user defined type</span></span>

<span data-ttu-id="04ef2-103">命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="04ef2-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="04ef2-104">Package： [default-machinelearning-southcentralus](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="04ef2-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="04ef2-105">用于训练量子分类器的选项的集合。</span><span class="sxs-lookup"><span data-stu-id="04ef2-105">A collection of options to be used in training quantum classifiers.</span></span>

```qsharp

newtype TrainingOptions = (LearningRate : Double, Tolerance : Double, MinibatchSize : Int, NMeasurements : Int, MaxEpochs : Int, MaxStalls : Int, StochasticRescaleFactor : Double, ScoringPeriod : Int, VerboseMessage : (String -> Unit));
```



## <a name="named-items"></a><span data-ttu-id="04ef2-106">命名项</span><span class="sxs-lookup"><span data-stu-id="04ef2-106">Named Items</span></span>

### <a name="learningrate--double"></a><span data-ttu-id="04ef2-107">Learningrate 超出： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="04ef2-107">LearningRate : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="04ef2-108">在定型步骤中更新模型参数时，重新缩放渐变应使用的学习速率。</span><span class="sxs-lookup"><span data-stu-id="04ef2-108">The learning rate by which gradients should be rescaled when updating model parameters during training steps.</span></span>
### <a name="tolerance--double"></a><span data-ttu-id="04ef2-109">容差： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="04ef2-109">Tolerance : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="04ef2-110">准备作为量程状态的示例时要使用的近似值。</span><span class="sxs-lookup"><span data-stu-id="04ef2-110">The approximation tolerance to use when preparing samples as quantum states.</span></span>
### <a name="minibatchsize--int"></a><span data-ttu-id="04ef2-111">MinibatchSize： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="04ef2-111">MinibatchSize : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="04ef2-112">每个定型 minibatch 中要使用的样本数。</span><span class="sxs-lookup"><span data-stu-id="04ef2-112">The number of samples to use in each training minibatch.</span></span>
### <a name="nmeasurements--int"></a><span data-ttu-id="04ef2-113">NMeasurements： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="04ef2-113">NMeasurements : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="04ef2-114">测量每个分类结果以便估算分类概率的次数。</span><span class="sxs-lookup"><span data-stu-id="04ef2-114">The number of times to measure each classification result in order to estimate the classification probability.</span></span>
### <a name="maxepochs--int"></a><span data-ttu-id="04ef2-115">MaxEpochs： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="04ef2-115">MaxEpochs : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="04ef2-116">要为每个模型定型的最大时期数。</span><span class="sxs-lookup"><span data-stu-id="04ef2-116">The maximum number of epochs to train each model for.</span></span>
### <a name="maxstalls--int"></a><span data-ttu-id="04ef2-117">MaxStalls： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="04ef2-117">MaxStalls : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="04ef2-118">允许定型 epoch 延迟的最大次数 (在发生故障之前约) 的渐变。</span><span class="sxs-lookup"><span data-stu-id="04ef2-118">The maximum number of times a training epoch is allowed to stall (approximately zero gradient) before failing.</span></span>
### <a name="stochasticrescalefactor--double"></a><span data-ttu-id="04ef2-119">StochasticRescaleFactor： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="04ef2-119">StochasticRescaleFactor : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="04ef2-120">重试更新前重新缩放已停止的模型的量。</span><span class="sxs-lookup"><span data-stu-id="04ef2-120">The amount to rescale stalled models by before retrying an update.</span></span>
### <a name="scoringperiod--int"></a><span data-ttu-id="04ef2-121">ScoringPeriod： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="04ef2-121">ScoringPeriod : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="04ef2-122">要在计分点之间执行的渐变步骤数。</span><span class="sxs-lookup"><span data-stu-id="04ef2-122">The number of gradient steps to be taken between scoring points.</span></span>
<span data-ttu-id="04ef2-123">为获得最佳准确性，请将设置为1。</span><span class="sxs-lookup"><span data-stu-id="04ef2-123">For best accuracy, set to 1.</span></span>
### <a name="verbosemessage--string---unit"></a><span data-ttu-id="04ef2-124">VerboseMessage： [String](xref:microsoft.quantum.lang-ref.string) -> [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="04ef2-124">VerboseMessage : [String](xref:microsoft.quantum.lang-ref.string) -> [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="04ef2-125">可用于提供详细反馈的函数。</span><span class="sxs-lookup"><span data-stu-id="04ef2-125">A function that can be used to provide verbose feedback.</span></span>

## <a name="remarks"></a><span data-ttu-id="04ef2-126">备注</span><span class="sxs-lookup"><span data-stu-id="04ef2-126">Remarks</span></span>

<span data-ttu-id="04ef2-127">不应直接创建此 UDT，而应通过调用 @"microsoft.quantum.machinelearning.defaulttrainingoptions" 并使用 `w/` 运算符重写不同的默认值来指定它。</span><span class="sxs-lookup"><span data-stu-id="04ef2-127">This UDT should not be created directly, but rather should be specified by calling @"microsoft.quantum.machinelearning.defaulttrainingoptions" and then using the `w/` operator to override different defaults.</span></span>

<span data-ttu-id="04ef2-128">例如，若要使用100000度量值和最多8个定型时期：</span><span class="sxs-lookup"><span data-stu-id="04ef2-128">For example, to use 100,000 measurements and at most 8 training epochs:</span></span>

```qsharp
let options = DefaultTrainingOptions()
              w/ NMeasurements <- 100000
              w/ MaxEpochs <- 8;
```

## <a name="references"></a><span data-ttu-id="04ef2-129">参考</span><span class="sxs-lookup"><span data-stu-id="04ef2-129">References</span></span>

- [<span data-ttu-id="04ef2-130">arXiv:1804.00633</span><span class="sxs-lookup"><span data-stu-id="04ef2-130">arXiv:1804.00633</span></span>](https://arxiv.org/abs/1804.00633)