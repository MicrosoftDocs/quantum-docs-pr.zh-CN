---
uid: Microsoft.Quantum.Math.DivRemL
title: DivRemL 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: DivRemL
qsharp.summary: Divides one BigInteger value by another, returns the result and the remainder as a tuple.
ms.openlocfilehash: d2ca91e0c3e8d69902234689359da7b73a8f7d1b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700644"
---
# <a name="divreml-function"></a>DivRemL 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)

软件包 [](https://nuget.org/packages/)


将一个 BigInteger 值除以另一个值，返回结果，并将余数作为元组返回。

```qsharp
function DivRemL (dividend : BigInt, divisor : BigInt) : (BigInt, BigInt)
```


## <a name="input"></a>输入

### <a name="dividend--bigint"></a>被除数： [BigInt](xref:microsoft.quantum.lang-ref.bigint)




### <a name="divisor--bigint"></a>除数： [BigInt](xref:microsoft.quantum.lang-ref.bigint)





## <a name="output--bigintbigint"></a>输出： ([bigint](xref:microsoft.quantum.lang-ref.bigint)、[bigint](xref:microsoft.quantum.lang-ref.bigint)) 



## <a name="remarks"></a>注解

有关更多详细信息，请参阅[BigInteger。](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.divrem)