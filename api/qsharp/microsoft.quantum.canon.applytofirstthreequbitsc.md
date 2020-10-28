---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsC
title: ApplyToFirstThreeQubitsC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubitsC
qsharp.summary: Applies an operation to the first three qubits in the register. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: 9450b084cd77f75511fe631cda9a4f9fc426142d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696226"
---
# <a name="applytofirstthreequbitsc-operation"></a>ApplyToFirstThreeQubitsC 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


将操作应用于寄存器中的前三个 qubits。
修饰符 `C` 指示操作可控制。

```qsharp
operation ApplyToFirstThreeQubitsC (op : ((Qubit, Qubit, Qubit) => Unit is Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a>输入

### <a name="op--qubitqubitqubit--unit-ctl"></a>op： ([Qubit](xref:microsoft.quantum.lang-ref.qubit)，[Qubit](xref:microsoft.quantum.lang-ref.qubit)，[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl

要应用于前三个 qubits 的操作


### <a name="register--qubit"></a>register： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit 数组到应用操作的前三个 qubits。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>注解

这等效于：

```qsharp
op(register[0], register[1], register[2]);
```

## <a name="see-also"></a>另请参阅

- [Canon. ApplyToFirstThreeQubits](xref:Microsoft.Quantum.Canon.ApplyToFirstThreeQubits)