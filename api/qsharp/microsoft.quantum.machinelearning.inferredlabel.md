---
uid: Microsoft.Quantum.MachineLearning.InferredLabel
title: InferredLabel 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabel
qsharp.summary: Given a of classification probability and a bias, returns the label inferred from that probability.
ms.openlocfilehash: b64bb1ec52d2456ee1b627b920890223d173533b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211774"
---
# <a name="inferredlabel-function"></a>InferredLabel 函数

命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)

Package： [default-machinelearning-southcentralus](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


给定一个分类概率和一个偏差，返回从该概率推导出的标签。

```qsharp
function InferredLabel (bias : Double, probability : Double) : Int
```


## <a name="input"></a>输入

### <a name="bias--double"></a>偏置： [Double](xref:microsoft.quantum.lang-ref.double)

两个类之间的偏移，通常是定型分类器的结果。


### <a name="probability--double"></a>概率： [Double](xref:microsoft.quantum.lang-ref.double)

特定示例的分类概率，通常是从估算其分类频率得出的。



## <a name="output--int"></a>输出： [Int](xref:microsoft.quantum.lang-ref.int)

从给定分类概率中推断出的标签。