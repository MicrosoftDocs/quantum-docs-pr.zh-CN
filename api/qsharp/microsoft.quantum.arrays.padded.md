---
uid: Microsoft.Quantum.Arrays.Padded
title: 填充的函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Padded
qsharp.summary: Returns an array padded at with specified values up to a specified length.
ms.openlocfilehash: 8742d4726e7ee32349bf3d0bd5077352ffca350b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696474"
---
# <a name="padded-function"></a>填充的函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

软件包 [](https://nuget.org/packages/)


返回使用指定的值（最大指定长度）填充的数组。

```qsharp
function Padded<'T> (nElementsTotal : Int, defaultElement : 'T, inputArray : 'T[]) : 'T[]
```


## <a name="input"></a>输入

### <a name="nelementstotal--int"></a>nElementsTotal： [Int](xref:microsoft.quantum.lang-ref.int)

填充的数组的长度。 如果为正， `inputArray` 则在头中填充。 如果此为负， `inputArray` 则在结尾处填充。


### <a name="defaultelement--t"></a>defaultElement： t

用于填充元素的默认值。


### <a name="inputarray--t"></a>inputArray： t []

其值位于输出数组的开头的数组。



## <a name="output--t"></a>输出： t []

一个数组 `output` ，它是 `inputArray` 在头中填充的， `defaultElement` 直到 `output` 长度为 `nElementsTotal`

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

数组元素的类型。