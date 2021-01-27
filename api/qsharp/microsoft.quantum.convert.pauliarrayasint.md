---
uid: Microsoft.Quantum.Convert.PauliArrayAsInt
title: PauliArrayAsInt 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: PauliArrayAsInt
qsharp.summary: Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.
ms.openlocfilehash: 4c3c51813ef509fdc52773b15a956c0a99500603
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98832707"
---
# <a name="pauliarrayasint-function"></a>PauliArrayAsInt 函数

命名空间 [：](xref:Microsoft.Quantum.Convert)

包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


将表示为一个 qubit Pauli 运算符数组的多 qubit Pauli 运算符编码为一个整数。

```qsharp
function PauliArrayAsInt (paulis : Pauli[]) : Int
```


## <a name="input"></a>输入

### <a name="paulis--pauli"></a>paulis： [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

最多31个 qubit Pauli 运算符的数组。



## <a name="output--int"></a>输出： [Int](xref:microsoft.quantum.lang-ref.int)

唯一标识的整数 `paulis` ，如下所述。

## <a name="remarks"></a>备注

每个 Pauli 运算符都可以使用两个位进行编码： $ $ \begin{align} \boldone \mapsto 00，\quad X \mapsto 01，\quad Y \mapsto 11，\quad Z \mapsto 10。
\end{align} $ $

给定一个 Pauli 运算符数组 `[P0, ..., Pn]` ，该函数将返回一个整数，该整数通过以大字节序顺序连接每个 Pauli 运算符的映射来形成二进制展开 `bits(Pn) ... bits(P0)` 。