---
uid: Microsoft.Quantum.Arrays.EqualA
title: EqualA 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EqualA
qsharp.summary: Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.
ms.openlocfilehash: 24fd76aaeb66081d6d8f1eaa3056117f54b5a5e7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696525"
---
# <a name="equala-function"></a>EqualA 函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

软件包 [](https://nuget.org/packages/)


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

## <a name="remarks"></a>注解

此函数是为泛型类型定义的;也就是说，每当有两个数组 `'T[]` 和一个函数时 `equal: ('T, 'T) -> Bool` ，此函数将返回一个 `Bool` 值，该值指示数组是否相等。
对于两个要视为相等的数组，它们必须具有相等的长度，并且数组中同一位置的元素必须相等。