---
uid: Microsoft.Quantum.Canon.ApplyToFirstThreeQubitsCA
title: ApplyToFirstThreeQubitsCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstThreeQubitsCA
qsharp.summary: Applies an operation to the first three qubits in the register. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: bd7a3ac260d370aae9da8691fcd34a8b6221d451
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696222"
---
# <a name="applytofirstthreequbitsca-operation"></a>ApplyToFirstThreeQubitsCA 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


将操作应用于寄存器中的前三个 qubits。
修饰符 `CA` 指示该操作是可控制的且 adjointable。

```qsharp
operation ApplyToFirstThreeQubitsCA (op : ((Qubit, Qubit, Qubit) => Unit is Adj + Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a>输入

### <a name="op--qubitqubitqubit--unit-adj--ctl"></a>op： ([Qubit](xref:microsoft.quantum.lang-ref.qubit)，[Qubit](xref:microsoft.quantum.lang-ref.qubit)，[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Unit](xref:microsoft.quantum.lang-ref.unit) 形容词 + Ctl

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