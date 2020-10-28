---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianPower
title: IterateThroughCartesianPower 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianPower
qsharp.summary: Applies an operation for each index in the Cartesian power of an integer range.
ms.openlocfilehash: 526d28cbf3cd356b4f48eec02b3f032f70a868d9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696033"
---
# <a name="iteratethroughcartesianpower-operation"></a>IterateThroughCartesianPower 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


以整数范围的笛卡尔幂对每个索引应用操作。

```qsharp
operation IterateThroughCartesianPower (power : Int, bound : Int, op : (Int[] => Unit)) : Unit
```


## <a name="description"></a>说明

以迭代方式为范围的笛卡尔幂的每个元素应用操作 `0..(bound - 1)` 。

## <a name="input"></a>输入

### <a name="power--int"></a>幂： [Int](xref:microsoft.quantum.lang-ref.int)

应为范围增加的笛卡尔幂 `0..(bound - 1)` 。


### <a name="bound--int"></a>绑定： [Int](xref:microsoft.quantum.lang-ref.int)

要循环访问的范围的规范，给定为范围的长度。


### <a name="op--int--unit"></a>op： [Int](xref:microsoft.quantum.lang-ref.int)[] => [单元](xref:microsoft.quantum.lang-ref.unit) 

为给定笛卡尔幂的每个元素调用的操作。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>另请参阅

- [Canon. IterateThroughCartesianProduct](xref:Microsoft.Quantum.Canon.IterateThroughCartesianProduct)