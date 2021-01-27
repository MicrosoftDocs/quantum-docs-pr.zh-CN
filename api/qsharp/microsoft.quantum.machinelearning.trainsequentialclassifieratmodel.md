---
uid: Microsoft.Quantum.MachineLearning.TrainSequentialClassifierAtModel
title: TrainSequentialClassifierAtModel 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: TrainSequentialClassifierAtModel
qsharp.summary: Given the structure of a sequential classifier, trains the classifier on a given labeled training set, starting from a particular model.
ms.openlocfilehash: 4164c190cb19b6d3ea74d9803a77d2b19607279b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857155"
---
# <a name="trainsequentialclassifieratmodel-operation"></a>TrainSequentialClassifierAtModel 操作

命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)

Package： [default-machinelearning-southcentralus](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


给定顺序分类器的结构，从特定模型开始训练给定标签定型集上的分类器。

```qsharp
operation TrainSequentialClassifierAtModel (model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Microsoft.Quantum.MachineLearning.LabeledSample[], options : Microsoft.Quantum.MachineLearning.TrainingOptions, trainingSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, validationSchedule : Microsoft.Quantum.MachineLearning.SamplingSchedule) : (Microsoft.Quantum.MachineLearning.SequentialModel, Int)
```


## <a name="input"></a>输入

### <a name="model--sequentialmodel"></a>模型： [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

要用作定型起点的顺序模型。


### <a name="samples--labeledsample"></a>示例： [LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)[]

一组用于执行定型的标记定型数据。


### <a name="options--trainingoptions"></a>选项： [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)

训练时要使用的配置; @"microsoft.quantum.machinelearning.trainingoptions" @"microsoft.quantum.machinelearning.defaulttrainingoptions" 有关更多详细信息，请参阅和。


### <a name="trainingschedule--samplingschedule"></a>trainingSchedule： [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)

在定型步骤中从定型数据中选择样本时要使用的采样计划。


### <a name="validationschedule--samplingschedule"></a>validationSchedule： [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)

当选择从定型数据中选择样本时，如果选择哪个起点导致最佳分类器分数，则使用采样计划。



## <a name="output--sequentialmodelint"></a>输出： ([SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)，[Int](xref:microsoft.quantum.lang-ref.int)) 

- 给定分类器的参数化和两个类之间的偏移，同时对应于每个给定起点的最佳结果。
- 在最佳分类器模型中观测到的未命中次数。

## <a name="see-also"></a>另请参阅

- [Default-machinelearning-southcentralus. TrainSequentialClassifier](xref:Microsoft.Quantum.MachineLearning.TrainSequentialClassifier)
- [Default-machinelearning-southcentralus. ValidateSequentialClassifier](xref:Microsoft.Quantum.MachineLearning.ValidateSequentialClassifier)