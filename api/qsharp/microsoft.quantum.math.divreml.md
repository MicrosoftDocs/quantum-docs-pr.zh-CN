---
uid: Microsoft.Quantum.Math.DivRemL
title: DivRemL 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: DivRemL
qsharp.summary: Divides one BigInteger value by another, returns the result and the remainder as a tuple.
ms.openlocfilehash: 329f4d0bc21e74ab6c138af39c88cdcd964e63cf
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857093"
---
# <a name="divreml-function"></a>DivRemL 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)

包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


将一个 BigInteger 值除以另一个值，返回结果，并将余数作为元组返回。

```qsharp
function DivRemL (dividend : BigInt, divisor : BigInt) : (BigInt, BigInt)
```


## <a name="input"></a>输入

### <a name="dividend--bigint"></a>被除数： [BigInt](xref:microsoft.quantum.lang-ref.bigint)




### <a name="divisor--bigint"></a>除数： [BigInt](xref:microsoft.quantum.lang-ref.bigint)





## <a name="output--bigintbigint"></a>输出： ([bigint](xref:microsoft.quantum.lang-ref.bigint)、[bigint](xref:microsoft.quantum.lang-ref.bigint)) 



## <a name="remarks"></a>备注

有关更多详细信息，请参阅[BigInteger。](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.divrem)