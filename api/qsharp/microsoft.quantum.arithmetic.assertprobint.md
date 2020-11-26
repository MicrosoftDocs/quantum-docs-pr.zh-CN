---
uid: Microsoft.Quantum.Arithmetic.AssertProbInt
title: AssertProbInt 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AssertProbInt
qsharp.summary: Asserts that the probability of a specific state of a quantum register has the expected value.
ms.openlocfilehash: b95c2c6294dd5a95b7215c22bd6c50a41635f432
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223691"
---
# <a name="assertprobint-operation"></a>AssertProbInt 操作

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


断言量程寄存器的特定状态的概率具有预期值。

```qsharp
operation AssertProbInt (stateIndex : Int, expected : Double, qubits : Microsoft.Quantum.Arithmetic.LittleEndian, tolerance : Double) : Unit
```


## <a name="description"></a>描述

如果给定 $n $-qubit 量程状态 $ \ket{\psi} = \sum ^ {2 ^ n-1} _ {j = 0} \ alpha_j \ket{j} $，则断言 $ $j 索引的状态 $ \ket{j} $ 的概率 $ | \ alpha_j | ^ 2 $ 具有预期值。

## <a name="input"></a>输入

### <a name="stateindex--int"></a>stateIndex： [Int](xref:microsoft.quantum.lang-ref.int)

由寄存器表示的状态 $ \ket{j} $ 的索引 $j $ `LittleEndian` 。


### <a name="expected--double"></a>应为： [Double](xref:microsoft.quantum.lang-ref.double)

$ | \ Alpha_j | ^ 2 $ 的预期值。


### <a name="qubits--littleendian"></a>qubits： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

以小字节序格式存储 $ \ket{\psi} $ 的 qubit 寄存器。


### <a name="tolerance--double"></a>容差： [Double](xref:microsoft.quantum.lang-ref.double)

实际值与预期值的绝对容差。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)

