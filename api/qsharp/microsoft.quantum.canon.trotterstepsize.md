---
uid: Microsoft.Quantum.Canon.TrotterStepSize
title: TrotterStepSize 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: TrotterStepSize
qsharp.summary: Computes Trotter step size in recursive implementation of Trotter simulation algorithm.
ms.openlocfilehash: fabfbff74572b3c96c701de5443e4265a0468d78
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695919"
---
# <a name="trotterstepsize-function"></a>TrotterStepSize 函数

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


计算 Trotter 模拟算法的递归实现中的 Trotter 步长大小。

```qsharp
function TrotterStepSize (order : Int) : Double
```


## <a name="input"></a>输入

### <a name="order--int"></a>顺序： [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--double"></a>输出： [Double](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>注解

此操作使用的索引约定不同于 [quant/0508139](https://arxiv.org/abs/quant-ph/0508139)的索引约定。 特别是，与 `DecomposedIntoTimeStepsCA(_, 4)` quant/0508139 中的标量 $p _2 ( \lambda) $。