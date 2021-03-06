---
uid: Microsoft.Quantum.MachineLearning.EstimateGradient
title: EstimateGradient 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: EstimateGradient
qsharp.summary: Estimates the training gradient for a sequential classifier at a particular model and for a given encoded input.
ms.openlocfilehash: 38edcb67e7dcc5d2e971fb507a792937774a702c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844386"
---
# <a name="estimategradient-operation"></a>EstimateGradient 操作

命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)

Package： [default-machinelearning-southcentralus](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


估算特定模型和给定编码输入的顺序分类器的定型渐变。

```qsharp
operation EstimateGradient (model : Microsoft.Quantum.MachineLearning.SequentialModel, encodedInput : Microsoft.Quantum.MachineLearning.StateGenerator, nMeasurements : Int) : Double[]
```


## <a name="input"></a>输入

### <a name="model--sequentialmodel"></a>模型： [SequentialModel](xref:Microsoft.Quantum.MachineLearning.SequentialModel)

要估计其渐变的顺序模型。


### <a name="encodedinput--stategenerator"></a>encodedInput： [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)

对顺序分类器的输入，编码为状态准备操作。


### <a name="nmeasurements--int"></a>nMeasurements： [Int](xref:microsoft.quantum.lang-ref.int)

要在估计渐变时使用的度量值的数量。



## <a name="output--double"></a>输出： [Double](xref:microsoft.quantum.lang-ref.double)[]

给定输入和模型参数的定型渐变的估计值。

## <a name="remarks"></a>备注

此操作使用 Hadamard 测试和参数移位技术来估算渐变。