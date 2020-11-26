---
uid: Microsoft.Quantum.Simulation.IntToPauli
title: IntToPauli 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntToPauli
qsharp.summary: Converts a integer to a single-qubit Pauli operator.
ms.openlocfilehash: 18edb600f7b5b33c7ad98e78e32903c570082225
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229199"
---
# <a name="inttopauli-function"></a>IntToPauli 函数

命名空间 [：](xref:Microsoft.Quantum.Simulation)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


将整数转换为 qubit Pauli 运算符。

```qsharp
function IntToPauli (idx : Int) : Pauli
```


## <a name="input"></a>输入

### <a name="idx--int"></a>idx： [Int](xref:microsoft.quantum.lang-ref.int)

`0..3`要转换为 Pauli 运算符的范围内的整数。



## <a name="output--pauli"></a>输出： [Pauli](xref:microsoft.quantum.lang-ref.pauli)

`Pauli`给定的运算符 `[PauliI, PauliX, PauliY, PauliZ][idx]` 。