---
uid: Microsoft.Quantum.Arrays.Mapped
title: 映射函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Mapped
qsharp.summary: Given an array and a function that is defined for the elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 00ea0803faf6e8edfa748af63dd6c7e217b1de41
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845678"
---
# <a name="mapped-function"></a>映射函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


给定数组和为数组元素定义的函数后，将返回一个新数组，该数组由函数下的原始数组的图像组成。

```qsharp
function Mapped<'T, 'U> (mapper : ('T -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a>输入

### <a name="mapper--t---u"></a>映射器：不 > "U

用于映射元素的的函数 `'T` `'U` 。


### <a name="array--t"></a>array： t []

上的元素的数组 `'T` 。



## <a name="output--u"></a>输出： U []

`'U[]`由函数映射的元素的数组 `mapper` 。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

元素的类型 `array` 。
### <a name="u"></a>' U

函数的结果类型 `mapper` 。

## <a name="remarks"></a>备注

函数是为泛型类型定义的，也就是说，只要有一个数组 `'T[]` 和一个函数， `mapper: 'T -> 'U` 我们就可以映射数组的元素，并生成一个类型为的新数组 `'U[]` 。