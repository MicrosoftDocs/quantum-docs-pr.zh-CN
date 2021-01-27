---
uid: Microsoft.Quantum.Canon.CX
title: CX 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CX
qsharp.summary: >-
  Applies the controlled-X (CX) gate to a pair of qubits.

  $$ \begin{align} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: e27b30a6b4609daaac2cc5eda68120115777af0c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840760"
---
# <a name="cx-operation"></a><span data-ttu-id="1019a-102">CX 操作</span><span class="sxs-lookup"><span data-stu-id="1019a-102">CX operation</span></span>

<span data-ttu-id="1019a-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1019a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1019a-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1019a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1019a-105">将受控-X (CX) 入口应用于一对 qubits。</span><span class="sxs-lookup"><span data-stu-id="1019a-105">Applies the controlled-X (CX) gate to a pair of qubits.</span></span>

<span data-ttu-id="1019a-106">$ $ \begin{align} \left ( \begin{matrix} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}，$ $，其中的行和列按 "量程概念" 指南进行组织。</span><span class="sxs-lookup"><span data-stu-id="1019a-106">$$ \begin{align} \left(\begin{matrix} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \\\\ 0 & 0 & 1 & 0 \end{matrix}\right) \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CX (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="1019a-107">输入</span><span class="sxs-lookup"><span data-stu-id="1019a-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="1019a-108">控件： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="1019a-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="1019a-109">为 CX 入口控制 qubit。</span><span class="sxs-lookup"><span data-stu-id="1019a-109">Control qubit for the CX gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="1019a-110">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="1019a-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="1019a-111">CX 入口的目标 qubit。</span><span class="sxs-lookup"><span data-stu-id="1019a-111">Target qubit for the CX gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1019a-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1019a-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="1019a-113">备注</span><span class="sxs-lookup"><span data-stu-id="1019a-113">Remarks</span></span>

<span data-ttu-id="1019a-114">等效于：</span><span class="sxs-lookup"><span data-stu-id="1019a-114">Equivalent to:</span></span>

```qsharp
Controlled X([control], target);
```

<span data-ttu-id="1019a-115">和：</span><span class="sxs-lookup"><span data-stu-id="1019a-115">and to:</span></span>

```qsharp
CNOT(control, target);
```