---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracle
title: DeterministicStateOracle 用户定义的类型
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracle
qsharp.summary: >-
  Represents an oracle for deterministic state preparation.

  The input to the oracle $O$ is:

  - The register that will store the desired quantum state $\ket{\psi}\_s$.
ms.openlocfilehash: 10ae9e52f298cdfb92dd6a9e5cf85960bece6800
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842594"
---
# <a name="deterministicstateoracle-user-defined-type"></a>DeterministicStateOracle 用户定义的类型

命名空间： [Oracles](xref:Microsoft.Quantum.Oracles)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


表示 oracle for 确定性状态准备。

Oracle $O $ 的输入为：

- 将存储所需的量程状态 $ \ket{\psi} \_ s $ 的寄存器。

```qsharp

newtype DeterministicStateOracle = ((Qubit[] => Unit is Adj + Ctl));
```



## <a name="remarks"></a>备注

此 oracle 定义的 $O \ket {0} = \ket{\psi} $ 对计算基础状态 $ \ket $ 采取操作 {0} ，以创建状态 $ \ket{\psi} $。
第一个参数是 $ \ket{\psi} $ 的 qubit 寄存器。