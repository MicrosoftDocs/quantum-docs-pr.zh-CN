---
uid: Microsoft.Quantum.Arrays.IndexRange
title: IndexRange 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 043b56a1ac3cbe5cd59cdd45d3725f301d81a6ee
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845782"
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

## <a name="example"></a>示例

以下 `for` 循环是等效的：

```qsharp
for (idx in IndexRange(array)) { ... }
for (idx in IndexRange(array)) { ... }
```