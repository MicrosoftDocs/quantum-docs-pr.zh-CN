---
uid: Microsoft.Quantum.Arrays.Zip
title: Zip 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip
qsharp.summary: >-
  > [!WARNING]

  > Zip has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped> instead.


  Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 8ed658003f749efd31b8d841cecbb0a23a471af5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850904"
---
# <a name="zip-function"></a>Zip 函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


> [!WARNING]
> Zip 已弃用。 请改用 <xref:Microsoft.Quantum.Arrays.Zipped>。

给定两个数组，返回一个新的对数组，以便每个对都包含来自每个原始数组的元素。

```qsharp
function Zip<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a>输入

### <a name="left--t"></a>left： t []

一个数组，其中包含每个元组的第一个元素的值。


### <a name="right--u"></a>right： ' U []

一个数组，其中包含每个元组的第二个元素的值。



## <a name="output--tu"></a>Output： ( ' U) []

一个数组，其中包含每个的形式对 `(left[idx], right[idx])` `idx` 。 如果两个数组的长度不相等，则输出将与输入的较短内容相同。

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

左侧数组元素的类型。
### <a name="u"></a>' U

右侧数组元素的类型。

## <a name="example"></a>示例

```qsharp
let left = [1, 3, 71];
let right = [false, true];
let pairs = Zip(left, right); // [(1, false), (3, true)]
```

## <a name="see-also"></a>另请参阅

- [Microsoft.Quantum.Arrays.Zip3](xref:Microsoft.Quantum.Arrays.Zip3)
- [Microsoft.Quantum.Arrays.Zip4](xref:Microsoft.Quantum.Arrays.Zip4)
- ["."](xref:Microsoft.Quantum.Arrays.Unzipped)