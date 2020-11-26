---
uid: Microsoft.Quantum.Arrays.Interleaved
title: 交错函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 1ff5999cc19f47e3dcae601b960446923b613d90
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220954"
---
# <a name="interleaved-function"></a>交错函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


交错的两个 (数组几乎) 相同大小。

```qsharp
function Interleaved<'T> (first : 'T[], second : 'T[]) : 'T[]
```


## <a name="description"></a>描述

此函数返回两个数组的交错，从第一个数组的第一个元素开始，然后从第二个数组的第一个元素开始，依次类推。

第一个数组的长度必须与第二个数组的长度相同，或可以有一个以上的元素。

## <a name="input"></a>输入

### <a name="first--t"></a>第一个： t []

要交错的第一个数组。


### <a name="second--t"></a>second： t []

要交错的第二个数组。



## <a name="output--t"></a>输出： t []

交错数组

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

和的每个元素的 `first` 类型 `second` 。