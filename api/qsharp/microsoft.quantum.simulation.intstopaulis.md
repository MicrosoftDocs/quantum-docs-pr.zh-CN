---
uid: Microsoft.Quantum.Simulation.IntsToPaulis
title: IntsToPaulis 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IntsToPaulis
qsharp.summary: Converts an array of integers to an array of single-qubit Pauli operators.
ms.openlocfilehash: 605257aa7ca39e457127e3c3459b5891145b1863
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695094"
---
# <a name="intstopaulis-function"></a>IntsToPaulis 函数

命名空间 [：](xref:Microsoft.Quantum.Simulation)

软件包 [](https://nuget.org/packages/)


将整数数组转换为 qubit Pauli 运算符的数组。

```qsharp
function IntsToPaulis (ints : Int[]) : Pauli[]
```


## <a name="input"></a>输入

### <a name="ints--int"></a>整数： [Int](xref:microsoft.quantum.lang-ref.int)[]

要转换为 Pauli 运算符的范围内的整数数组 `0..3`  。



## <a name="output--pauli"></a>Output： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

`paulis`Pauli 运算符的数组 `Pauli[]` ，其长度与给定的的 `ints` `paulis[idxPauli]` 元素相等 `[PauliI, PauliX, PauliY, PauliZ]` `ints[idxPauli]` 。