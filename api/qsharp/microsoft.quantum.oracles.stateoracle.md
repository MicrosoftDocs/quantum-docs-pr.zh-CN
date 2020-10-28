---
uid: Microsoft.Quantum.Oracles.StateOracle
title: StateOracle 用户定义的类型
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracle
qsharp.summary: >-
  Represents an oracle for state preparation.

  The inputs to the oracle $O$ are:

  - An integer indexing the flag qubit $f$. - The system register $s$ that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 65f4edcf2101190da0c6d00eb4dd21881143ceb0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700781"
---
# <a name="stateoracle-user-defined-type"></a>StateOracle 用户定义的类型

命名空间： [Oracles](xref:Microsoft.Quantum.Oracles)

软件包 [](https://nuget.org/packages/)


表示 oracle for 状态准备。

Oracle $O $ 的输入为：

- 对标志 qubit $f $ 进行索引的整数。
- 系统注册 $s $，将存储所需的量程状态 $ \ket{\psi} \_ s $。

```qsharp

newtype StateOracle = (((Int, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="remarks"></a>注解

此 oracle 定义者： $ $ O\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f\ket {\ psi} \_ s + \sqrt{1-| \lambda | ^ 2} \ket {0} \_ f\cdots，$ $ 作用于 on 计算基础状态 $ \ket {0} \_ {f} \ket {0} \_ s $，以 \_ 在 $ \ket{\psi} {1} f $ 标志的基础上创建包含波幅 $ \lambda $ 的目标状态 $ \ket s $ \_ 。
第一个参数是 $ \ket f $ 的 qubit 寄存器的索引 {0} \_ 。 第二个参数包含两个寄存器。