---
uid: Microsoft.Quantum.Math.BitSizeL
title: BitSizeL 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BitSizeL
qsharp.summary: >-
  For a non-negative integer `a`, returns the number of bits required to represent `a`.

  That is, returns the smallest $n$ such that $a < 2^n$.
ms.openlocfilehash: 8b3d4cceb69619ed32977337fc0fe7401db38cbd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211043"
---
# <a name="bitsizel-function"></a>BitSizeL 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


对于非负整数 `a` ，返回表示所需的位数 `a` 。

即，返回 < 2 ^ n $ $a 的最小 $n $。

```qsharp
function BitSizeL (a : BigInt) : Int
```


## <a name="input"></a>输入

### <a name="a--bigint"></a>a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)

要计算其位大小的整数。



## <a name="output--int"></a>输出： [Int](xref:microsoft.quantum.lang-ref.int)

的位大小 `a` 。