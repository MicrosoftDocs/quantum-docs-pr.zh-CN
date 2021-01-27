---
uid: Microsoft.Quantum.MachineLearning.InferredLabel
title: InferredLabel 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InferredLabel
qsharp.summary: Given a of classification probability and a bias, returns the label inferred from that probability.
ms.openlocfilehash: 46b24c283a01e6ac1c959ee4a6899591ee708ff7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848421"
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