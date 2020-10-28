---
uid: Microsoft.Quantum.Arrays.RectangularArrayFact
title: RectangularArrayFact 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: RectangularArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a rectangular shape
ms.openlocfilehash: f0d3f4d6bfa9e86f1c7a91792c09e16fe86433a0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696464"
---
# <a name="rectangulararrayfact-function"></a>RectangularArrayFact 函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

软件包 [](https://nuget.org/packages/)


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

## <a name="see-also"></a>另请参阅

- [SquareArrayFact。](xref:Microsoft.Quantum.Arrays.SquareArrayFact)