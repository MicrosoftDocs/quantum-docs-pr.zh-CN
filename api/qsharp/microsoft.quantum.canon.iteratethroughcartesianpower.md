---
uid: Microsoft.Quantum.Canon.IterateThroughCartesianPower
title: IterateThroughCartesianPower 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: IterateThroughCartesianPower
qsharp.summary: Applies an operation for each index in the Cartesian power of an integer range.
ms.openlocfilehash: 3a303d13c4a6f102dab92d814e24df9d90213fbe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840299"
---
# <a name="iteratethroughcartesianpower-operation"></a>IterateThroughCartesianPower 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


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



## <a name="example"></a>示例

给定一个操作 `op` ，以下两个代码段是等效的：

```qsharp
IterateThroughCartesianPower(2, 3, op);
```

```qsharp
op([0, 0]);
op([1, 0]);
op([2, 0]);
op([0, 1]);
// ..
op([2, 2]);
```

## <a name="see-also"></a>另请参阅

- [Canon. IterateThroughCartesianProduct](xref:Microsoft.Quantum.Canon.IterateThroughCartesianProduct)