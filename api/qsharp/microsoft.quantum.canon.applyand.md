---
uid: Microsoft.Quantum.Canon.ApplyAnd
title: 现在操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyAnd
qsharp.summary: Inverts a given target qubit if and only if both control qubits are in the 1 state, using measurement to perform the adjoint operation.
ms.openlocfilehash: 39ffb9c598b6345c0d63c0c0d9705d84e101cc47
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845187"
---
# <a name="applyand-operation"></a>现在操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


当且仅当两个控件 qubits 都处于1状态时，使用度量来执行 adjoint 操作，以反转给定的目标 qubit。

```qsharp
operation ApplyAnd (control1 : Qubit, control2 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>说明

`target`当且仅当这两个控件都为1，但假定 `target` 处于状态0时，则反转。  操作具有 T 计数4、T 深度2和不需要 helper qubit，因此，如果已知为0，则可能更适合 CCNOT 操作 `target` 。  此操作的 adjoint 是基于度量的，不需要任何 T 入口。

此操作的受控应用程序不需要 helper qubit、 `2^c` `Rz` 入口和未进行深度优化，其中 `c` 是包括操作中两个控件的总体控制 qubits 的数目 `ApplyAnd` 。  Adjoint 控制的应用程序要求 `2^c - 1` `Rz` 入口 (两个角度，) 非 adjoint 操作大小的两倍，无帮助器 qubit，不是深度优化。

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
- Craig Gidney： "一半的量程增加成本"，量子2，page 74，2018 [arXiv： 1709.06648](https://arxiv.org/abs/1709.06648) doi>10.1145： 10.1103/PhysRevA. 85.044302
- Mathias Soeken： "量子 Oracle 线路和圣诞节树模式"， [博客文章2019年12月19日](https://msoeken.github.io/blog_qac.html) (注意：说明了多受控构造) 