---
uid: Microsoft.Quantum.Canon.CX
title: CX 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CX
qsharp.summary: >-
  Applies the controlled-X (CX) gate to a pair of qubits.

  $$ \begin{align} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: c430525b71ad4ef0812d90a8ff20c41a5d5b8708
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696083"
---
# <a name="cx-operation"></a><span data-ttu-id="c4dd0-102">CX 操作</span><span class="sxs-lookup"><span data-stu-id="c4dd0-102">CX operation</span></span>

<span data-ttu-id="c4dd0-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c4dd0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c4dd0-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c4dd0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c4dd0-105">将受控-X (CX) 入口应用于一对 qubits。</span><span class="sxs-lookup"><span data-stu-id="c4dd0-105">Applies the controlled-X (CX) gate to a pair of qubits.</span></span>

<span data-ttu-id="c4dd0-106">$ $ \begin{align} \left ( \begin{matrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}，$ $，其中的行和列按 "量程概念" 指南进行组织。</span><span class="sxs-lookup"><span data-stu-id="c4dd0-106">$$ \begin{align} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CX (control : Qubit, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="c4dd0-107">输入</span><span class="sxs-lookup"><span data-stu-id="c4dd0-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="c4dd0-108">控件： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c4dd0-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c4dd0-109">为 CX 入口控制 qubit。</span><span class="sxs-lookup"><span data-stu-id="c4dd0-109">Control qubit for the CX gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="c4dd0-110">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="c4dd0-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="c4dd0-111">CX 入口的目标 qubit。</span><span class="sxs-lookup"><span data-stu-id="c4dd0-111">Target qubit for the CX gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c4dd0-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c4dd0-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c4dd0-113">注解</span><span class="sxs-lookup"><span data-stu-id="c4dd0-113">Remarks</span></span>

<span data-ttu-id="c4dd0-114">等效于：</span><span class="sxs-lookup"><span data-stu-id="c4dd0-114">Equivalent to:</span></span>

```qsharp
Controlled X([control], target);
```

<span data-ttu-id="c4dd0-115">和：</span><span class="sxs-lookup"><span data-stu-id="c4dd0-115">and to:</span></span>

```qsharp
CNOT(control, target);
```