---
uid: Microsoft.Quantum.Arrays.Subarray
title: 子数组函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Subarray
qsharp.summary: Takes an array and a list of locations and produces a new array formed from the elements of the original array that match the given locations.
ms.openlocfilehash: ccc041da0213d1f5dc5c8b4ff7a03b8b01ad107d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845422"
---
# <a name="subarray-function"></a>子数组函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

## <a name="remarks"></a>备注

函数是为泛型类型定义的，即，只要有一个数组 `'T[]` 和一个定义子数组的位置列表 `Int[]` 。
子数组的构造是基于生成给定数组的新深层副本的，而不是维护引用。

如果为 `Length(indices) < Length(array)` ，则此函数将返回的子集 `array` 。 另一方面，如果 `indices` 包含重复的元素，则 `array` 同样会重复执行的相应元素。
如果 `indices` 和的 `array` 长度相同，则此函数将提供 `array` 。