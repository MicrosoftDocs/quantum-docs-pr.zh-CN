---
uid: Microsoft.Quantum.Intrinsic.R1Frac
title: R1Frac 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R1Frac
qsharp.summary: >-
  Applies a rotation about the $\ket{1}$ state by an angle specified as a dyadic fraction.

  \begin{align} R_1(n, k) \mathrel{:=} \operatorname{diag}(1, e^{i \pi k / 2^n}). \end{align}

  > [!WARNING] > This operation uses the **opposite** sign convention from > @"microsoft.quantum.intrinsic.r", and does not include the > factor of $1/ 2$ included by @"microsoft.quantum.intrinsic.r1".
ms.openlocfilehash: bfa6cd60eebd05feec8cfa2bf71e09dc0d02843a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699793"
---
# <a name="r1frac-operation"></a>R1Frac 操作

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)

软件包 [](https://nuget.org/packages/)


{1}通过指定为 dyadic 分数的角度，将关于 $ \ket $ 状态的旋转。

\begin{align} R_1 (n，k) \mathrel{： =} \operatorname{diag} (1，e ^ {i \pi k/2 ^ n} ) 。
\end{align}

> [!WARNING]
> 此操作使用 **相反** 的符号约定，不包括中的 @"microsoft.quantum.intrinsic.r" $ 1/2 $ 的因子 @"microsoft.quantum.intrinsic.r1" 。

```qsharp
operation R1Frac (numerator : Int, power : Int, qubit : Qubit) : Unit
```


## <a name="input"></a>输入

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
RFrac(PauliZ, -numerator, denominator + 1, qubit);
RFrac(PauliI, numerator, denominator + 1, qubit);
```