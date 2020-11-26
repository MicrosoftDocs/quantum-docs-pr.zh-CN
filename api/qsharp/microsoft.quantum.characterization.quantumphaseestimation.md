---
uid: Microsoft.Quantum.Characterization.QuantumPhaseEstimation
title: QuantumPhaseEstimation 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: QuantumPhaseEstimation
qsharp.summary: Performs the quantum phase estimation algorithm for a given oracle `U` and `targetState`, reading the phase into a big-endian quantum register.
ms.openlocfilehash: 14ba3e012f6561e7089f9fe59b2a13516b211d51
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204209"
---
# <a name="quantumphaseestimation-operation"></a>QuantumPhaseEstimation 操作

命名空间 [：](xref:Microsoft.Quantum.Characterization)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


执行给定 oracle 和的量程阶段估算算法 `U` ，并将 `targetState` 该阶段读入大字节序量程寄存器。

```qsharp
operation QuantumPhaseEstimation (oracle : Microsoft.Quantum.Oracles.DiscreteOracle, targetState : Qubit[], controlRegister : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>输入

### <a name="oracle--discreteoracle"></a>oracle： [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

为给定整数幂 m 实现 $U ^ m $ 的操作。


### <a name="targetstate--qubit"></a>targetState： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

表示状态 $ \ket{\phi} $ 的量程寄存器 $U $。 如果 $ \ket{\phi} $ 是 $U $ 的 eigenstate，$U \ket{\phi} = e ^ {i\phi} \ket{\phi} $ for $ \phi \in [0，2 \ pi) $ 未知阶段。


### <a name="controlregister--bigendian"></a>controlRegister： [BigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)

大字节序表示形式整数寄存器，可用于控制提供的 oracle，并在应用程序中包含 $ \phi $ 的表示形式。 假定 controlRegister 在初始状态 $ \ket{00\cdots 0} $ 下启动，其中寄存器的长度指示所需的精度。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)

