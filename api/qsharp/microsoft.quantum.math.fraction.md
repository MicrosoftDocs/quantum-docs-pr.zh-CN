---
uid: Microsoft.Quantum.Math.Fraction
title: 分式用户定义类型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: 1838bb2b605b109742948ec0633b08ca01baea98
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210669"
---
# <a name="fraction-user-defined-type"></a>分式用户定义类型

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


表示形式的有理数 `p/q` 。 整数 `p` 是元组的第一个元素， `q` 是元组的第二个元素。

```qsharp

newtype Fraction = (Numerator : Int, Denominator : Int);
```



## <a name="named-items"></a>命名项

### <a name="numerator--int"></a>分子： [Int](xref:microsoft.quantum.lang-ref.int)

分数的分子。
### <a name="denominator--int"></a>分母： [Int](xref:microsoft.quantum.lang-ref.int)

分数的分母/