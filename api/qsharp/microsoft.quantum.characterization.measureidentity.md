---
uid: Microsoft.Quantum.Characterization.MeasureIdentity
title: MeasureIdentity 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: MeasureIdentity
qsharp.summary: Measures the identity operator on a register of qubits.
ms.openlocfilehash: 71a103fddb3a27703318975bea94bc7a22a9ce81
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695882"
---
# <a name="measureidentity-operation"></a>MeasureIdentity 操作

命名空间 [：](xref:Microsoft.Quantum.Characterization)

软件包 [](https://nuget.org/packages/)


测量 qubits 的寄存器上的标识运算符。

```qsharp
operation MeasureIdentity (register : Qubit[]) : Result
```


## <a name="input"></a>输入

### <a name="register--qubit"></a>register： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

要测量的寄存器。



## <a name="output--__invalidresult__"></a>输出： __无效 <Result>__

结果值 `Zero` 。

## <a name="remarks"></a>注解

由于 $ \boldone $ 只有 eigenvalue $1 $，并且没有负 eigenvalue，此操作始终返回 `Zero` ，对应于 eigenvalue $ + 1 = (-1) ^ $0，而不会导致的状态折叠 `register` 。

此操作本身并不有用，但在进程 tomography 的上下文中很有用，因为它提供了有关量程进程的跟踪保存的信息。
特别是，具有有损度量的目标计算机应将此操作替换为 $ \boldone $ 的实际度量值。