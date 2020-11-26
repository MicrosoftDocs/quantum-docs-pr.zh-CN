---
uid: Microsoft.Quantum.Canon.EmbedPauli
title: EmbedPauli 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: EmbedPauli
qsharp.summary: Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.
ms.openlocfilehash: e9042ca9eac4b8791057037dc5698eb14deadd31
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207031"
---
# <a name="embedpauli-function"></a>EmbedPauli 函数

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


给定 qubit Pauli 运算符和 qubit 的索引后，将返回一个多 qubit Pauli 运算符，该运算符具有给定的单一 qubit 运算符，位于该索引处和 `PauliI` 其他每个索引处。

```qsharp
function EmbedPauli (pauli : Pauli, location : Int, n : Int) : Pauli[]
```


## <a name="input"></a>输入

### <a name="pauli--pauli"></a>pauli： [pauli](xref:microsoft.quantum.lang-ref.pauli)

要放在给定位置的 qubit Pauli 运算符。


### <a name="location--int"></a>位置： [Int](xref:microsoft.quantum.lang-ref.int)

一个索引 `output[location] == pauli` ，其中， `output` 是此函数的输出。


### <a name="n--int"></a>n： [Int](xref:microsoft.quantum.lang-ref.int)

要返回的数组的长度。



## <a name="output--pauli"></a>Output： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

