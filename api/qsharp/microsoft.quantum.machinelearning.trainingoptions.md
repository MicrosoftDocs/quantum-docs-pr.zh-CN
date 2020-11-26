---
uid: Microsoft.Quantum.MachineLearning.TrainingOptions
title: TrainingOptions 用户定义的类型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainingOptions
qsharp.summary: A collection of options to be used in training quantum classifiers.
ms.openlocfilehash: 280a3857aa7bc42f636a33f893d4f450e79b6a6a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196117"
---
# <a name="trainingoptions-user-defined-type"></a>TrainingOptions 用户定义的类型

命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)

Package： [default-machinelearning-southcentralus](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


用于训练量子分类器的选项的集合。

```qsharp

newtype TrainingOptions = (LearningRate : Double, Tolerance : Double, MinibatchSize : Int, NMeasurements : Int, MaxEpochs : Int, MaxStalls : Int, StochasticRescaleFactor : Double, ScoringPeriod : Int, VerboseMessage : (String -> Unit));
```



## <a name="named-items"></a>命名项

### <a name="learningrate--double"></a>Learningrate 超出： [Double](xref:microsoft.quantum.lang-ref.double)

在定型步骤中更新模型参数时，重新缩放渐变应使用的学习速率。
### <a name="tolerance--double"></a>容差： [Double](xref:microsoft.quantum.lang-ref.double)

准备作为量程状态的示例时要使用的近似值。
### <a name="minibatchsize--int"></a>MinibatchSize： [Int](xref:microsoft.quantum.lang-ref.int)

每个定型 minibatch 中要使用的样本数。
### <a name="nmeasurements--int"></a>NMeasurements： [Int](xref:microsoft.quantum.lang-ref.int)

测量每个分类结果以便估算分类概率的次数。
### <a name="maxepochs--int"></a>MaxEpochs： [Int](xref:microsoft.quantum.lang-ref.int)

要为每个模型定型的最大时期数。
### <a name="maxstalls--int"></a>MaxStalls： [Int](xref:microsoft.quantum.lang-ref.int)

允许定型 epoch 延迟的最大次数 (在发生故障之前约) 的渐变。
### <a name="stochasticrescalefactor--double"></a>StochasticRescaleFactor： [Double](xref:microsoft.quantum.lang-ref.double)

重试更新前重新缩放已停止的模型的量。
### <a name="scoringperiod--int"></a>ScoringPeriod： [Int](xref:microsoft.quantum.lang-ref.int)

要在计分点之间执行的渐变步骤数。
为获得最佳准确性，请将设置为1。
### <a name="verbosemessage--string---unit"></a>VerboseMessage： [String](xref:microsoft.quantum.lang-ref.string) -> [单元](xref:microsoft.quantum.lang-ref.unit)

可用于提供详细反馈的函数。

## <a name="remarks"></a>备注

不应直接创建此 UDT，而应通过调用 @"microsoft.quantum.machinelearning.defaulttrainingoptions" 并使用 `w/` 运算符重写不同的默认值来指定它。

例如，若要使用100000度量值和最多8个定型时期：

```Q#
let options = DefaultTrainingOptions()
              w/ NMeasurements <- 100000
              w/ MaxEpochs <- 8;
```

## <a name="references"></a>参考

- [arXiv:1804.00633](https://arxiv.org/abs/1804.00633)