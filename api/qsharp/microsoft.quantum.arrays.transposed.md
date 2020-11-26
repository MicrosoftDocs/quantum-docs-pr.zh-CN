---
uid: Microsoft.Quantum.Arrays.Transposed
title: 转置函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Transposed
qsharp.summary: Returns the transpose of a matrix represented as an array of arrays.
ms.openlocfilehash: f293399d8e3a2cb32b2929e8d1591ac5eaefd277
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219985"
---
# <a name="transposed-function"></a>转置函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


返回一个矩阵的换位，该矩阵表示为数组的数组。

```qsharp
function Transposed<'T> (matrix : 'T[][]) : 'T[][]
```


## <a name="description"></a>描述

使用 $r $ rows 和 $c $ 列作为 $r \times c $ matrix 的输入。  矩阵是基于行的，即， `matrix[i][j]` 访问行 $i $ 和 column $j $ 的元素。

此函数返回作为输入矩阵换位的 $c \times r $ matrix。

## <a name="input"></a>输入

### <a name="matrix--t"></a>matrix： t [] []

基于行的 $r \times c $ matrix



## <a name="output--t"></a>输出： t [] []

$C \times r $ matrix

## <a name="type-parameters"></a>类型参数

### <a name="t"></a>找

的每个元素的类型 `matrix` 。