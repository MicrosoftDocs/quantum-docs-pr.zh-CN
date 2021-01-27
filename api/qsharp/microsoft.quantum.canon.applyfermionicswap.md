---
uid: Microsoft.Quantum.Canon.ApplyFermionicSWAP
title: ApplyFermionicSWAP 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyFermionicSWAP
qsharp.summary: Applies the Fermionic SWAP.
ms.openlocfilehash: 334f407a32dabc8f4e0a1a29c8f06a1b9f40dc59
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845054"
---
# <a name="applyfermionicswap-operation"></a>ApplyFermionicSWAP 操作

命名空间： [Canon](xref:Microsoft.Quantum.Canon)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


应用 Fermionic 交换。

```qsharp
operation ApplyFermionicSWAP (qubit1 : Qubit, qubit2 : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>说明

如果两个 qubits 都是1，则这实质上是交换 qubits，同时应用-1 的全局阶段。 保留 orbitals 的 symmetrization。
有关详细信息，请参阅。

此操作由单一运算符 \begin{align} f_ {swap} \mathrel{： =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 &-1 \\ \\ \end{bmatrix}。
\end{align}

## <a name="input"></a>输入

### <a name="qubit1--qubit"></a>qubit1： [Qubit](xref:microsoft.quantum.lang-ref.qubit)

要交换的第一个 qubit。


### <a name="qubit2--qubit"></a>qubit2： [Qubit](xref:microsoft.quantum.lang-ref.qubit)

要交换的第二个 qubit。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>参考

- [*Ryan Babbush、Nathan Wiebe、Jarrod McClean、James McClain、Hartmut Neven、Garnet Kin-Lic 更改*、arXiv：1706.00023](https://arxiv.org/pdf/1706.00023.pdf)

## <a name="see-also"></a>另请参阅

- [。交换](xref:Microsoft.Quantum.Intrinsic.SWAP)