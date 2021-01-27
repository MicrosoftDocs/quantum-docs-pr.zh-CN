---
uid: Microsoft.Quantum.Arrays.RectangularArrayFact
title: RectangularArrayFact 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: RectangularArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a rectangular shape
ms.openlocfilehash: 8cf6b85da6e8fee7fc255a173753a6468d8134b9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845488"
---
# <a name="rectangulararrayfact-function"></a>RectangularArrayFact 函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


表示二维数组具有矩形形状的条件

```qsharp
function RectangularArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a>说明

此函数断言数组中的每一行都具有相同的长度。

## <a name="input"></a>输入

### <a name="array--t"></a>array： t [] []

二维元素数组


### <a name="message--string"></a>消息： [字符串](xref:microsoft.quantum.lang-ref.string)

如果数组不是矩形数组，则为要打印的消息



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

的每个元素的类型 `array` 。

## <a name="example"></a>示例

```qsharp
RectangularArrayFact([[1, 2], [3, 4]], "Array is not rectangular");       // okay
RectangularArrayFact([[1, 2, 3], [4, 5, 6]], "Array is not rectangular"); // okay
RectangularArrayFact([[1, 2], [3, 4, 5]], "Array is not rectangular");    // will fail
```

## <a name="see-also"></a>另请参阅

- [SquareArrayFact。](xref:Microsoft.Quantum.Arrays.SquareArrayFact)