---
uid: Microsoft.Quantum.Canon.ApplyToSubregisterCA
title: ApplyToSubregisterCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregisterCA
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 3eb210debf8980f057ed150f647d545f68734459
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696171"
---
# <a name="applytosubregisterca-operation"></a>ApplyToSubregisterCA 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


将操作应用于寄存器的 subregister，其 qubits 由其索引数组指定。
修饰符 `CA` 指示该操作是可控制的且 adjointable。

```qsharp
operation ApplyToSubregisterCA (op : (Qubit[] => Unit is Ctl + Adj), idxs : Int[], target : Qubit[]) : Unit
```


## <a name="input"></a>输入

### <a name="op--qubit--unit-ctl--adj"></a>op： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl + 形容词

要应用到 subregister 的操作。


### <a name="idxs--int"></a>idxs： [Int](xref:microsoft.quantum.lang-ref.int)[]

索引数组，指示将应用操作的 qubits。


### <a name="target--qubit"></a>target： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

注册操作所针对的。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>另请参阅

- [Canon. ApplyToSubregister](xref:Microsoft.Quantum.Canon.ApplyToSubregister)