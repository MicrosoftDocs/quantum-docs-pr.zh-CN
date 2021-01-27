---
uid: Microsoft.Quantum.Math.BitSizeI
title: BitSizeI 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeI
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: e7edf37a81571dfa1d4cb755493e1863a44c694e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857700"
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