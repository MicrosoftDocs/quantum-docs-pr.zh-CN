---
uid: Microsoft.Quantum.MachineLearning.NMisclassifications
title: NMisclassifications 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NMisclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns the number of indices at which each set of labels differ.
ms.openlocfilehash: adc7042d6108c7ec72d13340633824d3eaf5e18e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853906"
---
# <a name="nmisclassifications-function"></a>NMisclassifications 函数

命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)

Package： [default-machinelearning-southcentralus](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


给定一组推断标签和一组正确标签，返回每组标签不同的索引数。

```qsharp
function NMisclassifications (proposed : Int[], actual : Int[]) : Int
```


## <a name="input"></a>输入

### <a name="proposed--int"></a>已建议： [Int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="actual--int"></a>实际： [Int](xref:microsoft.quantum.lang-ref.int)[]





## <a name="output--int"></a>输出： [Int](xref:microsoft.quantum.lang-ref.int)

索引的数目 `idx` `inferredLabels[idx] != actualLabels[idx]` 。

## <a name="example"></a>示例

```qsharp
let nMisclassifications = NMisclassifications([1, 1, 0, 0], [0, 1, 1, 0]);
Message($"{nMisclassifications}"); // Will print 2.
```