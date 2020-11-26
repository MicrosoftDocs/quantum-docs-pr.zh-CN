---
uid: Microsoft.Quantum.Intrinsic.CNOT
title: CNOT-CONTAINS 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: CNOT
qsharp.summary: >-
  Applies the controlled-NOT (CNOT) gate to a pair of qubits.

  \begin{align} \operatorname{CNOT} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}, \end{align}

  where rows and columns are ordered as in the quantum concepts guide.
ms.openlocfilehash: 90e84f7d0ea7373498632474dfafa23335f0c78e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198970"
---
# <a name="cnot-operation"></a><span data-ttu-id="1fcf5-102">CNOT-CONTAINS 操作</span><span class="sxs-lookup"><span data-stu-id="1fcf5-102">CNOT operation</span></span>

<span data-ttu-id="1fcf5-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="1fcf5-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="1fcf5-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="1fcf5-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="1fcf5-105">将受控-NOT (CNOT-CONTAINS) 入口应用于一对 qubits。</span><span class="sxs-lookup"><span data-stu-id="1fcf5-105">Applies the controlled-NOT (CNOT) gate to a pair of qubits.</span></span>

<span data-ttu-id="1fcf5-106">\begin{align} \operatorname{CNOT} \mathrel{： =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \end{bmatrix}，\end{align}</span><span class="sxs-lookup"><span data-stu-id="1fcf5-106">\begin{align} \operatorname{CNOT} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{bmatrix}, \end{align}</span></span>

<span data-ttu-id="1fcf5-107">行和列的排序顺序，如量程概念指南中所示。</span><span class="sxs-lookup"><span data-stu-id="1fcf5-107">where rows and columns are ordered as in the quantum concepts guide.</span></span>

```qsharp
operation CNOT (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="1fcf5-108">输入</span><span class="sxs-lookup"><span data-stu-id="1fcf5-108">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="1fcf5-109">控件： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="1fcf5-109">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="1fcf5-110">控制 CNOT-CONTAINS 入口的 qubit。</span><span class="sxs-lookup"><span data-stu-id="1fcf5-110">Control qubit for the CNOT gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="1fcf5-111">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="1fcf5-111">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="1fcf5-112">CNOT-CONTAINS 入口的目标 qubit。</span><span class="sxs-lookup"><span data-stu-id="1fcf5-112">Target qubit for the CNOT gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1fcf5-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1fcf5-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="1fcf5-114">备注</span><span class="sxs-lookup"><span data-stu-id="1fcf5-114">Remarks</span></span>

<span data-ttu-id="1fcf5-115">等效于：</span><span class="sxs-lookup"><span data-stu-id="1fcf5-115">Equivalent to:</span></span>

```qsharp
Controlled X([control], target);
```