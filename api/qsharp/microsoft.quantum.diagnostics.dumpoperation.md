---
uid: Microsoft.Quantum.Diagnostics.DumpOperation
title: DumpOperation 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpOperation
qsharp.summary: Given an operation, displays diagnostics about the operation that are made available by the current execution target.
ms.openlocfilehash: b0e07173ddbeb8a96d4a85928258b6e30deb394d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202050"
---
# <a name="dumpoperation-operation"></a>DumpOperation 操作

命名空间 [：](xref:Microsoft.Quantum.Diagnostics)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


在给定操作的情况下，显示有关当前执行目标可用的操作的诊断。

```qsharp
operation DumpOperation (nQubits : Int, op : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a>输入

### <a name="nqubits--int"></a>nQubits： [Int](xref:microsoft.quantum.lang-ref.int)

给定操作对其起作用的 qubits 的数目。


### <a name="op--qubit--unit--is-adj"></a>op： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词

要诊断的操作。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>备注

调用此操作在 Q # 内没有明显的效果。 显示的确切诊断（如果有）依赖于当前的执行目标和编辑器环境。
例如，在全状态量程模拟器上使用时，会显示一个用于表示的单一矩阵 `op` 。

请注意，当在可接受全局阶段歧义的模拟器上运行时 (例如：全状态模拟器) ，返回的表示形式可能会因全局阶段而异。

同样，根据支持此操作的每个模拟器使用的约定，行和列的排序顺序也可能有所不同。