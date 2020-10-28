---
uid: Microsoft.Quantum.Math.BigFraction
title: BigFraction 用户定义的类型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BigFraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: a8daa54947097b95040a2dfa7a4d1b90bfaff856
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700492"
---
# <a name="bigfraction-user-defined-type"></a>BigFraction 用户定义的类型

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)

软件包 [](https://nuget.org/packages/)


表示形式的有理数 `p/q` 。 整数 `p` 是元组的第一个元素， `q` 是元组的第二个元素。

```qsharp

newtype BigFraction = (Numerator : BigInt, Denominator : BigInt);
```



## <a name="named-items"></a>命名项

### <a name="numerator--bigint"></a>分子： [BigInt](xref:microsoft.quantum.lang-ref.bigint)

分数的分子。
### <a name="denominator--bigint"></a>分母： [BigInt](xref:microsoft.quantum.lang-ref.bigint)

分数的分母/