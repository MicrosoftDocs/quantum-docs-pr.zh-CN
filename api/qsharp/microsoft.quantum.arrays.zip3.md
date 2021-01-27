---
uid: Microsoft.Quantum.Arrays.Zip3
title: List.zip3 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip3
qsharp.summary: >-
  > [!WARNING]

  > Zip3 has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.


  Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.
ms.openlocfilehash: b41b0789cdf90db534ee7a50ff25eb3a931ec683
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845351"
---
# <a name="zip3-function"></a>List.zip3 函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


> [!WARNING]
> List.zip3 已被弃用。 请改用 <xref:Microsoft.Quantum.Arrays.Zipped3>。

给定三个数组，返回一个新数组，其中包含3个元组，以便每个第三个元组包含每个原始数组中的一个元素。

```qsharp
function Zip3<'T1, 'T2, 'T3> (first : 'T1[], second : 'T2[], third : 'T3[]) : ('T1, 'T2, 'T3)[]
```


## <a name="input"></a>输入

### <a name="first--t1"></a>第一个：不是 1 []

一个数组，其中包含每个元组的第一个元素的值。


### <a name="second--t2"></a>second：不 2 []

一个数组，其中包含每个元组的第二个元素的值。


### <a name="third--t3"></a>第三个：不 3 []

一个数组，其中包含每个元组的第三个元素的值。



## <a name="output--t1t2t3"></a>输出： ( 不是1，不是2，不是 3) []

一个数组，其中包含每个的窗体的3元组 `(first[idx], second[idx], third[idx])` `idx` 。 如果三个数组的长度不相等，则输出将与输入的较短内容相同。

## <a name="type-parameters"></a>类型参数

### <a name="t1"></a>T 1

第一个数组元素的类型。
### <a name="t2"></a>不是2

第二个数组元素的类型。
### <a name="t3"></a>不3

第三个数组元素的类型。

## <a name="see-also"></a>另请参阅

- [Microsoft.Quantum.Arrays.Zip](xref:Microsoft.Quantum.Arrays.Zip)
- [Microsoft.Quantum.Arrays.Zip4](xref:Microsoft.Quantum.Arrays.Zip4)