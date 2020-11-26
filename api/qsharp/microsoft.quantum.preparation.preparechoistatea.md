---
uid: Microsoft.Quantum.Preparation.PrepareChoiStateA
title: PrepareChoiStateA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiStateA
qsharp.summary: Prepares the Choi–Jamiołkowski state for a given operation with an adjoint variant onto given reference and target registers.
ms.openlocfilehash: 59d47a549a6e2a208906b79504ea93bd9ebaabd7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96230117"
---
# <a name="preparechoistatea-operation"></a>PrepareChoiStateA 操作

命名空间： [Microsoft 量子. 准备](xref:Microsoft.Quantum.Preparation)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


准备具有 adjoint 变体的给定操作的 Choi – Jamiołkowski 状态到给定引用和目标寄存器。

```qsharp
operation PrepareChoiStateA (op : (Qubit[] => Unit is Adj), reference : Qubit[], target : Qubit[]) : Unit is Adj
```


## <a name="input"></a>输入

### <a name="op--qubit--unit--is-adj"></a>op： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词




### <a name="reference--qubit"></a>参考： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]




### <a name="target--qubit"></a>target： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]





## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>另请参阅

- [PrepareChoiState。](xref:Microsoft.Quantum.Preparation.PrepareChoiState)