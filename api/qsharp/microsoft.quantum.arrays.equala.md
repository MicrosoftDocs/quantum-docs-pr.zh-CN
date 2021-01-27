---
uid: Microsoft.Quantum.Arrays.EqualA
title: EqualA 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EqualA
qsharp.summary: Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.
ms.openlocfilehash: fe22e208f67d2c289b0b2d99f19ff26fc5abc3d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848686"
---
# <a name="equala-function"></a>EqualA 函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


给定两个相同类型的数组和为数组元素对定义的谓词，检查数组是否相等。

```qsharp
function EqualA<'T> (equal : (('T, 'T) -> Bool), array1 : 'T[], array2 : 'T[]) : Bool
```


## <a name="input"></a>输入

### <a name="equal--tt---bool"></a>等于： ( 不，不) ->[布尔](xref:microsoft.quantum.lang-ref.bool)值

元组中的一个函数， `('T, 'T)` `Bool` 用于检查两个数组元素是否相等。


### <a name="array1--t"></a>array1： t []

要比较的第一个数组。


### <a name="array2--t"></a>array2： t []

要比较的第二个数组。



## <a name="output--bool"></a>输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值

`true`当且仅当和相等时，值为 `array1` `array2` 。
也就是说，如果两个数组具有相同的长度，并且所有元素都与定义的相等 `equal` 。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

每个数组元素的类型。

## <a name="example"></a>示例

下面的代码检查不同的数组对是否相等：

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function EqualADemo() : Unit {
    let equalArrays = EqualA(EqualI, [2, 3, 4], [2, 3, 4]);
    let differentLength = EqualA(EqualD, [2.0, 3.0, 4.0], [2.0, 3.0]);
    let differentElements = EqualA(EqualR, [One, Zero], [One, One]);
    Message($"Equal arrays are {equalArrays ? "equal" | "not equal"}");
    Message($"Arrays of different length are {differentLength ? "equal" | "not equal"}");
    Message($"Arrays of the same length with different elements are {differentElements ? "equal" | "not equal"}");
}
```

## <a name="remarks"></a>备注

此函数是为泛型类型定义的;也就是说，每当有两个数组 `'T[]` 和一个函数时 `equal: ('T, 'T) -> Bool` ，此函数将返回一个 `Bool` 值，该值指示数组是否相等。
对于两个要视为相等的数组，它们必须具有相等的长度，并且数组中同一位置的元素必须相等。