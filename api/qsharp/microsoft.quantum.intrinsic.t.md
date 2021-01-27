---
uid: Microsoft.Quantum.Intrinsic.T
title: T 运算
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: T
qsharp.summary: Applies the T gate to a single qubit.
ms.openlocfilehash: bee252d9905aed26f6bf663f895e464e38073f44
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98817517"
---
# <a name="t-operation"></a><span data-ttu-id="a0ccb-102">T 运算</span><span class="sxs-lookup"><span data-stu-id="a0ccb-102">T operation</span></span>

<span data-ttu-id="a0ccb-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="a0ccb-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="a0ccb-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="a0ccb-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="a0ccb-105">将 T 入口应用于单个 qubit。</span><span class="sxs-lookup"><span data-stu-id="a0ccb-105">Applies the T gate to a single qubit.</span></span>

```qsharp
operation T (qubit : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="a0ccb-106">说明</span><span class="sxs-lookup"><span data-stu-id="a0ccb-106">Description</span></span>

<span data-ttu-id="a0ccb-107">此操作可由单一矩阵 \begin{align} T \mathrel{： =} \begin{bmatrix} 1 & 0 \\ \\ 0 & e ^ {i \pi/4} \end{bmatrix}. 模拟</span><span class="sxs-lookup"><span data-stu-id="a0ccb-107">This operation can be simulated by the unitary matrix \begin{align} T \mathrel{:=} \begin{bmatrix} 1 & 0 \\\\ 0 & e^{i \pi / 4} \end{bmatrix}.</span></span>
<span data-ttu-id="a0ccb-108">\end{align}</span><span class="sxs-lookup"><span data-stu-id="a0ccb-108">\end{align}</span></span>

## <a name="input"></a><span data-ttu-id="a0ccb-109">输入</span><span class="sxs-lookup"><span data-stu-id="a0ccb-109">Input</span></span>

### <a name="qubit--qubit"></a><span data-ttu-id="a0ccb-110">qubit： [qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="a0ccb-110">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="a0ccb-111">应将入口应用到的 Qubit。</span><span class="sxs-lookup"><span data-stu-id="a0ccb-111">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a0ccb-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a0ccb-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

