---
uid: Microsoft.Quantum.Arrays.Windows
title: Windows 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Windows
qsharp.summary: Returns all consecutive subarrays of length `size`.
ms.openlocfilehash: 6071d1c3e5981855c57abd0e741b1de0201c30a3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696435"
---
# <a name="windows-function"></a>Windows 函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

软件包 [](https://nuget.org/packages/)


返回子的所有连续的 `size` 。

```qsharp
function Windows<'T> (size : Int, array : 'T[]) : 'T[][]
```


## <a name="description"></a>说明

此函数 `n - size + 1` 按顺序返回所有长度的子 `size` ，其中 `n` 是的长度 `arr` 。
第一个子 `arr[0..size - 1], arr[1..size], arr[2..size + 1]` 一直为最后一个子数组 `arr[n - size..n - 1]` 。

如果为 `size <= 0` 或 `size > n` ，则返回空数组。

## <a name="input"></a>输入

### <a name="size--int"></a>大小： [Int](xref:microsoft.quantum.lang-ref.int)

子的长度。


### <a name="array--t"></a>array： t []

元素的数组。



## <a name="output--t"></a>输出： t [] []



## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

元素的类型 `array` 。