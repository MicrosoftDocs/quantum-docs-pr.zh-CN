---
uid: Microsoft.Quantum.Diagnostics.DumpOperation
title: DumpOperation 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpOperation
qsharp.summary: Given an operation, displays diagnostics about the operation that are made available by the current execution target.
ms.openlocfilehash: cde188806506c586c4c77a7f9b2b43ad0e10ef1b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829283"
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



## <a name="example"></a>示例

当在量程模拟器目标上运行时，以下代码片段会将矩阵 $ $ \begin{aligned} \left ( \begin{matrix} 1 & 0 & 0 & 0 0 & 0 & 0 & \\ \\ 1 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \end{matrix}\right) \end{aligned}。
$$

```qsharp
operation DumpCnot() : Unit {
    DumpOperation(2, ApplyToFirstTwoQubitsCA(CNOT, _));
}
```

## <a name="remarks"></a>备注

调用此操作在 Q # 内没有明显的效果。 显示的确切诊断（如果有）依赖于当前的执行目标和编辑器环境。
例如，在全状态量程模拟器上使用时，会显示一个用于表示的单一矩阵 `op` 。

请注意，当在可接受全局阶段歧义的模拟器上运行时 (例如：全状态模拟器) ，返回的表示形式可能会因全局阶段而异。

同样，根据支持此操作的每个模拟器使用的约定，行和列的排序顺序也可能有所不同。