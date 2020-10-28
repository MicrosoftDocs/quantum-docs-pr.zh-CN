---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubit
title: ApplyToFirstQubit 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubit
qsharp.summary: Applies an operation to the first qubit in the register.
ms.openlocfilehash: 99439229e2c3d5a10073669cf1e742f6de3d7618
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696233"
---
# <a name="applytofirstqubit-operation"></a>ApplyToFirstQubit 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


将操作应用于寄存器中的第一个 qubit。

```qsharp
operation ApplyToFirstQubit (op : (Qubit => Unit), register : Qubit[]) : Unit
```


## <a name="input"></a>输入

### <a name="op--qubit--unit"></a>op： [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit) 

要应用于第一个 qubit 的操作


### <a name="register--qubit"></a>register： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit 数组到应用操作的第一个 Qubit



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>另请参阅

- [Canon. ApplyToFirstQubitA](xref:Microsoft.Quantum.Canon.ApplyToFirstQubitA)
- [Canon. ApplyToFirstQubitC](xref:Microsoft.Quantum.Canon.ApplyToFirstQubitC)
- [Canon. ApplyToFirstQubitCA](xref:Microsoft.Quantum.Canon.ApplyToFirstQubitCA)