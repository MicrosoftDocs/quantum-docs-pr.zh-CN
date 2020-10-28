---
uid: Microsoft.Quantum.Math.ExtendedGreatestCommonDivisorL
title: ExtendedGreatestCommonDivisorL 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExtendedGreatestCommonDivisorL
qsharp.summary: Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: e671405045d6d2587a8c6ccbac4ae3402f92f722
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700636"
---
# <a name="extendedgreatestcommondivisorl-function"></a>ExtendedGreatestCommonDivisorL 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)

软件包 [](https://nuget.org/packages/)


计算元组 $ (u，v) $，以便 $u \cdot a + v \cdot b = \operatorname{GCD} (a，b) $，其中 $ \operatorname{GCD} $ 是 $a $ 最大公因数 $a $ 和 $b $。 GCD 始终为正值。

```qsharp
function ExtendedGreatestCommonDivisorL (a : BigInt, b : BigInt) : (BigInt, BigInt)
```


## <a name="input"></a>输入

### <a name="a--bigint"></a>a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)

计算最大的最大公因数的第一个数字


### <a name="b--bigint"></a>b： [BigInt](xref:microsoft.quantum.lang-ref.bigint)

正在计算的最大扩展常见除数的第二个数字



## <a name="output--bigintbigint"></a>输出： ([bigint](xref:microsoft.quantum.lang-ref.bigint)、[bigint](xref:microsoft.quantum.lang-ref.bigint)) 

元组 $ (u，v) $，其属性 $u \cdot a + v \cdot b = \operatorname{GCD} (a，b) $。

## <a name="references"></a>参考

- 此实现取决于 https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm