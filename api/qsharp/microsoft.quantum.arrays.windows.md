---
uid: Microsoft.Quantum.Arrays.Windows
title: Windows 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Windows
qsharp.summary: Returns all consecutive subarrays of length `size`.
ms.openlocfilehash: adfea2b9a2f6c22446817538d29586284dba723e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842200"
---
# <a name="windows-function"></a>Windows 函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

## <a name="example"></a>示例

```qsharp
// same as [[1, 2, 3], [2, 3, 4], [3, 4, 5]]
let windows = Windows(3, [1, 2, 3, 4, 5]);
```