---
uid: Microsoft.Quantum.Arithmetic.AddFxP
title: AddFxP 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddFxP
qsharp.summary: Adds two fixed-point numbers stored in quantum registers.
ms.openlocfilehash: 36a5d585a493f0e6f33f74b1686aaa01cca7ac0b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191034"
---
# <a name="addfxp-operation"></a>AddFxP 操作

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Numerics)


添加存储在量程寄存器中的两个定点数。

```qsharp
operation AddFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit is Adj + Ctl
```


## <a name="description"></a>描述

在状态 $ \ket{f_1} $ 和 $ \ket{f_2} $ 中分别给定了两个定点寄存器，执行操作 $ \ket{f_1} \ket{f_2} \mapsto \ket{f_1} \ket{f_1 + f_2} $。

## <a name="input"></a>输入

### <a name="fp1--fixedpoint"></a>fp1： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

第一个固定点数字


### <a name="fp2--fixedpoint"></a>fp2： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

第二个定点数将被更新，以包含两个输入的和。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>备注

当前实现要求两个固定点数字与最小有效位之间具有相同的点位置计数，即 $n _i $，$p _i $ 必须相等。