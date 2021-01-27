---
uid: Microsoft.Quantum.MachineLearning.InferredLabels
title: InferredLabels 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabels
qsharp.summary: Given an array of classification probabilities and a bias, returns the label inferred from each probability.
ms.openlocfilehash: 576b4b1f11fc21476bbb019d4b0326981294528c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848394"
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