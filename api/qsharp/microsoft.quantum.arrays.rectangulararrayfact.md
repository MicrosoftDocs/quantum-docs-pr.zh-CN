---
uid: Microsoft.Quantum.Arrays.RectangularArrayFact
title: RectangularArrayFact 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: RectangularArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a rectangular shape
ms.openlocfilehash: b8ef7d52f7f815ca3e21ded1236e775a381646cb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220410"
---
# <a name="rectangulararrayfact-function"></a>RectangularArrayFact 函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


表示二维数组具有矩形形状的条件

```qsharp
function RectangularArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a>描述

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

## <a name="see-also"></a>另请参阅

- [SquareArrayFact。](xref:Microsoft.Quantum.Arrays.SquareArrayFact)