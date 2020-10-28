---
uid: Microsoft.Quantum.Intrinsic.T
title: T 运算
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: T
qsharp.summary: Applies the T gate to a single qubit.
ms.openlocfilehash: 868031386c95f65ae956b5e444c6d87d7ea0a697
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699777"
---
# <a name="t-operation"></a>T 运算

命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)

软件包 [](https://nuget.org/packages/)


将 T 入口应用于单个 qubit。

```qsharp
operation T (qubit : Qubit) : Unit
```


## <a name="description"></a>说明

此操作可由单一矩阵 \begin{align} T \mathrel{： =} \begin{bmatrix} 1 & 0 \\ \\ 0 & e ^ {i \pi/4} \end{bmatrix}. 模拟
\end{align}

## <a name="input"></a>输入

### <a name="qubit--qubit"></a>qubit： [qubit](xref:microsoft.quantum.lang-ref.qubit)

应将入口应用到的 Qubit。



## <a name="output--unit"></a>输出： [单元](xref:microsoft.quantum.lang-ref.unit)

