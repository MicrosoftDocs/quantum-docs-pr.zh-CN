---
uid: Microsoft.Quantum.Arrays.Subarray
title: 子数组函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Subarray
qsharp.summary: Takes an array and a list of locations and produces a new array formed from the elements of the original array that match the given locations.
ms.openlocfilehash: be7b6ee1a396d67ebc311d8d97f4bd751a32d171
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696451"
---
# <a name="subarray-function"></a>子数组函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

软件包 [](https://nuget.org/packages/)


采用一个数组和一个位置列表，并生成一个新数组，该数组由与给定位置匹配的原始数组的元素构成。

```qsharp
function Subarray<'T> (indices : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a>输入

### <a name="indices--int"></a>索引： [Int](xref:microsoft.quantum.lang-ref.int)[]

用于定义子数组的整数的列表。


### <a name="array--t"></a>array： t []

上的元素的数组 `'T` 。



## <a name="output--t"></a>输出： t []

`out`元素的数组，这些元素的索引对应于子数组，因此为 `out[idx] == array[indices[idx]]` 。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

元素的类型 `array` 。

## <a name="remarks"></a>注解

函数是为泛型类型定义的，即，只要有一个数组 `'T[]` 和一个定义子数组的位置列表 `Int[]` 。
子数组的构造是基于生成给定数组的新深层副本的，而不是维护引用。

如果为 `Length(indices) < Length(array)` ，则此函数将返回的子集 `array` 。 另一方面，如果 `indices` 包含重复的元素，则 `array` 同样会重复执行的相应元素。
如果 `indices` 和的 `array` 长度相同，则此函数将提供 `array` 。