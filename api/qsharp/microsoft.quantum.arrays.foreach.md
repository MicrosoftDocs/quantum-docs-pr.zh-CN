---
uid: Microsoft.Quantum.Arrays.ForEach
title: ForEach 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ForEach
qsharp.summary: Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.
ms.openlocfilehash: b362d28e77c8dea2b3daeed4a4d605e1dd42e487
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221141"
---
# <a name="foreach-operation"></a>ForEach 操作

命名空间 [：](xref:Microsoft.Quantum.Arrays)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


给定为数组元素定义的数组和操作，返回一个新数组，该数组由该操作下的原始数组的图像组成。

```qsharp
operation ForEach<'T, 'U> (action : ('T => 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a>输入

### <a name="action--t--u"></a>操作：不 => ' U 

从 `'T` 到的操作将 `'U` 应用于每个元素。


### <a name="array--t"></a>array： t []

上的元素的数组 `'T` 。



## <a name="output--u"></a>输出： U []

`'U[]`由操作映射的元素的数组 `action` 。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

元素的类型 `array` 。
### <a name="u"></a>' U

操作的结果类型 `action` 。

## <a name="remarks"></a>备注

操作是为泛型类型定义的，也就是说，只要有一个数组 `'T[]` 和一个操作， `action : 'T -> 'U` 我们就可以映射数组的元素，并生成一个类型为的新数组 `'U[]` 。