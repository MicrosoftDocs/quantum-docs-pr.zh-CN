---
uid: Microsoft.Quantum.Math.ExpModI
title: ExpModI 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModI
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: e31273702a9850d0162f160ca412ff6d50f38b28
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700536"
---
# <a name="expmodi-function"></a>ExpModI 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)

软件包 [](https://nuget.org/packages/)


返回一个整数，该整数针对给定的模数引发了给定的幂。

```qsharp
function ExpModI (expBase : Int, power : Int, modulus : Int) : Int
```


## <a name="description"></a>说明

让我们通过 $N $ $p $ 和模数来表示 $x expBase。
该函数返回 $x ^ p \operatorname{mod} N $。

假定 $N $，$x $ 为正，且 power 为非负数。

## <a name="input"></a>输入

### <a name="expbase--int"></a>expBase： [Int](xref:microsoft.quantum.lang-ref.int)




### <a name="power--int"></a>幂： [Int](xref:microsoft.quantum.lang-ref.int)




### <a name="modulus--int"></a>取模： [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--int"></a>输出： [Int](xref:microsoft.quantum.lang-ref.int)



## <a name="remarks"></a>注解

与中的位数成正比，而 `power` 不是 `power` 本身。