---
uid: Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity
title: PrepareSingleQubitIdentity 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareSingleQubitIdentity
qsharp.summary: >-
  Prepares a qubit in the maximally mixed state.

  It prepares the given qubit in the $\boldone / 2$ state by applying the depolarizing channel $$ \begin{align} \Omega(\rho) \mathrel{:=} \frac{1}{4} \sum_{\mu \in \{0, 1, 2, 3\}} \sigma\_{\mu} \rho \sigma\_{\mu}^{\dagger}, \end{align} $$ where $\sigma\_i$ is the $i$th Pauli operator, and where $\rho$ is a density operator representing a mixed state.
ms.openlocfilehash: 1c8c161ec2eae73a81c46e7941af49145cde0493
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193618"
---
# <a name="preparesinglequbitidentity-operation"></a>PrepareSingleQubitIdentity 操作

命名空间： [Microsoft 量子. 准备](xref:Microsoft.Quantum.Preparation)

包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)


准备处于最大化混合状态的 qubit。

它通过应用 depolarizing 通道 $ $ \begin{align} \Omega ( \rho) \mathrel{，在 $ \boldone/$2 状态中准备给定的 qubit： =} \frac {1} {4} \ sum_ {\mu \in \{ 0，1，2，3 \} } \sigma \_ {\mu} \rho \sigma \_ {\mu} ^ {\dagger}，\end{align} $ $，其中 $ \sigma \_ i $ 是 $i $ th Pauli 运算符，其中 $ \rho $ 是表示混合状态的密度运算符。

```qsharp
operation PrepareSingleQubitIdentity (qubit : Qubit) : Unit
```


## <a name="input"></a>输入

### <a name="qubit--qubit"></a>qubit： [qubit](xref:microsoft.quantum.lang-ref.qubit)

其状态为 depolarized 的 qubit。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>备注

混合状态 $ \boldone/$2 描述将此操作应用于状态的结果。隐式描述此操作中随机选择的预期值。
因此，对于任何单个应用程序，此操作都会将纯状态映射到纯状态，但它的行为如预期所述。
具体而言，可以在进程 tomography 中使用此操作来度量通道的 *非 unital* 组件。