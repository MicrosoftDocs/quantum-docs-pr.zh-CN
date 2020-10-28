---
uid: Microsoft.Quantum.Preparation.PrepareEntangledState
title: PrepareEntangledState 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareEntangledState
qsharp.summary: >-
  Pairwise entangles two qubit registers.

  That is, given two registers, prepares the maximally entangled state $\frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right)$ between each pair of qubits on the respective registers, assuming that each register starts in the $\ket{0\cdots 0}$ state.
ms.openlocfilehash: 299d586f7581acdecf22da2f6bbfbb8d45f372f3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700196"
---
# <a name="prepareentangledstate-operation"></a>PrepareEntangledState 操作

命名空间： [Microsoft 量子. 准备](xref:Microsoft.Quantum.Preparation)

软件包 [](https://nuget.org/packages/)


成对 entangles 两个 qubit 寄存器。

也就是说，假设有两个寄存器，则准备最大化放大 state $ \frac {1} {\sqrt {2} } \left ( \ket {00} + \ket \right 在 {11} 各自寄存器上的每对 qubits 之间) $，假设每个注册都以 $ \ket{0\cdots 0} $ 状态启动。

```qsharp
operation PrepareEntangledState (left : Qubit[], right : Qubit[]) : Unit
```


## <a name="input"></a>输入

### <a name="left--qubit"></a>left： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

$ \Ket{0\cdots 0} $ 状态中的 qubit 数组


### <a name="right--qubit"></a>right： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

$ \Ket{0\cdots 0} $ 状态中的 qubit 数组



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)

