---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsC
title: ApplyToFirstTwoQubitsC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubitsC
qsharp.summary: Applies an operation to the first two qubits in the register. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 97706ffcc8700a0055ff37bbbaccc6fb4f8854b6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696213"
---
# <a name="applytofirsttwoqubitsc-operation"></a>ApplyToFirstTwoQubitsC 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


将操作应用于寄存器中的前两个 qubits。
修饰符 `C` 指示操作可控制。

```qsharp
operation ApplyToFirstTwoQubitsC (op : ((Qubit, Qubit) => Unit is Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a>输入

### <a name="op--qubitqubit--unit-ctl"></a>op： ([Qubit](xref:microsoft.quantum.lang-ref.qubit)，[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl

要应用于前两个 qubits 的操作


### <a name="register--qubit"></a>register： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit 数组指向应用了该操作的前两个 qubits。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>注解

这等效于：

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a>另请参阅

- [Canon. ApplyToFirstTwoQubits](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubits)