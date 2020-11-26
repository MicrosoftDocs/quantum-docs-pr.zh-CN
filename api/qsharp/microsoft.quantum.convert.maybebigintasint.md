---
uid: Microsoft.Quantum.Convert.MaybeBigIntAsInt
title: MaybeBigIntAsInt 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: MaybeBigIntAsInt
qsharp.summary: Converts a given big integer to an equivalent integer, if possible. The function returns a pair of the resulting integer and a Boolean flag which is true, if and only if the conversion was possible.
ms.openlocfilehash: d0a598497e8a8f019bbd8da7db1c6cc4d7bde017
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224269"
---
# <a name="maybebigintasint-function"></a>MaybeBigIntAsInt 函数

命名空间 [：](xref:Microsoft.Quantum.Convert)

包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


如果可能，将给定的大整数转换为等效的整数。
当且仅当可以进行转换时，函数将返回生成的整数对以及布尔标志。

```qsharp
function MaybeBigIntAsInt (a : BigInt) : (Int, Bool)
```


## <a name="input"></a>输入

### <a name="a--bigint"></a>a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)





## <a name="output--intbool"></a>Output： ([Int](xref:microsoft.quantum.lang-ref.int)、[Bool](xref:microsoft.quantum.lang-ref.bool)) 



## <a name="remarks"></a>备注

有关更多详细信息，请参阅 [c # BigInteger 构造函数](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) 。