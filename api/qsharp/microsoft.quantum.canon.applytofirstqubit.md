---
uid: Microsoft.Quantum.Canon.ApplyToFirstQubit
title: ApplyToFirstQubit 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstQubit
qsharp.summary: Applies an operation to the first qubit in the register.
ms.openlocfilehash: 381f8d689fba1984ba7fa287d658578bd5b6c48c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850736"
---
# <a name="applytofirstqubit-operation"></a>ApplyToFirstQubit 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


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