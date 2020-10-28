---
uid: Microsoft.Quantum.Simulation.IntToPauli
title: IntToPauli 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntToPauli
qsharp.summary: Converts a integer to a single-qubit Pauli operator.
ms.openlocfilehash: f0f1186f14a0dc30bb34bd29f148cdc830fd1337
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700960"
---
# <a name="inttopauli-function"></a>IntToPauli 函数

命名空间 [：](xref:Microsoft.Quantum.Simulation)

软件包 [](https://nuget.org/packages/)


将整数转换为 qubit Pauli 运算符。

```qsharp
function IntToPauli (idx : Int) : Pauli
```


## <a name="input"></a>输入

### <a name="idx--int"></a>idx： [Int](xref:microsoft.quantum.lang-ref.int)

`0..3`要转换为 Pauli 运算符的范围内的整数。



## <a name="output--pauli"></a>输出： [Pauli](xref:microsoft.quantum.lang-ref.pauli)

`Pauli`给定的运算符 `[PauliI, PauliX, PauliY, PauliZ][idx]` 。