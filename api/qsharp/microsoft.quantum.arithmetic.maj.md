---
uid: Microsoft.Quantum.Arithmetic.MAJ
title: MAJ 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MAJ
qsharp.summary: This applies the in-place majority operation to 3 qubits.
ms.openlocfilehash: 68236f1deeb409a01152d4b7e854202a1134314e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846544"
---
# <a name="maj-operation"></a>MAJ 操作

命名空间 [：](xref:Microsoft.Quantum.Arithmetic)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


这会将就地大多数操作应用到 3 qubits。

```qsharp
operation MAJ (input0 : Qubit, input1 : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>说明

如果将目标 qubit 的状态指示为 $ \ket{z} $，并将输入 qubits 输入状态输入为 $ \ket{x} $ 和 $ \ket{y} $，则此操作将执行以下转换： $ \ket{xyz} \rightarrow \ket{x \oplus z} \ket{y \oplus z} \ket{\operatorname{MAJ} (x、y、z) } $。

## <a name="input"></a>输入

### <a name="input0--qubit"></a>input0： [Qubit](xref:microsoft.quantum.lang-ref.qubit)

第一个输入 qubit。


### <a name="input1--qubit"></a>input1： [Qubit](xref:microsoft.quantum.lang-ref.qubit)

第二个输入 qubit。


### <a name="target--qubit"></a>目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)

将应用多数函数的 qubit。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)

