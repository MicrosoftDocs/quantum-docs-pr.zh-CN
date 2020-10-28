---
uid: Microsoft.Quantum.Arrays.MappedByIndex
title: MappedByIndex 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedByIndex
qsharp.summary: Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 07ca523248c363f2229551a14e77803dc4f4f82e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696486"
---
# <a name="mappedbyindex-function"></a>MappedByIndex 函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

软件包 [](https://nuget.org/packages/)


给定数组和为数组的索引元素定义的函数后，将返回一个新数组，该数组由函数下的原始数组的图像组成。

```qsharp
function MappedByIndex<'T, 'U> (mapper : ((Int, 'T) -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a>输入

### <a name="mapper--intt---u"></a>映射器： ([Int](xref:microsoft.quantum.lang-ref.int)，不) -> "U

用于 `(Int, 'T)` `'U` 映射元素及其索引的的函数。


### <a name="array--t"></a>array： t []

上的元素的数组 `'T` 。



## <a name="output--u"></a>输出： U []

`'U[]`由函数映射的元素的数组 `mapper` 。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

元素的类型 `array` 。
### <a name="u"></a>' U

函数的结果类型 `mapper` 。

## <a name="see-also"></a>另请参阅

- [已映射的](xref:Microsoft.Quantum.Arrays.Mapped)