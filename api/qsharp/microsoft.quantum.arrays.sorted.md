---
uid: Microsoft.Quantum.Arrays.Sorted
title: 已排序函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Sorted
qsharp.summary: Given an array, returns the elements of that array sorted by a given comparison function.
ms.openlocfilehash: bd8b869e03c7f4687c456a944e07a811ae0d2ce2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220223"
---
# <a name="sorted-function"></a>已排序函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


给定一个数组，返回该数组的元素，这些元素按给定的比较函数排序。

```qsharp
function Sorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a>输入

### <a name="comparison--tt---bool"></a>比较： ( 不) -> [Bool](xref:microsoft.quantum.lang-ref.bool)

比较两个元素的函数，如果为，则将 `a` 其视为小于或等于 `b` `comparison(a, b)` `true` 。


### <a name="array--t"></a>array： t []

要排序的数组。



## <a name="output--t"></a>输出： t []



## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

的每个元素的类型 `array` 。

## <a name="remarks"></a>备注

假定函数是 `comparison` 可传递的，因此，如果 `comparison(a, b)` 和，则 `comparison(b, c)` `comparison(a, c)` 假定为。 如果此属性不存在，则此函数的输出可能不正确。

由于这是一个函数，即使两个元素在下被视为相等，结果也完全是确定性的 `comparison` ; 即，当 `comparison(a, b)` 和 `comparison(b, a)` 都是时 `true` 。
具体而言，此函数执行的排序保证是稳定的，因此，如果中的两个 `a` 元素 `b` 在中按顺序发生 `array` ，并被视为相等 `comparison` ，则在 `a` 输出中也将出现 `b` 在之前。

例如：

```Q#
function LastDigitLessThanOrEqual(left : Int, right : Int) : Bool {
    return LessThanOrEqualI(
        left % 10, right % 10
    );
}

function SortedByLastDigit() : Int[] {
    return Sorted(LastDigitLessThanOrEqual, [3, 37, 11, 17]);
}
// returns [11, 3, 37, 17].
```