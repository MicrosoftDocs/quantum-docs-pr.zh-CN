---
uid: Microsoft.Quantum.Arrays.IndexRange
title: IndexRange 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 5afd4cc260ac3e384d2736bf7b43d941afd9ef73
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220937"
---
# <a name="indexrange-function"></a>IndexRange 函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


给定一个数组，返回该数组的索引范围，该范围适用于在 for 循环中使用。

```qsharp
function IndexRange<'TElement> (array : 'TElement[]) : Range
```


## <a name="input"></a>输入

### <a name="array--telement"></a>array： ' TElement []

应为其返回索引范围的数组。



## <a name="output--range"></a>输出： [范围](xref:microsoft.quantum.lang-ref.range)

数组的所有索引范围。

## <a name="type-parameters"></a>类型参数

### <a name="telement"></a>' TElement

数组元素的类型。