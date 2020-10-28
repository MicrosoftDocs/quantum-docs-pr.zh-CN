---
uid: Microsoft.Quantum.Canon.ApplyPauliFromBitString
title: ApplyPauliFromBitString 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyPauliFromBitString
qsharp.summary: Applies a Pauli operator on each qubit in an array if the corresponding bit of a Boolean array matches a given input.
ms.openlocfilehash: 09754accb92c1339b781003e5722e3c8f5884e6f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696288"
---
# <a name="applypaulifrombitstring-operation"></a>ApplyPauliFromBitString 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


如果布尔数组的相应位与给定的输入相匹配，则对数组中的每个 qubit 应用 Pauli 运算符。

```qsharp
operation ApplyPauliFromBitString (pauli : Pauli, bitApply : Bool, bits : Bool[], qubits : Qubit[]) : Unit
```


## <a name="input"></a>输入

### <a name="pauli--pauli"></a>pauli： [pauli](xref:microsoft.quantum.lang-ref.pauli)

要应用于 `qubits[idx]` where 的 Pauli 运算符 `bitsApply == bits[idx]`


### <a name="bitapply--bool"></a>bitApply： [Bool](xref:microsoft.quantum.lang-ref.bool)

如果 bit 为此值，则应用 Pauli


### <a name="bits--bool"></a>bits： [Bool](xref:microsoft.quantum.lang-ref.bool)[]

指定应操作的相应 qubit 的布尔型寄存器 `qubits`


### <a name="qubits--qubit"></a>qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

量程注册，可以选择应用指定的 Pauli 运算符



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>注解

布尔数组和量程寄存器的长度必须相等。