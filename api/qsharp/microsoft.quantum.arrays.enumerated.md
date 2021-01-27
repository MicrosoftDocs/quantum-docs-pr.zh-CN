---
uid: Microsoft.Quantum.Arrays.Enumerated
title: 枚举函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: adb13d8b25c9e4a6011ade119ffa3cb2783f60e2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848126"
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

## <a name="example"></a>示例

以下 `for` 循环是等效的：

```qsharp
for (idx in IndexRange(array)) {
    let element = array[idx];
    ...
}
for ((idx, element) in Enumerated(array)) { ... }
```