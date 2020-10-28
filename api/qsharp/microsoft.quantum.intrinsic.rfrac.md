---
uid: Microsoft.Quantum.Intrinsic.RFrac
title: RFrac 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: RFrac
qsharp.summary: >-
  Applies a rotation about the given Pauli axis by an angle specified as a dyadic fraction.

  \begin{align} R_{\mu}(n, k) \mathrel{:=} e^{i \pi n \sigma_{\mu} / 2^k}, \end{align} where $\mu \in \{I, X, Y, Z\}$.

  > [!WARNING] > This operation uses the **opposite** sign convention from > @"microsoft.quantum.intrinsic.r".
ms.openlocfilehash: 9fe6aee6c7bb9e52538eae5d2caa2a6025cb85d8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700577"
---
# <a name="rfrac-operation"></a>RFrac 操作

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)

软件包 [](https://nuget.org/packages/)


通过指定为 dyadic 分数的角度，对给定 Pauli 轴进行旋转。

\begin{align} R_ {\mu} (n，k) \mathrel{： =} e ^ {i \pi n \ sigma_ {\mu}/2 ^ k}，\end{align} 其中，$ \mu \in \{ i，X，Y，Z \} $。

> [!WARNING]
> 此操作使用中的 **相反** 符号约定 @"microsoft.quantum.intrinsic.r" 。

```qsharp
operation RFrac (pauli : Pauli, numerator : Int, power : Int, qubit : Qubit) : Unit
```


## <a name="input"></a>输入

### <a name="pauli--pauli"></a>pauli： [pauli](xref:microsoft.quantum.lang-ref.pauli)

要指数化以形成旋转的 Pauli 运算符。


### <a name="numerator--int"></a>分子： [Int](xref:microsoft.quantum.lang-ref.int)

Dyadic 中要旋转 qubit 的角度的分数表示形式的分子。


### <a name="power--int"></a>幂： [Int](xref:microsoft.quantum.lang-ref.int)

幂 of，指定 qubit 要旋转的角度的分母。


### <a name="qubit--qubit"></a>qubit： [qubit](xref:microsoft.quantum.lang-ref.qubit)

应将入口应用到的 Qubit。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>注解

等效于：

```qsharp
// PI() is a Q# function that returns an approximation of π.
R(pauli, -PI() * IntAsDouble(numerator) / IntAsDouble(2 ^ (power - 1)), qubit);
```