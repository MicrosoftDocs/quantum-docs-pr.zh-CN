---
title: 量程机器学习库术语表
author: alexeib2
ms.author: alexei.bocharov@microsoft.com
ms.date: 2/27/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.training
no-loc:
- Q#
- $$v
ms.openlocfilehash: 068fc61d0d7c066df1270384679e13a3b3a8c878
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863033"
---
# <a name="quantum-machine-learning-glossary"></a><span data-ttu-id="e110a-102">量程机器学习术语表</span><span class="sxs-lookup"><span data-stu-id="e110a-102">Quantum Machine Learning glossary</span></span>

<span data-ttu-id="e110a-103">对以线路为中心的量程分类器的训练是指多个移动部件的过程，这些部件需要相同的 (或稍) 大一些的校准，如使用传统分类器进行定型时的试用和错误。</span><span class="sxs-lookup"><span data-stu-id="e110a-103">Training of a circuit-centric quantum classifier is a process with many moving parts that require the same (or slightly larger) amount of calibration by trial and error as training of traditional classifiers.</span></span> <span data-ttu-id="e110a-104">这里，我们定义了本训练过程的主要概念和组成部分。</span><span class="sxs-lookup"><span data-stu-id="e110a-104">Here we define the main concepts and ingredients of this training process.</span></span>

## <a name="trainingtesting-schedules"></a><span data-ttu-id="e110a-105">训练/测试计划</span><span class="sxs-lookup"><span data-stu-id="e110a-105">Training/testing schedules</span></span>

<span data-ttu-id="e110a-106">在分类器培训的上下文中， *计划* 介绍了整体定型或测试集中的一部分数据样本。</span><span class="sxs-lookup"><span data-stu-id="e110a-106">In the context of classifier training a *schedule* describes a subset of data samples in an overall training or testing set.</span></span> <span data-ttu-id="e110a-107">计划通常定义为示例索引的集合。</span><span class="sxs-lookup"><span data-stu-id="e110a-107">A schedule is usually defined as a collection of sample indices.</span></span>

## <a name="parameterbias-scores"></a><span data-ttu-id="e110a-108">参数/偏向分数</span><span class="sxs-lookup"><span data-stu-id="e110a-108">Parameter/bias scores</span></span>

<span data-ttu-id="e110a-109">给定候选参数向量和分类符偏移，其 *验证分数* 是相对于所选验证计划的度量值，并由按计划中的所有示例计数的 misclassifications 表示。</span><span class="sxs-lookup"><span data-stu-id="e110a-109">Given a candidate parameter vector and a classifier bias, their *validation score* is measured relative to a chosen validation schedule S and is expressed by a number of misclassifications counted over all the samples in the schedule S.</span></span>

## <a name="hyperparameters"></a><span data-ttu-id="e110a-110">超参数</span><span class="sxs-lookup"><span data-stu-id="e110a-110">Hyperparameters</span></span>

<span data-ttu-id="e110a-111">模型定型过程由名为 *超参数*的某些预先设置的值控制：</span><span class="sxs-lookup"><span data-stu-id="e110a-111">The model training process is governed by certain pre-set values called *hyperparameters*:</span></span>

### <a name="learning-rate"></a><span data-ttu-id="e110a-112">学习速率</span><span class="sxs-lookup"><span data-stu-id="e110a-112">Learning rate</span></span>

<span data-ttu-id="e110a-113">它是关键超参数之一。</span><span class="sxs-lookup"><span data-stu-id="e110a-113">It is one of the key hyperparameters.</span></span> <span data-ttu-id="e110a-114">它定义当前随机梯度估算对参数更新有何影响。</span><span class="sxs-lookup"><span data-stu-id="e110a-114">It defines how much current stochastic gradient estimate impacts the parameter update.</span></span> <span data-ttu-id="e110a-115">参数更新增量的大小与学习速率成正比。</span><span class="sxs-lookup"><span data-stu-id="e110a-115">The size of parameter update delta is proportional to the learning rate.</span></span> <span data-ttu-id="e110a-116">较小的学习速率值导致较慢的参数演变和较慢的聚合，但如果渐变下降从不提交到特定的最小值，则 LR 的值会完全突破。</span><span class="sxs-lookup"><span data-stu-id="e110a-116">Smaller learning rate values lead to slower parameter evolution and slower convergence, but excessively large values of LR may break the convergence altogether as the gradient descent never commits to a particular local minimum.</span></span> <span data-ttu-id="e110a-117">尽管培训算法在一定程度上由定型算法自适应调整，但为它选择一个很好的初始值非常重要。</span><span class="sxs-lookup"><span data-stu-id="e110a-117">While learning rate is adaptively adjusted by the training algorithm to some extent, selecting a good initial value for it is important.</span></span> <span data-ttu-id="e110a-118">学习速率的常用默认初始值为0.1。</span><span class="sxs-lookup"><span data-stu-id="e110a-118">A usual default initial value for learning rate is 0.1.</span></span> <span data-ttu-id="e110a-119">选择 "学习速率" 的最佳值是一种不错的 (参阅 Goodfellow et al 的第4.3 节，"深度学习"，MIT 按，2017) 。</span><span class="sxs-lookup"><span data-stu-id="e110a-119">Selecting the best value of learning rate is a fine art (see, for example, section 4.3 of Goodfellow et al.,"Deep learning", MIT Press, 2017).</span></span>

### <a name="minibatch-size"></a><span data-ttu-id="e110a-120">Minibatch 大小</span><span class="sxs-lookup"><span data-stu-id="e110a-120">Minibatch size</span></span>

<span data-ttu-id="e110a-121">定义用于单个随机渐变计算的数据示例数。</span><span class="sxs-lookup"><span data-stu-id="e110a-121">Defines how many data samples is used for a single estimation of stochastic gradient.</span></span> <span data-ttu-id="e110a-122">较大的 minibatch 大小值通常会导致更强大和更单调的聚合，但可能会降低定型过程的速度，因为任何一个渐变估算的成本都与 minimatch 大小成正比。</span><span class="sxs-lookup"><span data-stu-id="e110a-122">Larger values of minibatch size generally lead to more robust and more monotonic convergence but can potentially slow down the training process, as the cost of any one gradient estimation is proportional to the minimatch size.</span></span> <span data-ttu-id="e110a-123">Minibatch 大小的常用默认值为10。</span><span class="sxs-lookup"><span data-stu-id="e110a-123">A usual default value for the minibatch size is 10.</span></span>

### <a name="training-epochs-tolerance-gridlocks"></a><span data-ttu-id="e110a-124">定型时期、容差、gridlocks</span><span class="sxs-lookup"><span data-stu-id="e110a-124">Training epochs, tolerance, gridlocks</span></span>

<span data-ttu-id="e110a-125">"Epoch" 表示通过计划的定型数据完成一次。</span><span class="sxs-lookup"><span data-stu-id="e110a-125">"Epoch" means one complete pass through the scheduled training data.</span></span>
<span data-ttu-id="e110a-126">) 应限制每个定型线程 (的最大时期数。</span><span class="sxs-lookup"><span data-stu-id="e110a-126">The maximum number of epochs per a training thread (see below) should be capped.</span></span> <span data-ttu-id="e110a-127">训练线程定义为在执行了时期的最大数目后终止 (具有最佳的候选参数) 。</span><span class="sxs-lookup"><span data-stu-id="e110a-127">The training thread is defined to terminate (with the best known candidate parameters) when the maximum number of epochs has been executed.</span></span> <span data-ttu-id="e110a-128">不过，如果验证计划的错误分类率低于所选的容差，此类培训会提前终止。</span><span class="sxs-lookup"><span data-stu-id="e110a-128">However such training would terminate earlier when misclassification rate on validation schedule falls below a chosen tolerance.</span></span> <span data-ttu-id="e110a-129">例如，假设错误分类公差为 0.01 (1% ) ;如果在2000示例的验证集上看到的 misclassifications 少于20个，则实现公差级别。</span><span class="sxs-lookup"><span data-stu-id="e110a-129">Suppose, for example, that misclassification tolerance is 0.01 (1%); if on validation set of 2000 samples we are seeing fewer than 20 misclassifications, then the tolerance level has been achieved.</span></span> <span data-ttu-id="e110a-130">如果候选模型的验证分数未显示对多个连续时期 (停滞不前) 的任何改进，则定型线程也会提前终止。</span><span class="sxs-lookup"><span data-stu-id="e110a-130">A training thread also terminates prematurely if the validation score of the candidate model has not shown any improvement over several consecutive epochs (a gridlock).</span></span> <span data-ttu-id="e110a-131">当前对停滞不前终止的逻辑进行了硬编码。</span><span class="sxs-lookup"><span data-stu-id="e110a-131">The logic for the gridlock termination is currently hardcoded.</span></span>

### <a name="measurements-count"></a><span data-ttu-id="e110a-132">度量值计数</span><span class="sxs-lookup"><span data-stu-id="e110a-132">Measurements count</span></span>

<span data-ttu-id="e110a-133">在量程设备上估算随机渐变的定型/验证分数和分量，以估计需要对适当可观察量进行多次度量的量程状态重叠。</span><span class="sxs-lookup"><span data-stu-id="e110a-133">Estimating the training/validation scores and the components of the stochastic gradient on a quantum device amounts to estimating quantum state overlaps that requires multiple measurements of the appropriate observables.</span></span> <span data-ttu-id="e110a-134">度量值的缩放比例应为 $O (1/\ epsilon ^ 2) $，其中 $ \epsilon $ 是所需的估计错误。</span><span class="sxs-lookup"><span data-stu-id="e110a-134">The number of measurements should scale as $O(1/\epsilon^2)$ where $\epsilon$ is the desired estimation error.</span></span>
<span data-ttu-id="e110a-135">根据经验法则，初始度量值计数可以是大约 $ 1/\ mbox {容差} ^ 2 $ (请参阅上一段落) 中的容差定义。</span><span class="sxs-lookup"><span data-stu-id="e110a-135">As a rule of thumb, the initial measurements count could be approximately $1/\mbox{tolerance}^2$ (see definition of tolerance in the previous paragraph).</span></span> <span data-ttu-id="e110a-136">如果梯度下降表现太多并导致难以实现，则需要修改测量计数。</span><span class="sxs-lookup"><span data-stu-id="e110a-136">One would need to revise the measurement count upward if the gradient descent appears to be too erratic and convergence too hard to achieve.</span></span>

### <a name="training-threads"></a><span data-ttu-id="e110a-137">训练线程</span><span class="sxs-lookup"><span data-stu-id="e110a-137">Training threads</span></span>

<span data-ttu-id="e110a-138">作为分类器训练实用程序的可能性很小，这意味着它通常在参数空间中有大量的本地 optima，它们在质量上可能会有很大差异。</span><span class="sxs-lookup"><span data-stu-id="e110a-138">The likelihood function which is the training utility for the classifier is very seldom convex, meaning that it usually has a multitude of local optima in the parameter space that may differ significantly by quality.</span></span> <span data-ttu-id="e110a-139">由于 SGD 进程只能汇聚到一个特定的最佳方法，因此必须探索多个起始参数向量。</span><span class="sxs-lookup"><span data-stu-id="e110a-139">Since the SGD process can converge to only one specific optimum, it is important to explore multiple starting parameter vectors.</span></span> <span data-ttu-id="e110a-140">机器学习的常见做法是，随机初始化此类起始向量。</span><span class="sxs-lookup"><span data-stu-id="e110a-140">Common practice in machine learning is to initialize such starting vectors randomly.</span></span> <span data-ttu-id="e110a-141">Q#训练 API 接受此类起始向量的任意数组，但基础代码会按顺序对其进行探讨。</span><span class="sxs-lookup"><span data-stu-id="e110a-141">The Q# training API accepts an arbitrary array of such starting vectors but the underlying code explores them sequentially.</span></span> <span data-ttu-id="e110a-142">在多核计算机上，或在任何并行计算体系结构上，建议使用多个调用来 Q# 与跨调用的不同参数初始化并行执行多个定型 API 调用。</span><span class="sxs-lookup"><span data-stu-id="e110a-142">On a multicore computer or in fact on any parallel computing architecture it is advisable to perform several calls to Q# training API in parallel with different parameter initializations across the calls.</span></span>

#### <a name="how-to-modify-the-hyperparameters"></a><span data-ttu-id="e110a-143">如何修改超参数</span><span class="sxs-lookup"><span data-stu-id="e110a-143">How to modify the hyperparameters</span></span>

<span data-ttu-id="e110a-144">在 QML 库中，修改超参数的最佳方式是替代 UDT 的默认值 [`TrainingOptions`](xref:microsoft.quantum.machinelearning.trainingoptions) 。</span><span class="sxs-lookup"><span data-stu-id="e110a-144">In the QML library, the best way to modify the hyperparameters is by overriding the default values of the UDT [`TrainingOptions`](xref:microsoft.quantum.machinelearning.trainingoptions).</span></span> <span data-ttu-id="e110a-145">为此，我们使用函数调用它 [`DefaultTrainingOptions`](xref:microsoft.quantum.machinelearning.defaulttrainingoptions) ，并应用运算符 `w/` 来替代默认值。</span><span class="sxs-lookup"><span data-stu-id="e110a-145">To do this we call it with the function [`DefaultTrainingOptions`](xref:microsoft.quantum.machinelearning.defaulttrainingoptions) and apply the operator `w/` to override the default values.</span></span> <span data-ttu-id="e110a-146">例如，若要使用100000度量值和0.01 的学习率：</span><span class="sxs-lookup"><span data-stu-id="e110a-146">For example, to use 100,000 measurements and a learning rate of 0.01:</span></span>
 ```qsharp
let options = DefaultTrainingOptions()
w/ LearningRate <- 0.01
w/ NMeasurements <- 100000;
 ```
