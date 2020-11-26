---
uid: Microsoft.Quantum.Canon.CY
title: CY 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CY
qsharp.summary: >-
  Applies the controlled-Y (CY) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -i \\\\ 0 & 0 & i & 0 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: 4a1a533421dd9205e973d5e8237d67b20bc4886d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216568"
---
# <a name="cy-operation"></a><span data-ttu-id="2ced1-102">CY 操作</span><span class="sxs-lookup"><span data-stu-id="2ced1-102">CY operation</span></span>

<span data-ttu-id="2ced1-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2ced1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2ced1-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2ced1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2ced1-105">将受控-Y (CY) 入口应用于一对 qubits。</span><span class="sxs-lookup"><span data-stu-id="2ced1-105">Applies the controlled-Y (CY) gate to a pair of qubits.</span></span>

<span data-ttu-id="2ced1-106">$ $ \begin{align} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 &-i \\ \\ 0 & 0 & & 0 \end{align}，$ $，其中的行和列按 "量程概念" 指南进行组织。</span><span class="sxs-lookup"><span data-stu-id="2ced1-106">$$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -i \\\\ 0 & 0 & i & 0 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CY (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="2ced1-107">输入</span><span class="sxs-lookup"><span data-stu-id="2ced1-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="2ced1-108">控件： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2ced1-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="2ced1-109">控制 CY 入口的 qubit。</span><span class="sxs-lookup"><span data-stu-id="2ced1-109">Control qubit for the CY gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="2ced1-110">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="2ced1-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="2ced1-111">为 CY 入口定位 qubit。</span><span class="sxs-lookup"><span data-stu-id="2ced1-111">Target qubit for the CY gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2ced1-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2ced1-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="2ced1-113">备注</span><span class="sxs-lookup"><span data-stu-id="2ced1-113">Remarks</span></span>

<span data-ttu-id="2ced1-114">等效于：</span><span class="sxs-lookup"><span data-stu-id="2ced1-114">Equivalent to:</span></span>

```qsharp
Controlled Y([control], target);
```