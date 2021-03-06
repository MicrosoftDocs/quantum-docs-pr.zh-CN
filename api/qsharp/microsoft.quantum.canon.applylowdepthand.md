---
uid: Microsoft.Quantum.Canon.ApplyLowDepthAnd
title: ApplyLowDepthAnd 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyLowDepthAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, with T-depth 1, using measurement to perform the adjoint operation.
ms.openlocfilehash: 7fa9d9bf2f1905bf1b59e783d7bceb8cb2e09fa4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841711"
---
# <a name="applylowdepthand-operation"></a>ApplyLowDepthAnd 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


当且仅当两个 control qubits 都处于1状态时，使用 qubit 执行 adjoint 操作时，使用度量来反转给定目标。

```qsharp
operation ApplyLowDepthAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>说明

`target`当且仅当这两个控件都为1，但假定 `target` 处于状态0时，则反转。  操作具有 T 计数4、T 深度1和需要一个 helper qubit，因此，如果已知为0，则可能更适合 CCNOT 操作 `target` 。  此操作的 adjoint 是基于度量的，不需要任何 T 入口，也不需要 helper qubit。

## <a name="input"></a>输入

### <a name="control1--qubit"></a>control1： [Qubit](xref:microsoft.quantum.lang-ref.qubit)

第一个控件 qubit


### <a name="control2--qubit"></a>control2： [Qubit](xref:microsoft.quantum.lang-ref.qubit)

第二个控件 qubit


### <a name="target--qubit"></a>目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)

目标辅助 qubit;必须处于状态0



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>参考

- Cody： "容错 Toffoli 入口的 Novel 构造"，Phys. A 87，022328，2013 [arXiv： 1212.5069](https://arxiv.org/abs/1212.5069) doi>10.1145： 10.1103/PhysRevA 87.022328
- Peter Selinger： "T 深一条的量子线路"，Phys，87，042302，2013 [arXiv： 1210.0974](https://arxiv.org/abs/1210.0974) doi>10.1145： 10.1103/PhysRevA 87.042302