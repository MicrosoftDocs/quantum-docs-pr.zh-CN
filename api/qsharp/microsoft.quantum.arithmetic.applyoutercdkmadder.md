---
uid: Microsoft.Quantum.Arithmetic.ApplyOuterCDKMAdder
title: ApplyOuterCDKMAdder 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyOuterCDKMAdder
qsharp.summary: Reversible, in-place ripple-carry operation that is used in the integer addition operation RippleCarryAdderCDKM below. Given two qubit registers `xs` and `ys` of the same length, the operation applies a ripple carry sequence of CNOT and CCNOT gates with qubits in `xs` and `ys` as the controls and qubits in `xs` as the targets.
ms.openlocfilehash: 81311a75beedb62331184faf4e1523f3ccc74f43
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96190660"
---
# <a name="applyoutercdkmadder-operation"></a>ApplyOuterCDKMAdder 操作

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


在下面的整数加法运算中使用的可逆的就地波纹-携带运算 RippleCarryAdderCDKM。
假设有两个 qubit 寄存器， `xs` 并且 `ys` 具有相同的长度，则操作会将 CNOT-CONTAINS 和 CCNOT 入口序列应用到中的 qubits， `xs` 并将 `ys` 作为目标中的控件和 qubits `xs` 。

```qsharp
operation ApplyOuterCDKMAdder (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, ancilla : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a>输入

### <a name="xs--littleendian"></a>xs： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

第一个 qubit 寄存器，其中包含控件和目标。


### <a name="ys--littleendian"></a>y) ： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

第二个 qubit 注册，对控件构成。


### <a name="ancilla--qubit"></a>ancilla： [Qubit](xref:microsoft.quantum.lang-ref.qubit)

传递给此操作的 RippleCarryAdderCDKM 中使用的 ancilla qubit。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>参考

- Steven Cuccaro、Thomas Draper、Samuel Kutin、David Petrie Moulton： "A 新的量程波纹-携带加法线路"，2004。
  https://arxiv.org/abs/quant-ph/0410184v1