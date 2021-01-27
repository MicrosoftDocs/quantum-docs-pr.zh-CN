---
uid: Microsoft.Quantum.Intrinsic.SWAP
title: 交换操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: SWAP
qsharp.summary: >-
  Applies the SWAP gate to a pair of qubits.

  \begin{align} \operatorname{SWAP} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{bmatrix}, \end{align}

  where rows and columns are ordered as in the quantum concepts guide.
ms.openlocfilehash: 4d8d037404ac835a1dd032790e7fd03f29591c41
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849276"
---
# <a name="swap-operation"></a><span data-ttu-id="4d35a-102">交换操作</span><span class="sxs-lookup"><span data-stu-id="4d35a-102">SWAP operation</span></span>

<span data-ttu-id="4d35a-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="4d35a-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="4d35a-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="4d35a-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="4d35a-105">将交换入口应用于一对 qubits。</span><span class="sxs-lookup"><span data-stu-id="4d35a-105">Applies the SWAP gate to a pair of qubits.</span></span>

<span data-ttu-id="4d35a-106">\begin{align} \operatorname{SWAP} \mathrel{： =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \end{bmatrix}，\end{align}</span><span class="sxs-lookup"><span data-stu-id="4d35a-106">\begin{align} \operatorname{SWAP} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{bmatrix}, \end{align}</span></span>

<span data-ttu-id="4d35a-107">行和列的排序顺序，如量程概念指南中所示。</span><span class="sxs-lookup"><span data-stu-id="4d35a-107">where rows and columns are ordered as in the quantum concepts guide.</span></span>

```qsharp
operation SWAP (qubit1 : Qubit, qubit2 : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="4d35a-108">输入</span><span class="sxs-lookup"><span data-stu-id="4d35a-108">Input</span></span>

### <a name="qubit1--qubit"></a><span data-ttu-id="4d35a-109">qubit1： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="4d35a-109">qubit1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="4d35a-110">要交换的第一个 qubit。</span><span class="sxs-lookup"><span data-stu-id="4d35a-110">First qubit to be swapped.</span></span>


### <a name="qubit2--qubit"></a><span data-ttu-id="4d35a-111">qubit2： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="4d35a-111">qubit2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="4d35a-112">要交换的第二个 qubit。</span><span class="sxs-lookup"><span data-stu-id="4d35a-112">Second qubit to be swapped.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4d35a-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4d35a-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="4d35a-114">备注</span><span class="sxs-lookup"><span data-stu-id="4d35a-114">Remarks</span></span>

<span data-ttu-id="4d35a-115">等效于：</span><span class="sxs-lookup"><span data-stu-id="4d35a-115">Equivalent to:</span></span>

```qsharp
CNOT(qubit1, qubit2);
CNOT(qubit2, qubit1);
CNOT(qubit1, qubit2);
```