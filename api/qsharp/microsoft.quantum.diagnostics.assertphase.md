---
uid: Microsoft.Quantum.Diagnostics.AssertPhase
title: AssertPhase 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertPhase
qsharp.summary: Asserts that the phase of an equal superposition state has the expected value.
ms.openlocfilehash: 9130d6c735d90abbc51989ef4a68a8eff8b41371
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202254"
---
# <a name="assertphase-operation"></a>AssertPhase 操作

命名空间 [：](xref:Microsoft.Quantum.Diagnostics)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


断言 superposition 状态相同的阶段具有预期值。

```qsharp
operation AssertPhase (expected : Double, qubit : Qubit, tolerance : Double) : Unit
```


## <a name="description"></a>描述

此操作断言对于一些任意实 $t $，可以表示为 $ \frac{e ^ {i t}} {\sqrt {2} } (e ^ {i\phi} \ 票证 {0} + e ^ {-i\phi} \ 票证) $ 的阶段 $ \phi $ {1} 具有预期值。

## <a name="input"></a>输入

### <a name="expected--double"></a>应为： [Double](xref:microsoft.quantum.lang-ref.double)

$ \Phi \in 的预期值 (-\pi，\pi] $。


### <a name="qubit--qubit"></a>qubit： [qubit](xref:microsoft.quantum.lang-ref.qubit)

存储预期状态的 qubit。


### <a name="tolerance--double"></a>容差： [Double](xref:microsoft.quantum.lang-ref.double)

实际值与预期值的绝对容差。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)

