---
uid: Microsoft.Quantum.Canon.Angle
title: Angle 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Angle
qsharp.summary: Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.
ms.openlocfilehash: 1d8a9c2c19469e4949f043edd1ba91021fa42e78
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219407"
---
# <a name="angle-function"></a>Angle 函数

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


如果的值为奇数，则返回 1; `index` 如果的值为偶数，则返回-1 `index` 。

```qsharp
function Angle (index : Int) : Int
```


## <a name="description"></a>描述

值对应于指定赋值的 n 变量和函数的 Rademacher-Walsh 的系数的符号，用于决定旋转角度。

## <a name="input"></a>输入

### <a name="index--int"></a>索引： [Int](xref:microsoft.quantum.lang-ref.int)

输入分配作为整数 (，从0到 2 ^ n-1) 



## <a name="output--int"></a>输出： [Int](xref:microsoft.quantum.lang-ref.int)

