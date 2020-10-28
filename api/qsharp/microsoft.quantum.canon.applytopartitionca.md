---
uid: Microsoft.Quantum.Canon.ApplyToPartitionCA
title: ApplyToPartitionCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartitionCA
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 8ea437a0e25ed43eb745a7740ecd8861ced1350a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696190"
---
# <a name="applytopartitionca-operation"></a>ApplyToPartitionCA 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


将一对操作应用于寄存器的给定分区分为两部分。
修饰符 `CA` 指示该操作是可控制的且 adjointable。

```qsharp
operation ApplyToPartitionCA (op : ((Qubit[], Qubit[]) => Unit is Ctl + Adj), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit
```


## <a name="input"></a>输入

### <a name="op--qubitqubit--unit-ctl--adj"></a>op： ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[]，[Qubit](xref:microsoft.quantum.lang-ref.qubit)[] ) => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + 形容词

要应用于给定分区的一对操作。


### <a name="numberofqubitstofirstargument--int"></a>numberOfQubitsToFirstArgument： [Int](xref:microsoft.quantum.lang-ref.int)

要放入分区第一部分中的 qubits 的数目。
其余的 qubits 构成分区的第二部分。


### <a name="target--qubit"></a>target： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

给定的两个操作正在进行分区和操作的 qubits 的寄存器。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>另请参阅

- [Canon. ApplyToPartition](xref:Microsoft.Quantum.Canon.ApplyToPartition)