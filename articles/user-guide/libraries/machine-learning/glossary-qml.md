---
title: 量子机器学习库
author: alexeib2
ms.author: alexei.bocharov@microsoft.com
ms.date: 2/27/2020
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.training
ms.openlocfilehash: f9b33a607a892179795d0700ba3080f9a24ab94a
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274468"
---
# <a name="quantum-machine-learning-glossary"></a>量程机器学习术语表

针对以线路为中心的量程分类器的训练是指多个移动部件，这些部件需要通过试用和错误进行的校准量与传统分类器的定型相同（或略大）。 这里，我们定义了本训练过程的主要概念和组成部分。

## <a name="trainingtesting-schedules"></a>训练/测试计划

在分类器培训的上下文中，*计划*介绍了整体定型或测试集中的一部分数据样本。 计划通常定义为示例索引的集合。

## <a name="parameterbias-scores"></a>参数/偏向分数

给定候选参数向量和分类符偏移，其*验证分数*是相对于所选验证计划的度量值，并由按计划中的所有示例计数的 misclassifications 表示。

## <a name="hyperparameters"></a>超参数

模型定型过程由名为*超参数*的某些预先设置的值控制：

### <a name="learning-rate"></a>学习速率

它是关键超参数之一。 它定义当前随机梯度估算对参数更新有何影响。 参数更新增量的大小与学习速率成正比。 较小的学习速率值导致较慢的参数演变和较慢的聚合，但如果渐变下降从不提交到特定的最小值，则 LR 的值会完全突破。 尽管培训算法在一定程度上由定型算法自适应调整，但为它选择一个很好的初始值非常重要。 学习速率的常用默认初始值为0.1。 选择最佳学习速率值是一种不错的选择（例如，Goodfellow et al 的第4.3 节，"深度学习"，MIT 按，2017）。

### <a name="minibatch-size"></a>Minibatch 大小

定义用于单个随机渐变计算的数据示例数。 较大的 minibatch 大小值通常会导致更强大和更单调的聚合，但可能会降低定型过程的速度，因为任何一个渐变估算的成本都与 minimatch 大小成正比。 Minibatch 大小的常用默认值为10。

### <a name="training-epochs-tolerance-gridlocks"></a>定型时期、容差、gridlocks

"Epoch" 表示通过计划的定型数据完成一次。
每个定型线程的最大时期数（见下文）应被限制。 在执行了最大数量的时期后，定型线程定义为终止（带有最佳的候选参数）。 不过，如果验证计划的错误分类率低于所选的容差，此类培训会提前终止。 例如，假设错误分类容差为0.01 （1%）; 如果在2000样本验证集上看到的 misclassifications 少于20个，则实现了容差级别。 如果候选模型的验证分数未显示对多个连续时期（停滞不前）的任何改进，则定型线程也会提前终止。 当前对停滞不前终止的逻辑进行了硬编码。

### <a name="measurements-count"></a>度量值计数

在量程设备上估算随机渐变的定型/验证分数和分量，以估计需要对适当可观察量进行多次度量的量程状态重叠。 度量值的缩放比例应为 $O （1/\ epsilon ^ 2） $，其中 $ \epsilon $ 是所需的估计错误。
根据经验法则，初始度量值计数可以是大约 $ 1/\ mbox {容差} ^ 2 $ （请参阅上一段落中的容差定义）。 如果梯度下降表现太多并导致难以实现，则需要修改测量计数。

### <a name="training-threads"></a>训练线程

作为分类器训练实用程序的可能性很小，这意味着它通常在参数空间中有大量的本地 optima，它们在质量上可能会有很大差异。 由于 SGD 进程只能汇聚到一个特定的最佳方法，因此必须探索多个起始参数向量。 机器学习的常见做法是，随机初始化此类起始向量。 Q # 训练 API 接受此类起始向量的任意数组，但基础代码会按顺序对其进行探讨。 在多核计算机上，或在任何并行计算体系结构上，都建议并行执行多个对 Q # 定型 API 的调用，并跨调用进行不同的参数初始化。

#### <a name="how-to-modify-the-hyperparameters"></a>如何修改超参数

在 QML 库中，修改超参数的最佳方式是替代 UDT 的默认值 [`TrainingOptions`](xref:microsoft.quantum.machinelearning.trainingoptions) 。 为此，我们使用函数调用它 [`DefaultTrainingOptions`](xref:microsoft.quantum.machinelearning.defaulttrainingoptions) ，并应用运算符 `w/` 来替代默认值。 例如，若要使用100000度量值和0.01 的学习率：
 ```qsharp
let options = DefaultTrainingOptions()
w/ LearningRate <- 0.01
w/ NMeasurements <- 100000;
 ```