---
uid: Microsoft.Quantum.Arrays.FlatMapped
title: FlatMapped 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: FlatMapped
qsharp.summary: Given an array and a function that maps an array element to some output array, returns the concatenated output arrays for each array element.
ms.openlocfilehash: bee7002c5a1e80cee7907ff9cb4ebaaedf8e9923
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848643"
---
# <a name="flatmapped-function"></a>FlatMapped 函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

## <a name="example"></a>示例

```qsharp
let Numbers = SequenceI(1, _); // generates numbers starting from 1
let values = FlatMapped(Numbers, [1, 2, 3]);
// values = [1, 1, 2, 1, 2, 3]
```