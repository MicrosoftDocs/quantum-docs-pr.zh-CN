---
uid: Microsoft.Quantum.Arrays.IsSorted
title: IsSorted 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsSorted
qsharp.summary: Given an array, returns whether that array is sorted as defined by a given comparison function.
ms.openlocfilehash: b2c5f11c0d92ddf9214de2d439c175319c569be0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220824"
---
# <a name="issorted-function"></a>IsSorted 函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


给定数组，返回数组是否按给定比较函数的定义进行排序。

```qsharp
function IsSorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a>输入

### <a name="comparison--tt---bool"></a>比较： ( 不) -> [Bool](xref:microsoft.quantum.lang-ref.bool)

比较两个元素的函数，如果为，则将 `a` 其视为小于或等于 `b` `comparison(a, b)` `true` 。


### <a name="array--t"></a>array： t []

要检查的数组。



## <a name="output--bool"></a>输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值

`true` 当且仅当对于每对元素 `a` 和 `b` 按顺序发生时 `array` ， `comparison(a, b)` 为 `true` 。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

的每个元素的类型 `array` 。

## <a name="remarks"></a>备注

假定函数是 `comparison` 可传递的，因此，如果 `comparison(a, b)` 和，则 `comparison(b, c)` `comparison(a, c)` 假定为。 如果此属性不存在，则此函数的输出可能不正确。