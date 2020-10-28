---
uid: Microsoft.Quantum.Math.ExtendedGreatestCommonDivisorI
title: ExtendedGreatestCommonDivisorI 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExtendedGreatestCommonDivisorI
qsharp.summary: Computes a tuple $(u,v)$ such that $u \cdot a + v \cdot b = \operatorname{GCD}(a, b)$, where $\operatorname{GCD}$ is $a$ greatest common divisor of $a$ and $b$. The GCD is always positive.
ms.openlocfilehash: 8cb21ae5052ae6c5a8aed8be71d6bd3d32034272
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700637"
---
# <a name="extendedgreatestcommondivisori-function"></a>ExtendedGreatestCommonDivisorI 函数

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)

软件包 [](https://nuget.org/packages/)


计算元组 $ (u，v) $，以便 $u \cdot a + v \cdot b = \operatorname{GCD} (a，b) $，其中 $ \operatorname{GCD} $ 是 $a $ 最大公因数 $a $ 和 $b $。 GCD 始终为正值。

```qsharp
function ExtendedGreatestCommonDivisorI (a : Int, b : Int) : (Int, Int)
```


## <a name="input"></a>输入

### <a name="a--int"></a>a： [Int](xref:microsoft.quantum.lang-ref.int)

计算最大的最大公因数的第一个数字


### <a name="b--int"></a>b： [Int](xref:microsoft.quantum.lang-ref.int)

正在计算的最大扩展常见除数的第二个数字



## <a name="output--intint"></a>Output： ([int](xref:microsoft.quantum.lang-ref.int)，[int](xref:microsoft.quantum.lang-ref.int)) 

元组 $ (u，v) $，其属性 $u \cdot a + v \cdot b = \operatorname{GCD} (a，b) $。

## <a name="references"></a>参考

- 此实现取决于 https://en.wikipedia.org/wiki/Extended_Euclidean_algorithm