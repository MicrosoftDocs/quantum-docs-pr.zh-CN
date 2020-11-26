---
uid: Microsoft.Quantum.Arrays.Excluding
title: 排除函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Excluding
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: 6585e619834a96953c9eae2d36a8ebe0a11dbda0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221311"
---
# <a name="excluding-function"></a>排除函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


返回一个数组，其中包含另一个数组的元素，而不包括给定索引列表中的元素。

```qsharp
function Excluding<'T> (remove : Int[], array : 'T[]) : 'T[]
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