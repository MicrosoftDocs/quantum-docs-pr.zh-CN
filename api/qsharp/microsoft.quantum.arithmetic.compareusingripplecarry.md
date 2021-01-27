---
uid: Microsoft.Quantum.Arithmetic.CompareUsingRippleCarry
title: CompareUsingRippleCarry 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CompareUsingRippleCarry
qsharp.summary: This operation tests if an integer represented by a register of qubits is greater than another integer, applying an XOR of the result onto an output qubit.
ms.openlocfilehash: ce2be140ecfed21dea6212651249b4a11d2542c8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843290"
---
# <a name="compareusingripplecarry-operation"></a>CompareUsingRippleCarry 操作

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


此操作测试由 qubits 的寄存器表示的整数是否大于另一个整数，并将结果 XOR 应用到输出 qubit。

```qsharp
operation CompareUsingRippleCarry (x : Microsoft.Quantum.Arithmetic.LittleEndian, y : Microsoft.Quantum.Arithmetic.LittleEndian, output : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>说明

给定两个整数 `x` 并 `y` 存储在大小相等的 qubit 寄存器中，此操作将检查它们是否满足 `x > y` 。 如果为 true，则将 1 XORed 到输出 qubit。 否则，0将 XORed 到输出 qubit 中。
换句话说，此操作可由单一 $ $ \begin{align} U\ket {x} \ 票证 {y} \ 票证 {z} = \ket{x}\ket{y}\ket{z\oplus (x>y) } 表示。
\end{align} $ $

## <a name="input"></a>输入

### <a name="x--littleendian"></a>x： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

要进行比较的第一个数字以 `LittleEndian` qubit 寄存器格式存储。


### <a name="y--littleendian"></a>y： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

要进行比较的第二个数字，以 `LittleEndian` qubit 寄存器格式存储。


### <a name="output--qubit"></a>输出： [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit，用于存储比较 $x>y $ 的结果。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>参考

- 新的量程波纹-携带加法线路 Steven Cuccaro、Thomas Draper、Samuel Kutin、David Petrie Moulton https://arxiv.org/abs/quant-ph/0410184