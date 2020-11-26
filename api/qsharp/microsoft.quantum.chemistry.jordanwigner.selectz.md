---
uid: Microsoft.Quantum.Chemistry.JordanWigner.SelectZ
title: SelectZ 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: SelectZ
qsharp.summary: A unitary $U$ that applies the Pauli $Z$ gate on a qubits $p$ conditioned on an index state $\ket{p}$. That is, $$ \begin{align} U\ket{p}\ket{\psi} = \ket{p}Z\_p\ket{\psi} \end{align} $$
ms.openlocfilehash: 08abe3f465432bf98f35090c59fb4d952c3b4882
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224711"
---
# <a name="selectz-operation"></a>SelectZ 操作

命名空间： [JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

包： [Microsoft 量子](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


一种单一 $U $，它对索引状态 $ \ket{p} $ $p 上 $Z 的 qubits $ 也就是说，$ $ \begin{align} U\ket {p} \ 票证 {\ psi} = \ket{p}Z \_ p\ket {\ psi} \end{align} $ $

```qsharp
operation SelectZ (indexRegister : Microsoft.Quantum.Arithmetic.LittleEndian, targetRegister : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>输入

### <a name="indexregister--littleendian"></a>indexRegister： [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

此寄存器的状态 $ \ket{p} $ 确定应用 $Z $ 的 qubit。


### <a name="targetregister--qubit"></a>targetRegister： [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

注册应用 Pauli 运算符的 qubits。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)

