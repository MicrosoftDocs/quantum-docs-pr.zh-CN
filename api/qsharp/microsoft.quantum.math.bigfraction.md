---
uid: Microsoft.Quantum.Math.BigFraction
title: BigFraction 用户定义的类型
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BigFraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: 1c9b9e350c4fa3664b2c66da05149005b1170ec3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96211077"
---
# <a name="bigfraction-user-defined-type"></a>BigFraction 用户定义的类型

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


表示形式的有理数 `p/q` 。 整数 `p` 是元组的第一个元素， `q` 是元组的第二个元素。

```qsharp

newtype BigFraction = (Numerator : BigInt, Denominator : BigInt);
```



## <a name="named-items"></a>命名项

### <a name="numerator--bigint"></a>分子： [BigInt](xref:microsoft.quantum.lang-ref.bigint)

分数的分子。
### <a name="denominator--bigint"></a>分母： [BigInt](xref:microsoft.quantum.lang-ref.bigint)

分数的分母/