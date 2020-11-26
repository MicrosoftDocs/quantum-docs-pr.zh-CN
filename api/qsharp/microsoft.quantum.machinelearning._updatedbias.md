---
uid: Microsoft.Quantum.MachineLearning._UpdatedBias
title: _UpdatedBias 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: _UpdatedBias
qsharp.summary: Returns a bias value that leads to near-minimum misclassification score.
ms.openlocfilehash: 141edf6e425a060a995bfc181aefb1bcffdb128b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196695"
---
# <a name="_updatedbias-function"></a>_UpdatedBias 函数

命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)

Package： [default-machinelearning-southcentralus](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)


返回导致最小错误分类分数的偏差值。

```qsharp
function _UpdatedBias (labeledProbabilities : (Double, Int)[], bias : Double, tolerance : Double) : Double
```


## <a name="input"></a>输入

### <a name="labeledprobabilities--doubleint"></a>labeledProbabilities： ([Double](xref:microsoft.quantum.lang-ref.double)，[Int](xref:microsoft.quantum.lang-ref.int)) []




### <a name="bias--double"></a>偏置： [Double](xref:microsoft.quantum.lang-ref.double)




### <a name="tolerance--double"></a>容差： [Double](xref:microsoft.quantum.lang-ref.double)





## <a name="output--double"></a>输出： [Double](xref:microsoft.quantum.lang-ref.double)

