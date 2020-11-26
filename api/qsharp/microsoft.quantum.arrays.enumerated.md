---
uid: Microsoft.Quantum.Arrays.Enumerated
title: 枚举函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: 94e8fdb7288bc43ed84d10a3292819b455a2be31
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221413"
---
# <a name="enumerated-function"></a>枚举函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


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