---
uid: Microsoft.Quantum.Arrays.Zip4
title: Zip4 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip4
qsharp.summary: >-
  > [!WARNING]

  > Zip4 has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped4> instead.


  Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.
ms.openlocfilehash: 534721e6544a31f6f5d27db0c077e9d8c574aecd
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850884"
---
# <a name="zip4-function"></a>Zip4 函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


> [!WARNING]
> Zip4 已被弃用。 请改用 <xref:Microsoft.Quantum.Arrays.Zipped4>。

给定四个数组，返回一个4元组的新数组，使每个4元组包含每个原始数组中的一个元素。

```qsharp
function Zip4<'T1, 'T2, 'T3, 'T4> (first : 'T1[], second : 'T2[], third : 'T3[], fourth : 'T4[]) : ('T1, 'T2, 'T3, 'T4)[]
```


## <a name="input"></a>输入

### <a name="first--t1"></a>第一个：不是 1 []

一个数组，其中包含每个元组的第一个元素的值。


### <a name="second--t2"></a>second：不 2 []

一个数组，其中包含每个元组的第二个元素的值。


### <a name="third--t3"></a>第三个：不 3 []

一个数组，其中包含每个元组的第三个元素的值。


### <a name="fourth--t4"></a>第四个：不 4 []

一个数组，其中包含每个元组的第四个元素的值。



## <a name="output--t1t2t3t4"></a>输出： ( 不是1，不是2，不是3，不) []

一个数组，其中包含每个的窗体的4元组 `(first[idx], second[idx], third[idx], fourth[idx])` `idx` 。 如果四个数组的长度不相等，则输出将与输入的较短内容相同。

## <a name="type-parameters"></a>类型参数

### <a name="t1"></a>T 1

第一个数组元素的类型。
### <a name="t2"></a>不是2

第二个数组元素的类型。
### <a name="t3"></a>不3

第三个数组元素的类型。
### <a name="t4"></a>不4

第四个数组元素的类型。

## <a name="see-also"></a>另请参阅

- [Microsoft.Quantum.Arrays.Zip](xref:Microsoft.Quantum.Arrays.Zip)
- [Microsoft.Quantum.Arrays.Zip3](xref:Microsoft.Quantum.Arrays.Zip3)