---
uid: Microsoft.Quantum.Measurement.SetToBasisState
title: SetToBasisState 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Measurement
qsharp.name: SetToBasisState
qsharp.summary: Sets a qubit to a given computational basis state by measuring the qubit and applying a bit flip if needed.
ms.openlocfilehash: bb40ddcf6518a30f5d88eec21cf8e2c2d6e0bbaf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700909"
---
# <a name="settobasisstate-operation"></a>SetToBasisState 操作

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Measurement)

软件包 [](https://nuget.org/packages/)


通过测量 qubit 并在需要时应用位翻转，将 qubit 设置为给定的计算基础状态。

```qsharp
operation SetToBasisState (desired : Result, target : Qubit) : Unit
```


## <a name="input"></a>输入

### <a name="desired--__invalidresult__"></a>desired： __无效 <Result>__

应将 qubit 设置为的基本状态。


### <a name="target--qubit"></a>目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)

要设置其状态的 qubit。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>注解

作为此操作的固定条件， `M(q)` `SetToBasisState(result, q)` 将返回之后立即调用 `result` 。