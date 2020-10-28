---
uid: Microsoft.Quantum.Canon.ApplyCNOTChainWithTarget
title: ApplyCNOTChainWithTarget 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyCNOTChainWithTarget
qsharp.summary: Computes the parity of an array of qubits into a target qubit.
ms.openlocfilehash: fd0a0f3e1db89946aec2c63f3cde7a021608eea5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696371"
---
# <a name="applycnotchainwithtarget-operation"></a>ApplyCNOTChainWithTarget 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

软件包 [](https://nuget.org/packages/)


计算 qubits 数组到目标 qubit 的奇偶校验。

```qsharp
operation ApplyCNOTChainWithTarget (qubits : Qubit[], targetQubit : Qubit) : Unit
```


## <a name="description"></a>说明

如果数组最初处于状态 $ \ket{q_0} \ket{q_1} \cdots \ket{q_ {\text{target}}} $，则最终状态由 $ \ket{q_0} \ket{q_1 \oplus q_0} \cdots \ket{q_ {n-1} \oplus \cdots \oplus q_0 \oplus q_ {\text{target}}} $。

## <a name="input"></a>输入

### <a name="qubits--qubit"></a>qubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

计算其奇偶校验的 qubits 数组。


### <a name="targetqubit--qubit"></a>targetQubit： [Qubit](xref:microsoft.quantum.lang-ref.qubit)

"Qubits" 的奇偶校验的最终 qubit 为 XORed。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>注解

以下项是等效的：

```qsharp
ApplyCNOTChainWithTarget(Most(qs), Last(qs));
```

和

```qsharp
ApplyCNOTChain(qs);
```