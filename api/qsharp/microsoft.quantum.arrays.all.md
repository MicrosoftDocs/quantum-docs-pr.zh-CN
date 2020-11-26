---
uid: Microsoft.Quantum.Arrays.All
title: All 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: All
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.
ms.openlocfilehash: a7c83e38c3c101b712215eb664486fe29863a52b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221685"
---
# <a name="all-function"></a>All 函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


给定为数组元素定义的数组和谓词，并检查数组的所有元素是否都满足该谓词。

```qsharp
function All<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a>输入

### <a name="predicate--t---bool"></a>谓词：不 >[布尔](xref:microsoft.quantum.lang-ref.bool)值

用于 `'T` `Bool` 检查元素的的函数。


### <a name="array--t"></a>array： t []

上的元素的数组 `'T` 。



## <a name="output--bool"></a>输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值

`Bool`应用于所有元素的谓词的和函数的值。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

元素的类型 `array` 。

## <a name="remarks"></a>备注

函数是为泛型类型定义的，也就是说，只要有一个数组 `'T[]` 和一个函数， `predicate: 'T -> Bool` 我们就可以生成一个 `Bool` 值，该值指示所有元素是否满足 `predicate` 。