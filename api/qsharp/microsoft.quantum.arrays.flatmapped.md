---
uid: Microsoft.Quantum.Arrays.FlatMapped
title: FlatMapped 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: FlatMapped
qsharp.summary: Given an array and a function that maps an array element to some output array, returns the concatenated output arrays for each array element.
ms.openlocfilehash: 3e75c7703471a2986812df660c2f9328f1536d22
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696519"
---
# <a name="flatmapped-function"></a>FlatMapped 函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

软件包 [](https://nuget.org/packages/)


给定一个数组和一个将数组元素映射到某个输出数组的函数，将返回每个数组元素的串联输出数组。

```qsharp
function FlatMapped<'TInput, 'TOutput> (mapper : ('TInput -> 'TOutput[]), array : 'TInput[]) : 'TOutput[]
```


## <a name="input"></a>输入

### <a name="mapper--tinput---toutput"></a>映射器： "> TInput" TOutput []

用于 `'TInput` `'TOutput[]` 映射数组元素的的函数。


### <a name="array--tinput"></a>array： ' TInput []

元素的数组。



## <a name="output--toutput"></a>输出： "TOutput []

数组， `'TOutput[]` 它是由映射函数生成的所有数组的串联。

## <a name="type-parameters"></a>类型参数

### <a name="tinput"></a>'TInput

元素的类型 `array` 。
### <a name="toutput"></a>'TOutput

`mapper`函数返回此类型的数组。