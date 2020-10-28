---
uid: Microsoft.Quantum.MachineLearning.NMisclassifications
title: NMisclassifications 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NMisclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns the number of indices at which each set of labels differ.
ms.openlocfilehash: 9e356d68233519978e007e5a2999ca1be8cb7f83
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695135"
---
# <a name="nmisclassifications-function"></a>NMisclassifications 函数

命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)

软件包 [](https://nuget.org/packages/)


给定一组推断标签和一组正确标签，返回每组标签不同的索引数。

```qsharp
function NMisclassifications (proposed : Int[], actual : Int[]) : Int
```


## <a name="input"></a>输入

### <a name="proposed--int"></a>已建议： [Int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="actual--int"></a>实际： [Int](xref:microsoft.quantum.lang-ref.int)[]





## <a name="output--int"></a>输出： [Int](xref:microsoft.quantum.lang-ref.int)

索引的数目 `idx` `inferredLabels[idx] != actualLabels[idx]` 。