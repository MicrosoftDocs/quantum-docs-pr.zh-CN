---
uid: Microsoft.Quantum.Arithmetic.MultiplyFxP
title: MultiplyFxP 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyFxP
qsharp.summary: Multiplies two fixed-point numbers in quantum registers.
ms.openlocfilehash: 18883f3f4c3793b91e248f4bd89f9def640bf254
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696607"
---
# <a name="multiplyfxp-operation"></a>MultiplyFxP 操作

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

软件包 [](https://nuget.org/packages/)


将量程寄存器中的两个定点数相乘。

```qsharp
operation MultiplyFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint, result : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="input"></a>输入

### <a name="fp1--fixedpoint"></a>fp1： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

第一个固定点号。


### <a name="fp2--fixedpoint"></a>fp2： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

第二个定点数。


### <a name="result--fixedpoint"></a>result： [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

结果固定点数字，最初必须处于状态 $ \ket {0} $。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>注解

当前实现要求三个固定点数字具有相同的点位置和相同数量的 qubits。