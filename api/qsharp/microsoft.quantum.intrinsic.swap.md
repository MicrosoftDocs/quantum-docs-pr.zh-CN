---
uid: Microsoft.Quantum.Intrinsic.SWAP
title: 交换操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: SWAP
qsharp.summary: >-
  Applies the SWAP gate to a pair of qubits.

  \begin{align} \operatorname{SWAP} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{bmatrix}, \end{align}

  where rows and columns are ordered as in the quantum concepts guide.
ms.openlocfilehash: 18b910741e9d0883fc5fcd025eb647407c823269
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696643"
---
# <a name="swap-operation"></a><span data-ttu-id="42658-102">交换操作</span><span class="sxs-lookup"><span data-stu-id="42658-102">SWAP operation</span></span>

<span data-ttu-id="42658-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="42658-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="42658-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="42658-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="42658-105">将交换入口应用于一对 qubits。</span><span class="sxs-lookup"><span data-stu-id="42658-105">Applies the SWAP gate to a pair of qubits.</span></span>

<span data-ttu-id="42658-106">\begin{align} \operatorname{SWAP} \mathrel{： =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \end{bmatrix}，\end{align}</span><span class="sxs-lookup"><span data-stu-id="42658-106">\begin{align} \operatorname{SWAP} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{bmatrix}, \end{align}</span></span>

<span data-ttu-id="42658-107">行和列的排序顺序，如量程概念指南中所示。</span><span class="sxs-lookup"><span data-stu-id="42658-107">where rows and columns are ordered as in the quantum concepts guide.</span></span>

```qsharp
operation SWAP (qubit1 : Qubit, qubit2 : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="42658-108">输入</span><span class="sxs-lookup"><span data-stu-id="42658-108">Input</span></span>

### <a name="qubit1--qubit"></a><span data-ttu-id="42658-109">qubit1： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="42658-109">qubit1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="42658-110">要交换的第一个 qubit。</span><span class="sxs-lookup"><span data-stu-id="42658-110">First qubit to be swapped.</span></span>


### <a name="qubit2--qubit"></a><span data-ttu-id="42658-111">qubit2： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="42658-111">qubit2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="42658-112">要交换的第二个 qubit。</span><span class="sxs-lookup"><span data-stu-id="42658-112">Second qubit to be swapped.</span></span>



## <a name="output--unit"></a><span data-ttu-id="42658-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="42658-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="42658-114">注解</span><span class="sxs-lookup"><span data-stu-id="42658-114">Remarks</span></span>

<span data-ttu-id="42658-115">等效于：</span><span class="sxs-lookup"><span data-stu-id="42658-115">Equivalent to:</span></span>

```qsharp
CNOT(qubit1, qubit2);
CNOT(qubit2, qubit1);
CNOT(qubit1, qubit2);
```