---
uid: Microsoft.Quantum.Diagnostics._iterateThroughCartesianPower
title: _iterateThroughCartesianPower 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _iterateThroughCartesianPower
qsharp.summary: Iterates a variable through a Cartesian product [ 0, bounds[0]-1 ] × [ 0, bounds[1]-1 ] × [ 0, bounds[Length(bounds)-1]-1 ] and calls op(arr) for every element of the Cartesian product
ms.openlocfilehash: a27302be75ee701b0629310700b56d222aaef7db
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853566"
---
# <a name="_iteratethroughcartesianpower-operation"></a>_iterateThroughCartesianPower 操作

命名空间 [：](xref:Microsoft.Quantum.Diagnostics)

包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


通过笛卡尔积 [0，界限 [0]-1] × [0，界限 [1]-1] × [0，界限 [Length (界限) -1]-1] 来循环访问变量，并为笛卡尔积的每个元素调用 op (arr) 

```qsharp
operation _iterateThroughCartesianPower (length : Int, value : Int, op : (Int[] => Unit)) : Unit
```


## <a name="input"></a>输入

### <a name="length--int"></a>长度： [Int](xref:microsoft.quantum.lang-ref.int)




### <a name="value--int"></a>值： [Int](xref:microsoft.quantum.lang-ref.int)




### <a name="op--int--unit"></a>op： [Int](xref:microsoft.quantum.lang-ref.int)[] => [单元](xref:microsoft.quantum.lang-ref.unit) 





## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)

