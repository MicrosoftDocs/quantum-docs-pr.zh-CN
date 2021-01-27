---
uid: Microsoft.Quantum.Intrinsic.H
title: H 运算
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: H
qsharp.summary: >-
  Applies the Hadamard transformation to a single qubit.

  \begin{align} H \mathrel{:=} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ 1 & -1 \end{bmatrix}. \end{align}
ms.openlocfilehash: 6fa712b00a2745d8c0d8d3198cc9c5e6af3e2400
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98818986"
---
# <a name="h-operation"></a><span data-ttu-id="64ac0-102">H 运算</span><span class="sxs-lookup"><span data-stu-id="64ac0-102">H operation</span></span>

<span data-ttu-id="64ac0-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="64ac0-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="64ac0-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="64ac0-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="64ac0-105">将 Hadamard 转换应用于单个 qubit。</span><span class="sxs-lookup"><span data-stu-id="64ac0-105">Applies the Hadamard transformation to a single qubit.</span></span>

<span data-ttu-id="64ac0-106">\begin{align} H \mathrel{： =} \frac {1} {\sqrt {2} } \begin{bmatrix} 1 & 1 \\ \\ 1 &-1 \end{bmatrix}。</span><span class="sxs-lookup"><span data-stu-id="64ac0-106">\begin{align} H \mathrel{:=} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ 1 & -1 \end{bmatrix}.</span></span>
<span data-ttu-id="64ac0-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="64ac0-107">\end{align}</span></span>

```qsharp
operation H (qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="64ac0-108">输入</span><span class="sxs-lookup"><span data-stu-id="64ac0-108">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="64ac0-109">qubit： [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="64ac0-109">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="64ac0-110">应将入口应用到的 Qubit。</span><span class="sxs-lookup"><span data-stu-id="64ac0-110">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="64ac0-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="64ac0-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

