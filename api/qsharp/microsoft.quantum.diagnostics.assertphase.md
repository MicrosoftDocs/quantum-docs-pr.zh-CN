---
uid: Microsoft.Quantum.Diagnostics.AssertPhase
title: AssertPhase 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertPhase
qsharp.summary: Asserts that the phase of an equal superposition state has the expected value.
ms.openlocfilehash: 59fa0f2f68b4de271b972aef776ee5097fd5c201
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830084"
---
# <a name="assertphase-operation"></a>AssertPhase 操作

命名空间 [：](xref:Microsoft.Quantum.Diagnostics)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


断言 superposition 状态相同的阶段具有预期值。

```qsharp
operation AssertPhase (expected : Double, qubit : Qubit, tolerance : Double) : Unit
```


## <a name="description"></a>说明

此操作断言对于一些任意实 $t $，可以表示为 $ \frac{e ^ {i t}} {\sqrt {2} } (e ^ {i\phi} \ 票证 {0} + e ^ {-i\phi} \ 票证) $ 的阶段 $ \phi $ {1} 具有预期值。

## <a name="input"></a>输入

### <a name="expected--double"></a>应为： [Double](xref:microsoft.quantum.lang-ref.double)

$ \Phi \in 的预期值 (-\pi，\pi] $。


### <a name="qubit--qubit"></a>qubit： [qubit](xref:microsoft.quantum.lang-ref.qubit)

存储预期状态的 qubit。


### <a name="tolerance--double"></a>容差： [Double](xref:microsoft.quantum.lang-ref.double)

实际值与预期值的绝对容差。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>示例

以下断言成功： `qubit` 处于状态 $ \ket{\psi} = e ^ {i 0.5} \ sqrt {1/2} \ 票证 {0} + e ^ {i 0.5} \ sqrt {1/2} \ 票证 {1} $;

- `AssertPhase(0.0,qubit,10e-10);`

`qubit` 处于状态 $ \ket{\psi} = e ^ {i 0.5} \ sqrt {1/2} \ 票证 {0} + e ^ {-i 0.5} \ sqrt {1/2} \ 票证 {1} $;

- `AssertPhase(0.5,qubit,10e-10);`

`qubit` 处于状态 $ \ket{\psi} = e ^ {-i 2.2} \ sqrt {1/2} \ 票证 {0} + e ^ {i 0.2} \ sqrt {1/2} \ 票证 {1} $;

- `AssertPhase(-1.2,qubit,10e-10);`