---
uid: Microsoft.Quantum.Preparation.PrepareChoiState
title: PrepareChoiState 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiState
qsharp.summary: Prepares the Choi–Jamiołkowski state for a given operation onto given reference and target registers.
ms.openlocfilehash: ced71c4278f42f577760acd54ae53e7f5e6dae4a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210567"
---
# <a name="preparechoistate-operation"></a>PrepareChoiState 操作

命名空间： [Microsoft 量子. 准备](xref:Microsoft.Quantum.Preparation)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


将给定操作的 Choi – Jamiołkowski 状态准备到给定的引用和目标寄存器。

```qsharp
operation PrepareChoiState (op : (Qubit[] => Unit), reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a>输入

### <a name="op--qubit--unit"></a>op： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单元](xref:microsoft.quantum.lang-ref.unit) 

操作 $ \Lambda $，其 Choi – Jamiołkowski 状态 $J ( \Lambda) /2 ^ N $ 准备好，其中 $N $ 是其作用的 qubits 的数目 `op` 。


### <a name="reference--qubit"></a>参考： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

以 $ \ket{00\cdots 0} $ 状态开头的 qubits 的寄存器，将用作操作的引用 `op` 。


### <a name="target--qubit"></a>target： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

最初在 $ \ket{00\cdots 0} $ 状态的 qubits 的寄存器，将应用该状态 `op` 。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>备注

Choi – Jamiłkowski 状态 $J 量程进程的 ( \Lambda) $ 定义为 $ $ \begin{align} J ( \Lambda) \mathrel{： =} ( \boldone \otimes \Lambda)  (| \boldone\rangle \! \rangle\langle \! \langle\boldone |) ，\end{align} $ $ where $ |X\rangle \! \rangle $ 是列堆栈约定中的矩阵 $X $ 的 *矢量化* 。 了解此状态的传统说明会提供有关 $ \Lambda $ 对任意输入状态的影响的完整信息，并构成 *量程进程 tomography* 的基础。

## <a name="see-also"></a>另请参阅

- [PrepareChoiStateA。](xref:Microsoft.Quantum.Preparation.PrepareChoiStateA)
- [PrepareChoiStateC。](xref:Microsoft.Quantum.Preparation.PrepareChoiStateC)
- [PrepareChoiStateCA。](xref:Microsoft.Quantum.Preparation.PrepareChoiStateCA)