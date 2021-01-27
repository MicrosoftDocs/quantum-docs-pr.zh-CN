---
uid: Microsoft.Quantum.Arrays.MappedByIndex
title: MappedByIndex 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedByIndex
qsharp.summary: Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 584cabcb7b6059ae5d311f13f5f75bd1f87bdba5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845665"
---
# <a name="mappedbyindex-function"></a>MappedByIndex 函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

## <a name="example"></a>示例

以下两行是等效的：

```qsharp
let arr = MapIndex(f, [x0, x1, x2]);
```

和

```qsharp
let arr = [f(0, x0), f(1, x1), f(2, x2)];
```

## <a name="see-also"></a>另请参阅

- [已映射的](xref:Microsoft.Quantum.Arrays.Mapped)