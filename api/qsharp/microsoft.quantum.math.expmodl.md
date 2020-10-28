---
uid: Microsoft.Quantum.Math.ExpModL
title: ExpModL 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModL
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: 73d434bd364847b4e5e06d1a9f460424e0c50850
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700640"
---
# <a name="expmodl-function"></a>ExpModL 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)

软件包 [](https://nuget.org/packages/)


返回一个整数，该整数针对给定的模数引发了给定的幂。

```qsharp
function ExpModL (expBase : BigInt, power : BigInt, modulus : BigInt) : BigInt
```


## <a name="description"></a>说明

让我们通过 $N $ $p $ 和模数来表示 $x expBase。
该函数返回 $x ^ p \operatorname{mod} N $。

假定 $N $，$x $ 为正，且 power 为非负数。

## <a name="input"></a>输入

### <a name="expbase--bigint"></a>expBase： [BigInt](xref:microsoft.quantum.lang-ref.bigint)




### <a name="power--bigint"></a>power： [BigInt](xref:microsoft.quantum.lang-ref.bigint)




### <a name="modulus--bigint"></a>模数： [BigInt](xref:microsoft.quantum.lang-ref.bigint)





## <a name="output--bigint"></a>输出： [BigInt](xref:microsoft.quantum.lang-ref.bigint)



## <a name="remarks"></a>注解

与中的位数成正比，而 `power` 不是 `power` 本身。