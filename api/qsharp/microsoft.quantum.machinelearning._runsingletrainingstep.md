---
uid: Microsoft.Quantum.MachineLearning._RunSingleTrainingStep
title: _RunSingleTrainingStep 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: _RunSingleTrainingStep
qsharp.summary: attempts a single parameter update in the direction of mini batch gradient
ms.openlocfilehash: c40bf6f1ceecef2cb196846b4f5a1c49023f1f74
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696748"
---
# <a name="_runsingletrainingstep-operation"></a>_RunSingleTrainingStep 操作

命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)

软件包 [](https://nuget.org/packages/)


尝试在小型批处理渐变方向上进行单个参数更新

```qsharp
operation _RunSingleTrainingStep (miniBatch : (Microsoft.Quantum.MachineLearning.LabeledSample, Microsoft.Quantum.MachineLearning.StateGenerator)[], options : Microsoft.Quantum.MachineLearning.TrainingOptions, model : Microsoft.Quantum.MachineLearning.SequentialModel) : (Double, Microsoft.Quantum.MachineLearning.SequentialModel)
```


## <a name="input"></a>输入

### <a name="minibatch--labeledsamplestategenerator"></a>miniBatch： ([LabeledSample](xref:Microsoft.Quantum.MachineLearning.LabeledSample)，[StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)) []

小型批处理中带标记的示例的容器


### <a name="options--trainingoptions"></a>选项： [TrainingOptions](xref:Microsoft.Quantum.MachineLearning.TrainingOptions)




### <a name="model--sequentialmodel"></a>模型： [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)





## <a name="output--doublesequentialmodel"></a>输出： ([Double](xref:microsoft.quantum.lang-ref.double)、[SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)) 

 (实用工具， (new) 参数) 对