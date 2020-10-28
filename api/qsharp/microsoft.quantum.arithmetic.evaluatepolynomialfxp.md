---
uid: Microsoft.Quantum.Arithmetic.EvaluatePolynomialFxP
title: EvaluatePolynomialFxP 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: EvaluatePolynomialFxP
qsharp.summary: Evaluates a polynomial in a fixed-point representation.
ms.openlocfilehash: 3903bf69d5b0a6e57530f2c6a44e1d351c8a605f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699888"
---
# <a name="evaluatepolynomialfxp-operation"></a>EvaluatePolynomialFxP 操作

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

软件包 [](https://nuget.org/packages/)


计算定点表示形式的多项式。

```qsharp
operation EvaluatePolynomialFxP (coefficients : Double[], fpx : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a>输入

### <a name="coefficients--double"></a>系数： [Double](xref:microsoft.quantum.lang-ref.double)[]

多项式的系数为 double 数组，即数组 $ [a_0，a_1，...，a_d] $ for 多项式 $P (x) = a_0 + a_1 x + \cdots + a_d x ^ d $。


### <a name="fpx--fixedpoint"></a>fpx： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

为其计算多项式的定点数。


### <a name="result--fixedpoint"></a>result： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

将保留 $P (x) $ 的定点数。 最初必须处于 $ \ket {0} $ 状态。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)

