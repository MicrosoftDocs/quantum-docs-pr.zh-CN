---
uid: Microsoft.Quantum.Canon.TrotterStepSize
title: TrotterStepSize 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterStepSize
qsharp.summary: Computes Trotter step size in recursive implementation of Trotter simulation algorithm.
ms.openlocfilehash: c7b6432645dcad2bd47c62b91e04e0b42cd04ca9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840072"
---
# <a name="trotterstepsize-function"></a>TrotterStepSize 函数

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


计算 Trotter 模拟算法的递归实现中的 Trotter 步长大小。

```qsharp
function TrotterStepSize (order : Int) : Double
```


## <a name="input"></a>输入

### <a name="order--int"></a>顺序： [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--double"></a>输出： [Double](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>备注

此操作使用的索引约定不同于 [quant/0508139](https://arxiv.org/abs/quant-ph/0508139)的索引约定。 特别是，与 `DecomposedIntoTimeStepsCA(_, 4)` quant/0508139 中的标量 $p _2 ( \lambda) $。