---
uid: Microsoft.Quantum.Arrays.Count
title: Count 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Count
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: 408a4a42dda6a4827db6d5865e2b4b8a8df5b37a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696544"
---
# <a name="count-function"></a>Count 函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

软件包 [](https://nuget.org/packages/)


给定为数组元素定义的数组和谓词后，将返回一个数组，该数组由满足该谓词的元素组成。

```qsharp
function Count<'T> (predicate : ('T -> Bool), array : 'T[]) : Int
```


## <a name="input"></a>输入

### <a name="predicate--t---bool"></a>谓词：不 >[布尔](xref:microsoft.quantum.lang-ref.bool)值

从 `'T` 到用于筛选元素的布尔值的函数。


### <a name="array--t"></a>array： t []

上的元素的数组 `'T` 。



## <a name="output--int"></a>输出： [Int](xref:microsoft.quantum.lang-ref.int)

中满足谓词的元素的数目 `array` 。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

元素的类型 `array` 。

## <a name="remarks"></a>注解

函数是为泛型类型定义的，也就是说，只要有一个数组 `'T[]` 和一个谓词，就 `'T -> Bool` 可以筛选元素。