---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced
title: AssertOperationsEqualReferenced 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualReferenced
qsharp.summary: >-
  Given two operations, asserts that they act identically for all input states.

  This assertion is implemented by using the Choi–Jamiołkowski isomorphism to reduce the assertion to one of a qubit state assertion on two entangled registers. Thus, this operation needs only a single call to each operation being tested, but requires twice as many qubits to be allocated. This assertion can be used to ensure, for instance, that an optimized version of an operation acts identically to its naïve implementation, or that an operation which acts on a range of non-quantum inputs agrees with known cases.
ms.openlocfilehash: 59c0fa72c9ca8f3bc512b6ed674fd73babc57f84
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202305"
---
# <a name="assertoperationsequalreferenced-operation"></a>AssertOperationsEqualReferenced 操作

命名空间 [：](xref:Microsoft.Quantum.Diagnostics)

包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


假设有两个运算，则断言它们对于所有输入状态都是相同的。

通过使用 Choi – Jamiołkowski isomorphism 将断言降低到两个放大寄存器上的某个 qubit 状态断言，实现此断言。
因此，此操作只需对正在测试的每个操作进行一次调用，而需要分配两个要分配的 qubits。
例如，可以使用这种断言来确保操作的优化版本与其简单的实现完全相同，或者对非量程输入进行操作的操作与已知情况有关。

```qsharp
operation AssertOperationsEqualReferenced (nQubits : Int, actual : (Qubit[] => Unit), expected : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a>输入

### <a name="nqubits--int"></a>nQubits： [Int](xref:microsoft.quantum.lang-ref.int)

要传递给每个操作的 qubits 数。


### <a name="actual--qubit--unit"></a>实际： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单元](xref:microsoft.quantum.lang-ref.unit) 

要测试的操作。


### <a name="expected--qubit--unit--is-adj"></a>应为： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词

定义要测试的操作的预期行为的操作。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>备注

此操作要求对预期行为进行建模的操作为 adjointable，以便可以在目标寄存器上单独执行相反的操作。
正式，可以指定换位操作，该操作放宽此要求，但换位操作并不是对任意量程操作以物理 realizable 的形式进行的，因此不作为选项包含在此处。