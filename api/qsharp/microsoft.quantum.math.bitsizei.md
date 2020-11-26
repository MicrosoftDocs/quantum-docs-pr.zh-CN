---
uid: Microsoft.Quantum.Math.BitSizeI
title: BitSizeI 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeI
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: 561450ef43144aa4d7820e1f15d9300018104acd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96195845"
---
# <a name="bitsizei-function"></a>BitSizeI 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


对于非负整数 `a` ，返回表示所需的位数 `a` 。

即，返回 < 2 ^ n $ $a 的最小 $n $。

```qsharp
function BitSizeI (a : Int) : Int
```


## <a name="input"></a>输入

### <a name="a--int"></a>a： [Int](xref:microsoft.quantum.lang-ref.int)

要计算其位大小的整数。



## <a name="output--int"></a>输出： [Int](xref:microsoft.quantum.lang-ref.int)

的位大小 `a` 。