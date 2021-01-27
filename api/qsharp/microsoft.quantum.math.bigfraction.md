---
uid: Microsoft.Quantum.Math.BigFraction
title: BigFraction 用户定义的类型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: BigFraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: bfbf49e7a3d060417e506a1977c20adc08b81f0e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846902"
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