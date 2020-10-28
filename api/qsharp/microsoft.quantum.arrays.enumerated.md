---
uid: Microsoft.Quantum.Arrays.Enumerated
title: 枚举函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: 0a591025a4eef79e08b47527c0bdb556f5645334
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696528"
---
# <a name="enumerated-function"></a>枚举函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

软件包 [](https://nuget.org/packages/)


给定一个数组，返回一个新数组，其中包含原始数组的元素以及每个元素的索引。

```qsharp
function Enumerated<'TElement> (array : 'TElement[]) : (Int, 'TElement)[]
```


## <a name="input"></a>输入

### <a name="array--telement"></a>array： ' TElement []

要枚举其元素的数组。



## <a name="output--inttelement"></a>Output： ([Int](xref:microsoft.quantum.lang-ref.int)，' TElement) []

一个新数组，其中包含原始数组的元素及其索引。

## <a name="type-parameters"></a>类型参数

### <a name="telement"></a>' TElement

数组元素的类型。