---
uid: Microsoft.Quantum.Arrays.ColumnAt
title: ColumnAt 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ColumnAt
qsharp.summary: Extracts a column from a matrix.
ms.openlocfilehash: 32dc814de9b04563c2798a768f121723a1a8252c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846258"
---
# <a name="columnat-function"></a>ColumnAt 函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

## <a name="example"></a>示例

```qsharp
let matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]];
let column = ColumnAt(0, matrix);
// same as: column = [1, 4, 7]
```

## <a name="see-also"></a>另请参阅

- [。转换](xref:Microsoft.Quantum.Arrays.Transposed)
- [Microsoft 量子. 对角线](xref:Microsoft.Quantum.Arrays.Diagonal)