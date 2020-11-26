---
uid: Microsoft.Quantum.Diagnostics.AssertOperationsEqualInPlace
title: AssertOperationsEqualInPlace 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertOperationsEqualInPlace
qsharp.summary: >-
  Given two operations, asserts that they act identically for all input states.

  This assertion is implemented by checking the action of the operations on all states of the form $V_0 \otimes ... \otimes V_{n-1}$, where $V_k$ is one of the states $\ket{0}$, $\ket{1}$, $\ket{+}$ and $\ket{i}$ (+1 eigenstate of Pauli Y operator).

  This assertion uses $n$ qubits and requires multiple calls of the operations being compared.
ms.openlocfilehash: 9b17bac9d95baf5a542604892c64130bf35d7f69
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202424"
---
# <a name="assertoperationsequalinplace-operation"></a>AssertOperationsEqualInPlace 操作

命名空间 [：](xref:Microsoft.Quantum.Diagnostics)

包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


假设有两个运算，则断言它们对于所有输入状态都是相同的。

此断言是通过以下方式实现的：检查所有状态的操作的操作： $V _0 \otimes ... \otimes V_ {n-1} $，其中 $V _k $ 是状态 $ \ket {0} $，$ \ket $ {1} ，$ \ket{+} $，$ \ket{i} $ (+ 1 Eigenstate Of Pauli Y operator) 。

此断言使用 $n $ qubits，需要对要比较的操作进行多次调用。

```qsharp
operation AssertOperationsEqualInPlace (nQubits : Int, givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a>输入

### <a name="nqubits--int"></a>nQubits： [Int](xref:microsoft.quantum.lang-ref.int)

操作和操作 $n $ 的 qubits 的数目 `givenU` `expectedU` 。


### <a name="givenu--qubit--unit"></a>givenU： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单元](xref:microsoft.quantum.lang-ref.unit) 

要检查 $n $ qubits 上的操作。


### <a name="expectedu--qubit--unit--is-adj"></a>expectedU： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词

要与进行比较 $n $ qubits 上的引用操作 `givenU` 。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>参考

状态 $ \ket {0} $、$ \ket {1} $、$ \ket{+} $ 和 $ \ket{i} $ 是 Chuang-Nielsen 的基础，如中所述 [ *I. L. Chuang, M. A. Nielsen*](https://arxiv.org/abs/quant-ph/9610001)。

## <a name="see-also"></a>另请参阅

- [AssertOperationsEqualReferenced。](xref:Microsoft.Quantum.Diagnostics.AssertOperationsEqualReferenced)