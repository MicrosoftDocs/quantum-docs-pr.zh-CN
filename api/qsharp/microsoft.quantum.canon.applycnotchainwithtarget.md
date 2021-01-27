---
uid: Microsoft.Quantum.Canon.ApplyCNOTChainWithTarget
title: ApplyCNOTChainWithTarget 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCNOTChainWithTarget
qsharp.summary: Computes the parity of an array of qubits into a target qubit.
ms.openlocfilehash: ba1a4e99c411a4718b5a09fdcd57a7239eb4dbd6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845121"
---
# <a name="applycnotchainwithtarget-operation"></a>ApplyCNOTChainWithTarget 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


计算 qubits 数组到目标 qubit 的奇偶校验。

```qsharp
operation ApplyCNOTChainWithTarget (qubits : Qubit[], targetQubit : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>说明

如果数组最初处于状态 $ \ket{q_0} \ket{q_1} \cdots \ket{q_ {\text{target}}} $，则最终状态由 $ \ket{q_0} \ket{q_1 \oplus q_0} \cdots \ket{q_ {n-1} \oplus \cdots \oplus q_0 \oplus q_ {\text{target}}} $。

## <a name="input"></a>输入

### <a name="qubits--qubit"></a>qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

计算其奇偶校验的 qubits 数组。


### <a name="targetqubit--qubit"></a>targetQubit： [Qubit](xref:microsoft.quantum.lang-ref.qubit)

"Qubits" 的奇偶校验的最终 qubit 为 XORed。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>备注

以下项是等效的：

```qsharp
ApplyCNOTChainWithTarget(Most(qs), Last(qs));
```

和

```qsharp
ApplyCNOTChain(qs);
```