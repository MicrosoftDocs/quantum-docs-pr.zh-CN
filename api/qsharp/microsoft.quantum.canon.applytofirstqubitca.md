---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitCA
title: ApplyToFirstQubitCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitCA
qsharp.summary: Applies operation op to the first qubit in the register. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 2e1db23ad819a85df99a826f406d9b0fbcc7a175
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696229"
---
# <a name="applytofirstqubitca-operation"></a>ApplyToFirstQubitCA 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


将操作 op 应用于寄存器中的第一个 qubit。
修饰符 `CA` 指示该操作是可控制的且 adjointable。

```qsharp
operation ApplyToFirstQubitCA (op : (Qubit => Unit is Adj + Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a>输入

### <a name="op--qubit--unit-adj--ctl"></a>op： [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit) 形容词 + Ctl

要应用于第一个 qubit 的操作


### <a name="register--qubit"></a>register： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit 数组到应用操作的第一个 Qubit



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>另请参阅

- [Canon. ApplyToFirstQubit](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)