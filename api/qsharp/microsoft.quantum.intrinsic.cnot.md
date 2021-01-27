---
uid: Microsoft.Quantum.Intrinsic.CNOT
title: CNOT-CONTAINS 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: CNOT
qsharp.summary: >-
  Applies the controlled-NOT (CNOT) gate to a pair of qubits.

  \begin{align} \operatorname{CNOT} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}, \end{align}

  where rows and columns are ordered as in the quantum concepts guide.
ms.openlocfilehash: 02ae795c785dcbc25b56ac513a9237540e57ea63
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849441"
---
# <a name="cnot-operation"></a><span data-ttu-id="4310c-102">CNOT-CONTAINS 操作</span><span class="sxs-lookup"><span data-stu-id="4310c-102">CNOT operation</span></span>

<span data-ttu-id="4310c-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="4310c-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="4310c-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="4310c-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="4310c-105">将受控-NOT (CNOT-CONTAINS) 入口应用于一对 qubits。</span><span class="sxs-lookup"><span data-stu-id="4310c-105">Applies the controlled-NOT (CNOT) gate to a pair of qubits.</span></span>

<span data-ttu-id="4310c-106">\begin{align} \operatorname{CNOT} \mathrel{： =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \end{bmatrix}，\end{align}</span><span class="sxs-lookup"><span data-stu-id="4310c-106">\begin{align} \operatorname{CNOT} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}, \end{align}</span></span>

<span data-ttu-id="4310c-107">行和列的排序顺序，如量程概念指南中所示。</span><span class="sxs-lookup"><span data-stu-id="4310c-107">where rows and columns are ordered as in the quantum concepts guide.</span></span>

```qsharp
operation CNOT (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="4310c-108">输入</span><span class="sxs-lookup"><span data-stu-id="4310c-108">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="4310c-109">控件： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="4310c-109">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="4310c-110">控制 CNOT-CONTAINS 入口的 qubit。</span><span class="sxs-lookup"><span data-stu-id="4310c-110">Control qubit for the CNOT gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="4310c-111">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="4310c-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="4310c-112">CNOT-CONTAINS 入口的目标 qubit。</span><span class="sxs-lookup"><span data-stu-id="4310c-112">Target qubit for the CNOT gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4310c-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4310c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="4310c-114">备注</span><span class="sxs-lookup"><span data-stu-id="4310c-114">Remarks</span></span>

<span data-ttu-id="4310c-115">等效于：</span><span class="sxs-lookup"><span data-stu-id="4310c-115">Equivalent to:</span></span>

```qsharp
Controlled X([control], target);
```