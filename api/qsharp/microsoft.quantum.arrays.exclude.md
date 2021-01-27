---
uid: Microsoft.Quantum.Arrays.Exclude
title: Exclude 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Exclude
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: 76cdee56e84951c63e80babfdca6a3de33583cab
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848680"
---
# <a name="exclude-function"></a>Exclude 函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


返回一个数组，其中包含另一个数组的元素，而不包括给定索引列表中的元素。

```qsharp
function Exclude<'T> (remove : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a>输入

### <a name="remove--int"></a>删除： [Int](xref:microsoft.quantum.lang-ref.int)[]

指示应从输出中排除哪些元素的索引数组。


### <a name="array--t"></a>array： t []

输出数组中的值采用的数组。



## <a name="output--t"></a>输出： t []

一个数组， `output` 它 `output[0]` 是 `array` 其索引未出现在中的第一个元素 `remove` ，这 `output[1]` 是第二个这样的元素，依此类推。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

数组元素的类型。

## <a name="example"></a>示例

```qsharp
let array = [10, 11, 12, 13, 14, 15];
// The following line returns [10, 12, 15].
let subarray = Exclude([1, 3, 4], array);
```