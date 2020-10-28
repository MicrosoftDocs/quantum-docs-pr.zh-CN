---
uid: Microsoft.Quantum.Intrinsic.CNOT
title: CNOT-CONTAINS 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: CNOT
qsharp.summary: >-
  Applies the controlled-NOT (CNOT) gate to a pair of qubits.

  \begin{align} \operatorname{CNOT} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}, \end{align}

  where rows and columns are ordered as in the quantum concepts guide.
ms.openlocfilehash: 2fb5b4df189fb3ab23b2ca5cb273b2451ffcc067
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700337"
---
# <a name="cnot-operation"></a><span data-ttu-id="9a12d-102">CNOT-CONTAINS 操作</span><span class="sxs-lookup"><span data-stu-id="9a12d-102">CNOT operation</span></span>

<span data-ttu-id="9a12d-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="9a12d-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="9a12d-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9a12d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9a12d-105">将受控-NOT (CNOT-CONTAINS) 入口应用于一对 qubits。</span><span class="sxs-lookup"><span data-stu-id="9a12d-105">Applies the controlled-NOT (CNOT) gate to a pair of qubits.</span></span>

<span data-ttu-id="9a12d-106">\begin{align} \operatorname{CNOT} \mathrel{： =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \end{bmatrix}，\end{align}</span><span class="sxs-lookup"><span data-stu-id="9a12d-106">\begin{align} \operatorname{CNOT} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}, \end{align}</span></span>

<span data-ttu-id="9a12d-107">行和列的排序顺序，如量程概念指南中所示。</span><span class="sxs-lookup"><span data-stu-id="9a12d-107">where rows and columns are ordered as in the quantum concepts guide.</span></span>

```qsharp
operation CNOT (control : Qubit, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="9a12d-108">输入</span><span class="sxs-lookup"><span data-stu-id="9a12d-108">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="9a12d-109">控件： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9a12d-109">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9a12d-110">控制 CNOT-CONTAINS 入口的 qubit。</span><span class="sxs-lookup"><span data-stu-id="9a12d-110">Control qubit for the CNOT gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="9a12d-111">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="9a12d-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="9a12d-112">CNOT-CONTAINS 入口的目标 qubit。</span><span class="sxs-lookup"><span data-stu-id="9a12d-112">Target qubit for the CNOT gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9a12d-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9a12d-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="9a12d-114">注解</span><span class="sxs-lookup"><span data-stu-id="9a12d-114">Remarks</span></span>

<span data-ttu-id="9a12d-115">等效于：</span><span class="sxs-lookup"><span data-stu-id="9a12d-115">Equivalent to:</span></span>

```qsharp
Controlled X([control], target);
```