---
uid: Microsoft.Quantum.Intrinsic.R
title: R 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R
qsharp.summary: >-
  Applies a rotation about the given Pauli axis.

  \begin{align} R_{\mu}(\theta) \mathrel{:=} e^{-i \theta \sigma_{\mu} / 2}, \end{align} where $\mu \in \{I, X, Y, Z\}$.
ms.openlocfilehash: 7d1d51031f4587b1c501feab459e614fc1530457
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699804"
---
# <a name="r-operation"></a>R 操作

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)

软件包 [](https://nuget.org/packages/)


应用围绕给定 Pauli 轴的旋转。

\begin{align} R_ {\mu} ( \theta) \mathrel{： =} e ^ {-i \theta \ sigma_ {\mu}/2}，\end{align}，其中，$ \mu \in \{ i，X，Y，Z \} $。

```qsharp
operation R (pauli : Pauli, theta : Double, qubit : Qubit) : Unit
```


## <a name="input"></a>输入

### <a name="pauli--pauli"></a>pauli： [pauli](xref:microsoft.quantum.lang-ref.pauli)

Pauli 运算符 ($ \mu $) 指数化形成旋转。


### <a name="theta--double"></a>theta： [Double](xref:microsoft.quantum.lang-ref.double)

Qubit 要旋转的角度。


### <a name="qubit--qubit"></a>qubit： [qubit](xref:microsoft.quantum.lang-ref.qubit)

应将入口应用到的 Qubit。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>注解

使用调用时 `pauli = PauliI` ，此操作将应用 *全局阶段* 。 与函子一起使用时，此阶段可能很重要 `Controlled` 。