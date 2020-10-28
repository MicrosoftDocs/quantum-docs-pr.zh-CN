---
uid: Microsoft.Quantum.Arrays.Diagonal
title: 对角函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Diagonal
qsharp.summary: Returns an array of diagonal elements of a 2-dimensional array
ms.openlocfilehash: 180b7185c94d712fa02100cb97abfbb6c464d12a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696541"
---
# <a name="diagonal-function"></a>对角函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

软件包 [](https://nuget.org/packages/)


返回二维数组的对角元素数组

```qsharp
function Diagonal<'T> (matrix : 'T[][]) : 'T[]
```


## <a name="description"></a>说明

如果二维数组没有方形形状，则返回超出行数和列数的最小值。

## <a name="input"></a>输入

### <a name="matrix--t"></a>matrix： t [] []

按行顺序排列的二维矩阵



## <a name="output--t"></a>输出： t []



## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

的每个元素的类型 `matrix` 。

## <a name="see-also"></a>另请参阅

- [。转换](xref:Microsoft.Quantum.Arrays.Transposed)