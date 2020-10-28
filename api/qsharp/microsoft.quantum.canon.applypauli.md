---
uid: Microsoft.Quantum.Canon.ApplyPauli
title: ApplyPauli 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyPauli
qsharp.summary: Given a multi-qubit Pauli operator, applies the corresponding operation to a register.
ms.openlocfilehash: ccf8e1b3dbe5d4cd916a581aeab190ab0cff2021
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696289"
---
# <a name="applypauli-operation"></a>ApplyPauli 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


给定多 qubit Pauli 运算符，将相应的操作应用于寄存器。

```qsharp
operation ApplyPauli (pauli : Pauli[], target : Qubit[]) : Unit
```


## <a name="input"></a>输入

### <a name="pauli--pauli"></a>pauli： [pauli](xref:microsoft.quantum.lang-ref.pauli)[]

多 qubit Pauli 运算符，表示为单个 qubit Pauli 运算符的数组。


### <a name="target--qubit"></a>target： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

注册以在上应用给定的 Pauli 操作。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)

