---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubits
title: ApplyToFirstTwoQubits 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubits
qsharp.summary: Applies an operation to the first two qubits in the register.
ms.openlocfilehash: aad07889c0dbf2329304c98b06dbd0c225df8a81
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696217"
---
# <a name="applytofirsttwoqubits-operation"></a>ApplyToFirstTwoQubits 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


将操作应用于寄存器中的前两个 qubits。

```qsharp
operation ApplyToFirstTwoQubits (op : ((Qubit, Qubit) => Unit), register : Qubit[]) : Unit
```


## <a name="input"></a>输入

### <a name="op--qubitqubit--unit"></a>op： ([Qubit](xref:microsoft.quantum.lang-ref.qubit)，[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit) 

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

- [Canon. ApplyToFirstTwoQubitsA](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsA)
- [Canon. ApplyToFirstTwoQubitsC](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsC)
- [Canon. ApplyToFirstTwoQubitsCA](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsCA)