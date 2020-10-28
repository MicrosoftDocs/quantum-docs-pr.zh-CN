---
uid: Microsoft.Quantum.MachineLearning._UpdatedBias
title: _UpdatedBias 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: _UpdatedBias
qsharp.summary: Returns a bias value that leads to near-minimum misclassification score.
ms.openlocfilehash: 2704d08e4c1ce868e1fd9065c3cab0285d431094
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696738"
---
# <a name="_updatedbias-function"></a>_UpdatedBias 函数

命名空间： [default-machinelearning-southcentralus](xref:Microsoft.Quantum.MachineLearning)

软件包 [](https://nuget.org/packages/)


返回导致最小错误分类分数的偏差值。

```qsharp
function _UpdatedBias (labeledProbabilities : (Double, Int)[], bias : Double, tolerance : Double) : Double
```


## <a name="input"></a>输入

### <a name="labeledprobabilities--doubleint"></a>labeledProbabilities： ([Double](xref:microsoft.quantum.lang-ref.double)，[Int](xref:microsoft.quantum.lang-ref.int)) []




### <a name="bias--double"></a>偏置： [Double](xref:microsoft.quantum.lang-ref.double)




### <a name="tolerance--double"></a>容差： [Double](xref:microsoft.quantum.lang-ref.double)





## <a name="output--double"></a>输出： [Double](xref:microsoft.quantum.lang-ref.double)

