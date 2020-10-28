---
uid: Microsoft.Quantum.Intrinsic.H
title: H 运算
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: H
qsharp.summary: >-
  Applies the Hadamard transformation to a single qubit.

  \begin{align} H \mathrel{:=} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ 1 & -1 \end{bmatrix}. \end{align}
ms.openlocfilehash: 1ba99d2f34c601b46b82fb853008464c3add965d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695382"
---
# <a name="h-operation"></a><span data-ttu-id="f1492-102">H 运算</span><span class="sxs-lookup"><span data-stu-id="f1492-102">H operation</span></span>

<span data-ttu-id="f1492-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="f1492-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="f1492-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f1492-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f1492-105">将 Hadamard 转换应用于单个 qubit。</span><span class="sxs-lookup"><span data-stu-id="f1492-105">Applies the Hadamard transformation to a single qubit.</span></span>

<span data-ttu-id="f1492-106">\begin{align} H \mathrel{： =} \frac {1} {\sqrt {2} } \begin{bmatrix} 1 & 1 \\ \\ 1 &-1 \end{bmatrix}。</span><span class="sxs-lookup"><span data-stu-id="f1492-106">\begin{align} H \mathrel{:=} \frac{1}{\sqrt{2}} \begin{bmatrix} 1 & 1 \\\\ 1 & -1 \end{bmatrix}.</span></span>
<span data-ttu-id="f1492-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="f1492-107">\end{align}</span></span>

```qsharp
operation H (qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="f1492-108">输入</span><span class="sxs-lookup"><span data-stu-id="f1492-108">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="f1492-109">qubit： [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="f1492-109">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="f1492-110">应将入口应用到的 Qubit。</span><span class="sxs-lookup"><span data-stu-id="f1492-110">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f1492-111">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f1492-111">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

