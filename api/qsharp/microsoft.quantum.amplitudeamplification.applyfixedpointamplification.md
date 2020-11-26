---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyFixedPointAmplification
title: ApplyFixedPointAmplification 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyFixedPointAmplification
qsharp.summary: Fixed-Point Amplitude Amplification algorithm
ms.openlocfilehash: 13e70b1ebd5e3bf0996e6a76f4bffe57ca2d2250
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96191527"
---
# <a name="applyfixedpointamplification-operation"></a>ApplyFixedPointAmplification 操作

命名空间： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


Fixed-Point 振幅放大算法

```qsharp
operation ApplyFixedPointAmplification (statePrepOracle : Microsoft.Quantum.Oracles.StateOracle, startQubits : Qubit[]) : Unit
```


## <a name="input"></a>输入

### <a name="statepreporacle--stateoracle"></a>statePrepOracle： [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)

准备开始状态的单一 oracle。


### <a name="startqubits--qubit"></a>startQubits： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit 注册



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>备注

StartQubits 必须处于 $ \ket{0 \cdots 0} $ 状态。 此操作将循环访问多个查询，以 $2 $ 的幂来循环访问，直到达到最大数量的查询或找到目标状态。