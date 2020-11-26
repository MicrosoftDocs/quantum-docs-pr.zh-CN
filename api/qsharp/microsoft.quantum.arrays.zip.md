---
uid: Microsoft.Quantum.Arrays.Zip
title: Zip 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip
qsharp.summary: >-
  > [!WARNING]

  > Zip has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped> instead.


  Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 44db8d38d96babd16ead5ae6dde91da23bdee2c9
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219849"
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

## <a name="see-also"></a>另请参阅

- [Microsoft.Quantum.Arrays.Zip3](xref:Microsoft.Quantum.Arrays.Zip3)
- [Microsoft.Quantum.Arrays.Zip4](xref:Microsoft.Quantum.Arrays.Zip4)
- ["."](xref:Microsoft.Quantum.Arrays.Unzipped)