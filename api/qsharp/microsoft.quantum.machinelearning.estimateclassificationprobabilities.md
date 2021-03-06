---
uid: Microsoft.Quantum.MachineLearning.EstimateClassificationProbabilities
title: EstimateClassificationProbabilities 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateClassificationProbabilities
qsharp.summary: Given a set of samples and a sequential classifier, estimates the classification probability for those samples by repeatedly measuring the output of the classifier on each sample.
ms.openlocfilehash: eea503d042d6ffc241186c117a7c02ee72983b09
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847724"
---
# <a name="estimateclassificationprobabilities-operation"></a>EstimateClassificationProbabilities 操作

命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)

Package： [default-machinelearning-southcentralus](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


给定一组示例和顺序分类器，通过反复测量每个样本上分类器的输出来估算这些样本的分类概率。

```qsharp
operation EstimateClassificationProbabilities (tolerance : Double, model : Microsoft.Quantum.MachineLearning.SequentialModel, samples : Double[][], nMeasurements : Int) : Double[]
```


## <a name="input"></a>输入

### <a name="tolerance--double"></a>容差： [Double](xref:microsoft.quantum.lang-ref.double)

在将示例编码为状态准备操作时允许的容差。


### <a name="model--sequentialmodel"></a>模型： [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

用于估算给定样本的分类概率的顺序模型。


### <a name="samples--double"></a>示例： [Double](xref:microsoft.quantum.lang-ref.double)[] []

要分类的每个样本的特性向量数组。


### <a name="nmeasurements--int"></a>nMeasurements： [Int](xref:microsoft.quantum.lang-ref.int)

要在估计分类概率时使用的度量值的数量。



## <a name="output--double"></a>输出： [Double](xref:microsoft.quantum.lang-ref.double)[]

计算每个给定样本的分类概率的数组。