---
uid: Microsoft.Quantum.Arrays.ElementAt
title: .Value.elementat 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ElementAt
qsharp.summary: Returns the at the given index of an array.
ms.openlocfilehash: 2d31c62a4a5ba3b273e7440b5dfe4482b47e3a8b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842806"
---
# <a name="elementat-function"></a>.Value.elementat 函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


返回数组中给定索引处的。

```qsharp
function ElementAt<'T> (index : Int, array : 'T[]) : 'T
```


## <a name="input"></a>输入

### <a name="index--int"></a>索引： [Int](xref:microsoft.quantum.lang-ref.int)

元素的索引


### <a name="array--t"></a>array： t []

要编制索引的数组。



## <a name="output--t"></a>输出：不



## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

的每个元素的类型 `array` 。

## <a name="example"></a>示例

获取四个著名整数序列中的第三个数字。  (请注意，0索引对应于序列的 _第一个_ 值。 ) 

```qsharp
let lucas = [2, 1, 3, 4, 7, 11, 18, 29, 47, 76];
let prime = [2, 3, 5, 7, 11, 13, 17, 19, 23, 29];
let fibonacci = [0, 1, 1, 2, 3, 5, 8, 13, 21, 34];
let catalan = [1, 1, 2, 5, 14, 42, 132, 429, 1430, 4862];
let famous2 = Mapped(ElementAt<Int>(2, _), [lucas, prime, fibonacci, catalan]);
// same as: famous2 = [3, 5, 1, 2]
```

## <a name="see-also"></a>另请参阅

- [LookupFunction。](xref:Microsoft.Quantum.Arrays.LookupFunction)
- [ElementsAt。](xref:Microsoft.Quantum.Arrays.ElementsAt)