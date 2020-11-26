---
uid: Microsoft.Quantum.Arithmetic.ComputeReciprocalFxP
title: ComputeReciprocalFxP 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ComputeReciprocalFxP
qsharp.summary: Computes $1/x$ for a fixed-point number $x$.
ms.openlocfilehash: 3ca050d6ce9daaa10e14c2f12dd571398cf436b0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223385"
---
# <a name="computereciprocalfxp-operation"></a>ComputeReciprocalFxP 操作

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Numerics)


计算固定点数字的 $ 1/x $ $x $。

```qsharp
operation ComputeReciprocalFxP (x : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="input"></a>输入

### <a name="x--fixedpoint"></a>x： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

要反转的固定点数字。


### <a name="result--fixedpoint"></a>result： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

将保存结果的定点数。 必须初始化为 $ \ket{0.0} $。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)

