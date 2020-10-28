---
uid: Microsoft.Quantum.Arrays.IndexRange
title: IndexRange 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 7f9779acd4a781c50388217aa780710bd0b99ff3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696502"
---
# <a name="indexrange-function"></a>IndexRange 函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

软件包 [](https://nuget.org/packages/)


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