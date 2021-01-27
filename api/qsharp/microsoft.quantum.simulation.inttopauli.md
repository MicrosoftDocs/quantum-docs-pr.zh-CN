---
uid: Microsoft.Quantum.Simulation.IntToPauli
title: IntToPauli 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntToPauli
qsharp.summary: Converts a integer to a single-qubit Pauli operator.
ms.openlocfilehash: 76f482b86ff4a27b6e6ce6ae4ec3d59422563f12
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842251"
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