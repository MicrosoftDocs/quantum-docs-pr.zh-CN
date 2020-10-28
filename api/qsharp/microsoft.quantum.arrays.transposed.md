---
uid: Microsoft.Quantum.Arrays.Transposed
title: 转置函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Transposed
qsharp.summary: Returns the transpose of a matrix represented as an array of arrays.
ms.openlocfilehash: 54071c461cf9f9411c332763b81e3bc448fb6c6e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696446"
---
# <a name="transposed-function"></a>转置函数

命名空间 [：](xref:Microsoft.Quantum.Arrays)

软件包 [](https://nuget.org/packages/)


返回一个矩阵的换位，该矩阵表示为数组的数组。

```qsharp
function Transposed<'T> (matrix : 'T[][]) : 'T[][]
```


## <a name="description"></a>说明

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