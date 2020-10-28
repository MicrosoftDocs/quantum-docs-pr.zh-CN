---
uid: Microsoft.Quantum.Arrays.MappedOverRange
title: MappedOverRange 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedOverRange
qsharp.summary: Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.
ms.openlocfilehash: e527a3ca1fd7571836f4f79bb453581f53d1db2b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696484"
---
# <a name="mappedoverrange-function"></a>MappedOverRange 函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

软件包 [](https://nuget.org/packages/)


给定一个范围和一个采用整数作为输入的函数时，将返回一个新数组，该数组由函数下的范围值的图像组成。

```qsharp
function MappedOverRange<'T> (mapper : (Int -> 'T), range : Range) : 'T[]
```


## <a name="input"></a>输入

### <a name="mapper--int---t"></a>映射器： [Int](xref:microsoft.quantum.lang-ref.int) ->

用于 `Int` `'T` 映射范围值的的函数。


### <a name="range--range"></a>范围： [范围](xref:microsoft.quantum.lang-ref.range)

整数的范围。



## <a name="output--t"></a>输出： t []

`'T[]`由函数映射的元素的数组 `mapper` 。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

函数的结果类型 `mapper` 。

## <a name="remarks"></a>注解

函数是为泛型类型定义的，也就是说，只要有一个函数， `mapper: Int -> 'T` 我们就可以映射范围的值并生成类型为的数组 `'T[]` 。

## <a name="see-also"></a>另请参阅

- [已映射的](xref:Microsoft.Quantum.Arrays.Mapped)