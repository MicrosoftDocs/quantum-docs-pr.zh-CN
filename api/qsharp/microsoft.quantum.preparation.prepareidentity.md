---
uid: Microsoft.Quantum.Preparation.PrepareIdentity
title: PrepareIdentity 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareIdentity
qsharp.summary: >-
  Given a register, prepares that register in the maximally mixed state.

  The register is prepared in the $\boldone / 2^N$ state by applying the complete depolarizing channel to each qubit, where $N$ is the length of the register.
ms.openlocfilehash: a3f96fbdafb19c90fb2b563243600cca60841566
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700972"
---
# <a name="prepareidentity-operation"></a>PrepareIdentity 操作

命名空间： [Microsoft 量子. 准备](xref:Microsoft.Quantum.Preparation)

软件包 [](https://nuget.org/packages/)


在给定寄存器的情况下，准备在最大化 mixed 状态下进行注册。

在 $ \boldone/2 ^ N $ 状态下注册注册，方法是将完整的 depolarizing 通道应用于每个 qubit，其中 $N $ 是寄存器的长度。

```qsharp
operation PrepareIdentity (register : Qubit[]) : Unit
```


## <a name="input"></a>输入

### <a name="register--qubit"></a>register： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

其状态为 depolarized 的寄存器。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>另请参阅

- [PrepareSingleQubitIdentity。](xref:Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity)