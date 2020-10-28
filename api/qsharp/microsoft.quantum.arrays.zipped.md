---
uid: Microsoft.Quantum.Arrays.Zipped
title: Zipped 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped
qsharp.summary: Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 67170fa005675f0e5d788c9c3b350fb9a961a597
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696429"
---
# <a name="zipped-function"></a>Zipped 函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

软件包 [](https://nuget.org/packages/)


给定两个数组，返回一个新的对数组，以便每个对都包含来自每个原始数组的元素。

```qsharp
function Zipped<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
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

- [Microsoft.Quantum.Arrays.Zipped3](xref:Microsoft.Quantum.Arrays.Zipped3)
- [Microsoft.Quantum.Arrays.Zipped4](xref:Microsoft.Quantum.Arrays.Zipped4)
- ["."](xref:Microsoft.Quantum.Arrays.Unzipped)