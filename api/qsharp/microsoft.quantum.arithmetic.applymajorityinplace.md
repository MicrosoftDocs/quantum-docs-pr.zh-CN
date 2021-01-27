---
uid: Microsoft.Quantum.Arithmetic.ApplyMajorityInPlace
title: ApplyMajorityInPlace 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyMajorityInPlace
qsharp.summary: Applies the three-qubit majority operation in-place on a register of qubits.
ms.openlocfilehash: 10b512392b2098663c09b2e07a09c4025da90706
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843729"
---
# <a name="applymajorityinplace-operation"></a>ApplyMajorityInPlace 操作

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


在 qubits 的收银机上就地应用三个 qubit 多数操作。

```qsharp
operation ApplyMajorityInPlace (output : Qubit, input : Qubit[]) : Unit is Adj + Ctl
```


## <a name="description"></a>说明

此操作计算 3 qubits 上就地的函数。

如果我们将 output qubit 表示为 $z $ 和输入 qubits 作为 $x $ 和 $y $，则该操作将执行以下转换： $ \ket{xyz} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x，y，z) } $。

## <a name="input"></a>输入

### <a name="output--qubit"></a>输出： [Qubit](xref:microsoft.quantum.lang-ref.qubit)

第一个输入 qubit。 请注意，输出是就地计算的，并存储在此 qubit 中。


### <a name="input--qubit"></a>输入： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

第二个和第三个输入 qubits。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)

