---
uid: Microsoft.Quantum.MachineLearning.InferredLabels
title: InferredLabels 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabels
qsharp.summary: Given an array of classification probabilities and a bias, returns the label inferred from each probability.
ms.openlocfilehash: 668ab89ed45c49d33ce50ff5d892f4d57246c12a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196355"
---
# <a name="inferredlabels-function"></a>InferredLabels 函数

命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)

Package： [default-machinelearning-southcentralus](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


给定一组分类概率和一个偏差，返回从每个概率推导出的标签。

```qsharp
function InferredLabels (bias : Double, probabilities : Double[]) : Int[]
```


## <a name="input"></a>输入

### <a name="bias--double"></a>偏置： [Double](xref:microsoft.quantum.lang-ref.double)

两个类之间的偏移，通常是定型分类器的结果。


### <a name="probabilities--double"></a>概率： [Double](xref:microsoft.quantum.lang-ref.double)[]

一组样本的分类概率数组，通常由估计分类频率引起。



## <a name="output--int"></a>输出： [Int](xref:microsoft.quantum.lang-ref.int)[]

从每个分类概率中推断出的标签。