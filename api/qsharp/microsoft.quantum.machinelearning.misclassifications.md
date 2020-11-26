---
uid: Microsoft.Quantum.MachineLearning.Misclassifications
title: Misclassifications 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Misclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.
ms.openlocfilehash: e13a9b9b65931678d5d87878e81fa172329a28ea
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211672"
---
# <a name="misclassifications-function"></a>Misclassifications 函数

命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)

Package： [default-machinelearning-southcentralus](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


给定一组推断标签和一组正确标签，返回每组标签不同的位置的索引。

```qsharp
function Misclassifications (inferredLabels : Int[], actualLabels : Int[]) : Int[]
```


## <a name="input"></a>输入

### <a name="inferredlabels--int"></a>inferredLabels： [Int](xref:microsoft.quantum.lang-ref.int)[]

为给定定型集或验证集推理出的标签。


### <a name="actuallabels--int"></a>actualLabels： [Int](xref:microsoft.quantum.lang-ref.int)[]

给定定型集或验证集的 true 标签。



## <a name="output--int"></a>输出： [Int](xref:microsoft.quantum.lang-ref.int)[]

索引的数组 `idx` ，例如 `inferredLabels[idx] != actualLabels[idx]` 。