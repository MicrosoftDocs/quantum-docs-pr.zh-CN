---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubitC
title: ApplyToFirstQubitC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubitC
qsharp.summary: Applies operation op to the first qubit in the register. The modifier `C` indicates that the operation is controllable.
ms.openlocfilehash: e2c137ad4a8252731acf94d6f2343f8fd386b8e3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696231"
---
# <a name="applytofirstqubitc-operation"></a>ApplyToFirstQubitC 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


将操作 op 应用于寄存器中的第一个 qubit。
修饰符 `C` 指示操作可控制。

```qsharp
operation ApplyToFirstQubitC (op : (Qubit => Unit is Ctl), register : Qubit[]) : Unit
```


## <a name="input"></a>输入

### <a name="op--qubit--unit-ctl"></a>op： [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl

要应用于第一个 qubit 的操作


### <a name="register--qubit"></a>register： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit 数组到应用操作的第一个 Qubit



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>另请参阅

- [Canon. ApplyToFirstQubit](xref:Microsoft.Quantum.Canon.ApplyToFirstQubit)