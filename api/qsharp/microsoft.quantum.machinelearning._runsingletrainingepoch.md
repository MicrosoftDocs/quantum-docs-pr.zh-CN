---
uid: Microsoft.Quantum.MachineLearning._RunSingleTrainingEpoch
title: _RunSingleTrainingEpoch 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: _RunSingleTrainingEpoch
qsharp.summary: Perform one epoch of sequential classifier training on a subset of data samples.
ms.openlocfilehash: 2b4f629eac0bd8e60bd4d86077521c60085d4809
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696749"
---
# <a name="_runsingletrainingepoch-operation"></a>_RunSingleTrainingEpoch 操作

命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)

软件包 [](https://nuget.org/packages/)


在部分数据示例中执行顺序分类器培训的一个时期。

```qsharp
operation _RunSingleTrainingEpoch (encodedSamples : (Microsoft.Quantum.MachineLearning.LabeledSample, Microsoft.Quantum.MachineLearning.StateGenerator)[], schedule : Microsoft.Quantum.MachineLearning.SamplingSchedule, periodScore : Int, options : Microsoft.Quantum.MachineLearning.TrainingOptions, model : Microsoft.Quantum.MachineLearning.SequentialModel, nPreviousBestMisses : Int) : (Int, Microsoft.Quantum.MachineLearning.SequentialModel)
```


## <a name="input"></a>输入

### <a name="encodedsamples--labeledsamplestategenerator"></a>encodedSamples： ([LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)，[StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)) []




### <a name="schedule--samplingschedule"></a>计划： [SamplingSchedule](xref:Microsoft.Quantum.MachineLearning.SamplingSchedule)




### <a name="periodscore--int"></a>periodScore： [Int](xref:microsoft.quantum.lang-ref.int)

要在计分点之间执行的渐变步骤数。
为获得最佳准确性，请将设置为1。


### <a name="options--trainingoptions"></a>选项： [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)

要在定型中使用的选项。


### <a name="model--sequentialmodel"></a>模型： [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

要定型的顺序模型。


### <a name="npreviousbestmisses--int"></a>nPreviousBestMisses： [Int](xref:microsoft.quantum.lang-ref.int)

在以前的时期中观察到的 misclassifications 的最佳数量。



## <a name="output--intsequentialmodel"></a>Output： ([Int](xref:microsoft.quantum.lang-ref.int)，[SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)) 

- 观察到的 misclassifications 的最小数目。
- 找到新的最佳顺序模型。