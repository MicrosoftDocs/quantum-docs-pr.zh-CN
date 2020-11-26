---
uid: Microsoft.Quantum.Math.ExpModI
title: ExpModI 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModI
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: 197f7351ce76ebb7684ca8014cab9ab65d9c784c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96228484"
---
# <a name="expmodi-function"></a>ExpModI 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


返回一个整数，该整数针对给定的模数引发了给定的幂。

```qsharp
function ExpModI (expBase : Int, power : Int, modulus : Int) : Int
```


## <a name="description"></a>描述

让我们通过 $N $ $p $ 和模数来表示 $x expBase。
该函数返回 $x ^ p \operatorname{mod} N $。

假定 $N $，$x $ 为正，且 power 为非负数。

## <a name="input"></a>输入

### <a name="expbase--int"></a>expBase： [Int](xref:microsoft.quantum.lang-ref.int)




### <a name="power--int"></a>幂： [Int](xref:microsoft.quantum.lang-ref.int)




### <a name="modulus--int"></a>取模： [Int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--int"></a>输出： [Int](xref:microsoft.quantum.lang-ref.int)



## <a name="remarks"></a>备注

与中的位数成正比，而 `power` 不是 `power` 本身。