---
uid: Microsoft.Quantum.Canon.ApplyCCNOTChain
title: ApplyCCNOTChain 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCCNOTChain
qsharp.summary: Implements a cascade of CCNOT gates controlled on corresponding bits of two qubit registers, acting on the next qubit of one of the registers. Starting from the qubits at position 0 in both registers as controls, CCNOT is applied to the qubit at position 1 of the target register, then controlled by the qubits at position 1 acting on the qubit at position 2 in the target register, etc., ending with an action on the target qubit in position `Length(nQubits)-1`.
ms.openlocfilehash: 53fdd59b06d542494647acb665f248fc18de93d9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845143"
---
# <a name="applyccnotchain-operation"></a>ApplyCCNOTChain 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


实现控制在两个 qubit 寄存器的相应位上控制的 CCNOT 入口的层叠，这是在其中一个寄存器的下一个 qubit 上进行的。
从两个寄存器中的位置0开始，将 CCNOT 应用于目标寄存器的位置1处的 qubit，然后由 qubits 在目标寄存器中的位置2进行控制，在目标 qubits 的位置2处进行控制，以目标 qubit 上的操作结束 `Length(nQubits)-1` 。

```qsharp
operation ApplyCCNOTChain (register : Qubit[], targets : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>输入

### <a name="register--qubit"></a>register： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit register，仅用于控件。


### <a name="targets--qubit"></a>目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit register，用于控件和作为目标。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>备注

目标 qubit 注册必须有一个以上的 qubit。