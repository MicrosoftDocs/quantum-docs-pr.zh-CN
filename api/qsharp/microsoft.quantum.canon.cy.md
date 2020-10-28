---
uid: Microsoft.Quantum.Canon.CY
title: CY 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CY
qsharp.summary: >-
  Applies the controlled-Y (CY) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -i \\\\ 0 & 0 & i & 0 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: 291891457ff39cf7092d17aa1d900dd0d35d9cf8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696081"
---
# <a name="cy-operation"></a><span data-ttu-id="ed9b0-102">CY 操作</span><span class="sxs-lookup"><span data-stu-id="ed9b0-102">CY operation</span></span>

<span data-ttu-id="ed9b0-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ed9b0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ed9b0-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ed9b0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ed9b0-105">将受控-Y (CY) 入口应用于一对 qubits。</span><span class="sxs-lookup"><span data-stu-id="ed9b0-105">Applies the controlled-Y (CY) gate to a pair of qubits.</span></span>

<span data-ttu-id="ed9b0-106">$ $ \begin{align} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 &-i \\ \\ 0 & 0 & & 0 \end{align}，$ $，其中的行和列按 "量程概念" 指南进行组织。</span><span class="sxs-lookup"><span data-stu-id="ed9b0-106">$$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & -i \\\\ 0 & 0 & i & 0 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CY (control : Qubit, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="ed9b0-107">输入</span><span class="sxs-lookup"><span data-stu-id="ed9b0-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="ed9b0-108">控件： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ed9b0-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ed9b0-109">控制 CY 入口的 qubit。</span><span class="sxs-lookup"><span data-stu-id="ed9b0-109">Control qubit for the CY gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="ed9b0-110">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="ed9b0-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="ed9b0-111">为 CY 入口定位 qubit。</span><span class="sxs-lookup"><span data-stu-id="ed9b0-111">Target qubit for the CY gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ed9b0-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ed9b0-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="ed9b0-113">注解</span><span class="sxs-lookup"><span data-stu-id="ed9b0-113">Remarks</span></span>

<span data-ttu-id="ed9b0-114">等效于：</span><span class="sxs-lookup"><span data-stu-id="ed9b0-114">Equivalent to:</span></span>

```qsharp
Controlled Y([control], target);
```