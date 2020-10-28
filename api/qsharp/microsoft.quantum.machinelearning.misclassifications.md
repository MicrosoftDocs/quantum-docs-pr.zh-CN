---
uid: Microsoft.Quantum.MachineLearning.Misclassifications
title: Misclassifications 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: Misclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns indices for where each set of labels differs.
ms.openlocfilehash: 500c2910f7c5616c88ff6c70ab3cc16680e199fb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700597"
---
# <a name="misclassifications-function"></a>Misclassifications 函数

命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)

软件包 [](https://nuget.org/packages/)


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