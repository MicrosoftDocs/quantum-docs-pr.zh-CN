---
uid: Microsoft.Quantum.Arithmetic.SquareI
title: SquareI 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: SquareI
qsharp.summary: Computes the square of the integer `xs` into `result`, which must be zero initially.
ms.openlocfilehash: d7334d50f245ba358624e6e2eee94b63d9ed7569
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696567"
---
# <a name="squarei-operation"></a>SquareI 操作

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

软件包 [](https://nuget.org/packages/)


将整数的平方计算 `xs` 为 `result` ，其最初必须为零。

```qsharp
operation SquareI (xs : Microsoft.Quantum.Arithmetic.LittleEndian, result : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a>输入

### <a name="xs--littleendian"></a>xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$n $ bit (LittleEndian) 


### <a name="result--littleendian"></a>result： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

$ 2n $-bit result (LittleEndian) ，其最初必须处于 $ \ket {0} $ 状态。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>注解

使用标准的移位和添加方法计算正方形。 与直向前解决方案节省 $n-$1 qubits，此解决方案先复制 x，然后应用常规乘数，然后撤消复制操作。