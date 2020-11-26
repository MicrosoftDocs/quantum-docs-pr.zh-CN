---
uid: Microsoft.Quantum.Math.ExpModL
title: ExpModL 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModL
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: 07da113caeb9f6f3f3f3f92f13478f33021bfa14
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210738"
---
# <a name="expmodl-function"></a>ExpModL 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


返回一个整数，该整数针对给定的模数引发了给定的幂。

```qsharp
function ExpModL (expBase : BigInt, power : BigInt, modulus : BigInt) : BigInt
```


## <a name="description"></a>描述

让我们通过 $N $ $p $ 和模数来表示 $x expBase。
该函数返回 $x ^ p \operatorname{mod} N $。

假定 $N $，$x $ 为正，且 power 为非负数。

## <a name="input"></a>输入

### <a name="expbase--bigint"></a>expBase： [BigInt](xref:microsoft.quantum.lang-ref.bigint)




### <a name="power--bigint"></a>power： [BigInt](xref:microsoft.quantum.lang-ref.bigint)




### <a name="modulus--bigint"></a>模数： [BigInt](xref:microsoft.quantum.lang-ref.bigint)





## <a name="output--bigint"></a>输出： [BigInt](xref:microsoft.quantum.lang-ref.bigint)



## <a name="remarks"></a>备注

与中的位数成正比，而 `power` 不是 `power` 本身。