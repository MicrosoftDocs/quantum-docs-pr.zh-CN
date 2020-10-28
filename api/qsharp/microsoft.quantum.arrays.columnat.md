---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: ColumnAt 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: ad09ada1a2253a54e70dddd6dba8aa243d2cd5a6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696553"
---
# <a name="columnat-function"></a>ColumnAt 函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

软件包 [](https://nuget.org/packages/)


提取矩阵中的列。

```qsharp
function ColumnAt<'T> (column : Int, matrix : 'T[][]) : 'T[]
```


## <a name="description"></a>说明

此函数按行顺序提取矩阵中的列。
提取第一个索引的行 corrsponds 到元素的访问权限，因此无需进一步处理。

## <a name="input"></a>输入

### <a name="column--int"></a>列： [Int](xref:microsoft.quantum.lang-ref.int)

矩阵的列


### <a name="matrix--t"></a>matrix： t [] []

按行顺序排列的二维矩阵



## <a name="output--t"></a>输出： t []



## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

的每个元素的类型 `matrix` 。

## <a name="see-also"></a>另请参阅

- [。转换](xref:Microsoft.Quantum.Arrays.Transposed)
- [Microsoft 量子. 对角线](xref:Microsoft.Quantum.Arrays.Diagonal)