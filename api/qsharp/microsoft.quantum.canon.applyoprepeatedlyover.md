---
uid: Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver
title: ApplyOpRepeatedlyOver 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyOpRepeatedlyOver
qsharp.summary: Applies the same op over a qubit register multiple times.
ms.openlocfilehash: 263eff8ec31f5ee36485eb1d2ed52bf15cef4bef
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844801"
---
# <a name="applyoprepeatedlyover-operation"></a>ApplyOpRepeatedlyOver 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


多次对 qubit 寄存器应用相同的操作。

```qsharp
operation ApplyOpRepeatedlyOver (op : (Qubit[] => Unit), targets : Int[][], register : Qubit[]) : Unit
```


## <a name="input"></a>输入

### <a name="op--qubit--unit"></a>op： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单元](xref:microsoft.quantum.lang-ref.unit) 

要在 qubit 寄存器上多次应用的操作


### <a name="targets--int"></a>目标： [Int](xref:microsoft.quantum.lang-ref.int)[] []

描述 op 目标的嵌套数组。 每个数组都应包含一个整数列表，其中包含描述要使用的 qubits 的整数。


### <a name="register--qubit"></a>register： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

要对其进行操作的 Qubit 寄存器。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>另请参阅

- [Canon. ApplySeriesOfOps](xref:Microsoft.Quantum.Canon.ApplySeriesOfOps)