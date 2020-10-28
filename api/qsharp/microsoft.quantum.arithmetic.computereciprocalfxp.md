---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalFxP
title: ComputeReciprocalFxP 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalFxP
qsharp.summary: Computes $1/x$ for a fixed-point number $x$.
ms.openlocfilehash: e8f31d82fc69a3d7f4b571c4a679255dffc28b7f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699909"
---
# <a name="computereciprocalfxp-operation"></a>ComputeReciprocalFxP 操作

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

软件包 [](https://nuget.org/packages/)


计算固定点数字的 $ 1/x $ $x $。

```qsharp
operation ComputeReciprocalFxP (x : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a>输入

### <a name="x--fixedpoint"></a>x： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

要反转的固定点数字。


### <a name="result--fixedpoint"></a>result： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

将保存结果的定点数。 必须初始化为 $ \ket{0.0} $。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)

