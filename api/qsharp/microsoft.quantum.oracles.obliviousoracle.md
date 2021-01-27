---
uid: Microsoft.Quantum.Oracles.ObliviousOracle
title: ObliviousOracle 用户定义的类型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ObliviousOracle
qsharp.summary: >-
  Represents an oracle for oblivious amplitude amplification.

  The inputs to the oracle $O$ are:

  - The ancilla register $a$ that $O$ acts on. - The system register $s$ on which the desired unitary $U$ is applied, post-selected on register $a$ being in state $\ket{t}\_a$.
ms.openlocfilehash: 793e72af56e288f9b437302f9958665e92e5e763
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842547"
---
# <a name="obliviousoracle-user-defined-type"></a>ObliviousOracle 用户定义的类型

命名空间： [Oracles](xref:Microsoft.Quantum.Oracles)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


表示 oracle for 在意波幅放大。

Oracle $O $ 的输入为：

- Ancilla 注册了 $O $ $a $ 的操作。
- 系统注册 $s $，将对其应用所需的单一 $U $，并在 register $a $ $ \ket{t} \_ a $。

```qsharp

newtype ObliviousOracle = (((Qubit[], Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a>备注

此 oracle 定义者： $ $ O\ket {s} \_ a\ket {\ psi} \_ s = \Lambda\ket{t} \_ a U \ket{\psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket{t ^ \perp} \_ a\cdots $ $ 作用于 ancilla 状态 $ \ket{s} \_ a $，在任何系统状态 $ \ket{\psi} s $ 上实现单一 $U $，该操作 \_ 由 $ \lambda \_ a $ 标记。
第一个参数是 $ \ket{s} 的 qubit 寄存器 \_ $。 第二个参数是 $ \ket{\psi} s $ 的 qubit 寄存器 \_ 。