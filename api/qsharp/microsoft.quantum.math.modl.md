---
uid: Microsoft.Quantum.Math.ModL
title: ModL 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ModL
qsharp.summary: Returns the modulus of a number with respect to another number.
ms.openlocfilehash: 0b1ac69cc1474e9cfa6a3489b2b2fdf497e812e0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227788"
---
# <a name="modl-function"></a>ModL 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


返回与另一个数字相关的数字的模数。

```qsharp
function ModL (a : BigInt, b : BigInt) : BigInt
```


## <a name="input"></a>输入

### <a name="a--bigint"></a>a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)

要返回其模数的输入 $a $。


### <a name="b--bigint"></a>b： [BigInt](xref:microsoft.quantum.lang-ref.bigint)

要返回其 $a $ 的模数的相对数量。



## <a name="output--bigint"></a>输出： [BigInt](xref:microsoft.quantum.lang-ref.bigint)

取模 $a \bmod b $。