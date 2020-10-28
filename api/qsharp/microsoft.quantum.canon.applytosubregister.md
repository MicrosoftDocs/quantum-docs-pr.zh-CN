---
uid: Microsoft.Quantum.Canon.ApplyToSubregister
title: ApplyToSubregister 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToSubregister
qsharp.summary: Applies an operation to a subregister of a register, with qubits specified by an array of their indices.
ms.openlocfilehash: c9181b8962d36b20f7a9140eb7aaef11aee7faa0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696177"
---
# <a name="applytosubregister-operation"></a>ApplyToSubregister 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


将操作应用于寄存器的 subregister，其 qubits 由其索引数组指定。

```qsharp
operation ApplyToSubregister (op : (Qubit[] => Unit), idxs : Int[], target : Qubit[]) : Unit
```


## <a name="input"></a>输入

### <a name="op--qubit--unit"></a>op： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单元](xref:microsoft.quantum.lang-ref.unit) 

要应用到 subregister 的操作。


### <a name="idxs--int"></a>idxs： [Int](xref:microsoft.quantum.lang-ref.int)[]

索引数组，指示将应用操作的 qubits。


### <a name="target--qubit"></a>target： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

注册操作所针对的。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>另请参阅

- [Canon. ApplyToSubregisterA](xref:Microsoft.Quantum.Canon.ApplyToSubregisterA)
- [Canon. ApplyToSubregisterC](xref:Microsoft.Quantum.Canon.ApplyToSubregisterC)
- [Canon. ApplyToSubregisterCA](xref:Microsoft.Quantum.Canon.ApplyToSubregisterCA)