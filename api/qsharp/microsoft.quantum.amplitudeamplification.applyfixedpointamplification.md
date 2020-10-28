---
uid: Microsoft.Quantum.AmplitudeAmplification.ApplyFixedPointAmplification
title: ApplyFixedPointAmplification 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: ApplyFixedPointAmplification
qsharp.summary: Fixed-Point Amplitude Amplification algorithm
ms.openlocfilehash: f506be7b2e3f65cf89694e30d79c04ec30d25035
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700120"
---
# <a name="applyfixedpointamplification-operation"></a>ApplyFixedPointAmplification 操作

命名空间： [AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

软件包 [](https://nuget.org/packages/)


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



## <a name="remarks"></a>注解

StartQubits 必须处于 $ \ket{0 \cdots 0} $ 状态。 此操作将循环访问多个查询，以 $2 $ 的幂来循环访问，直到达到最大数量的查询或找到目标状态。