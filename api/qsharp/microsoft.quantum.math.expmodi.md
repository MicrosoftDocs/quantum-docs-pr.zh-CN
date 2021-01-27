---
uid: Microsoft.Quantum.Math.ExpModI
title: ExpModI 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModI
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: dd4fc7d98275f6a02e3b13163b92f0812c92a82f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857036"
---
# <a name="expmodi-function"></a>ExpModI 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


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



## <a name="remarks"></a>备注

与中的位数成正比，而 `power` 不是 `power` 本身。