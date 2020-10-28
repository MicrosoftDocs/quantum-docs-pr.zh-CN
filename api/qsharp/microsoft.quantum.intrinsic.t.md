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
# <a name="t-operation"></a><span data-ttu-id="0f30e-102">T 运算</span><span class="sxs-lookup"><span data-stu-id="0f30e-102">T operation</span></span>

<span data-ttu-id="0f30e-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="0f30e-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="0f30e-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0f30e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0f30e-105">将 T 入口应用于单个 qubit。</span><span class="sxs-lookup"><span data-stu-id="0f30e-105">Applies the T gate to a single qubit.</span></span>

```qsharp
operation T (qubit : Qubit) : Unit
```


## <a name="description"></a><span data-ttu-id="0f30e-106">说明</span><span class="sxs-lookup"><span data-stu-id="0f30e-106">Description</span></span>

<span data-ttu-id="0f30e-107">此操作可由单一矩阵 \begin{align} T \mathrel{： =} \begin{bmatrix} 1 & 0 \\ \\ 0 & e ^ {i \pi/4} \end{bmatrix}. 模拟</span><span class="sxs-lookup"><span data-stu-id="0f30e-107">This operation can be simulated by the unitary matrix \begin{align} T \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ 0 & e^{i \pi / 4} \end{bmatrix}.</span></span>
<span data-ttu-id="0f30e-108">\end{align}</span><span class="sxs-lookup"><span data-stu-id="0f30e-108">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="0f30e-109">输入</span><span class="sxs-lookup"><span data-stu-id="0f30e-109">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="0f30e-110">qubit： [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="0f30e-110">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="0f30e-111">应将入口应用到的 Qubit。</span><span class="sxs-lookup"><span data-stu-id="0f30e-111">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0f30e-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0f30e-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

