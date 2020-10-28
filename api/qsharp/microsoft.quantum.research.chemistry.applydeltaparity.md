---
uid: Microsoft.Quantum.Research.Chemistry.ApplyDeltaParity
title: ApplyDeltaParity 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: ApplyDeltaParity
qsharp.summary: Computes difference in parity between a previous PQRS... terms and the next PQRS... term. This difference is computed on a auxiliary qubit.
ms.openlocfilehash: bb01eb684ff1820be08a573c0ca6cfc12efeb889
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700712"
---
# <a name="applydeltaparity-operation"></a>ApplyDeltaParity 操作

命名空间： [...](xref:Microsoft.Quantum.Research.Chemistry)

软件包 [](https://nuget.org/packages/)


计算上一个 PQRS 之间的奇偶校验差异条款和下一 PQRS二项式. 这种差异是在辅助 qubit 上计算的。

```qsharp
operation ApplyDeltaParity (prevFermionicTerm : Int[], nextFermionicTerm : Int[], aux : Qubit, qubits : Qubit[]) : Unit
```


## <a name="input"></a>输入

### <a name="prevfermionicterm--int"></a>prevFermionicTerm： [Int](xref:microsoft.quantum.lang-ref.int)[]

上一个 PQRS 的索引列表 .。。规定.


### <a name="nextfermionicterm--int"></a>nextFermionicTerm： [Int](xref:microsoft.quantum.lang-ref.int)[]

下一个 PQRS 的索引列表 .。。规定.


### <a name="aux--qubit"></a>aux： [Qubit](xref:microsoft.quantum.lang-ref.qubit)

辅助 qubit 将存储奇偶校验计算结果。


### <a name="qubits--qubit"></a>qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit 由所有 PQRS 进行操作 .。。规定.



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>注解

这假设 P < Q < R < S 的索引 < .。。适用于 prevPQ 和 nextPQ。