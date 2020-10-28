---
uid: Microsoft.Quantum.Intrinsic.Rz
title: Vny-rz-j42 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Rz
qsharp.summary: >-
  Applies a rotation about the $z$-axis by a given angle.

  \begin{align} R_z(\theta) \mathrel{:=} e^{-i \theta \sigma_z / 2} = \begin{bmatrix} e^{-i \theta / 2} & 0 \\\\ 0 & e^{i \theta / 2} \end{bmatrix}. \end{align}
ms.openlocfilehash: 954b0b097d4bffcb8047a9f0c8a4c28445653c5d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699781"
---
# <a name="rz-operation"></a>Vny-rz-j42 操作

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)

软件包 [](https://nuget.org/packages/)


按给定角度向 $z $ 轴旋转。

\begin{align} R_z ( \theta) \mathrel{： =} e ^ {-i \theta \ sigma_z/2} = \begin{bmatrix} e ^ {-i \theta/2} & 0 \\ \\ 0 & e ^ {i \theta/2} \end{bmatrix}。
\end{align}

```qsharp
operation Rz (theta : Double, qubit : Qubit) : Unit
```


## <a name="input"></a>输入

### <a name="theta--double"></a>theta： [Double](xref:microsoft.quantum.lang-ref.double)

Qubit 要旋转的角度。


### <a name="qubit--qubit"></a>qubit： [qubit](xref:microsoft.quantum.lang-ref.qubit)

应将入口应用到的 Qubit。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>注解

等效于：

```qsharp
R(PauliZ, theta, qubit);
```