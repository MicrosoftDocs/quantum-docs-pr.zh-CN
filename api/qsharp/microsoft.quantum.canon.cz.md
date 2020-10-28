---
uid: Microsoft.Quantum.Canon.CZ
title: CZ 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CZ
qsharp.summary: >-
  Applies the controlled-Z (CZ) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: bc38cd43a0dcaf7aea735ef6468a394e91c85593
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696079"
---
# <a name="cz-operation"></a><span data-ttu-id="e9871-102">CZ 操作</span><span class="sxs-lookup"><span data-stu-id="e9871-102">CZ operation</span></span>

<span data-ttu-id="e9871-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="e9871-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="e9871-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e9871-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e9871-105">将受控-Z (CZ) 入口应用于一对 qubits。</span><span class="sxs-lookup"><span data-stu-id="e9871-105">Applies the controlled-Z (CZ) gate to a pair of qubits.</span></span>

<span data-ttu-id="e9871-106">$ $ \begin{align} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 0 & 0 &-1 \end{align}，$ $，其中的行和列组织为 "量程概念" 指南。</span><span class="sxs-lookup"><span data-stu-id="e9871-106">$$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CZ (control : Qubit, target : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="e9871-107">输入</span><span class="sxs-lookup"><span data-stu-id="e9871-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="e9871-108">控件： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e9871-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e9871-109">控制 CZ 入口的 qubit。</span><span class="sxs-lookup"><span data-stu-id="e9871-109">Control qubit for the CZ gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="e9871-110">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="e9871-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="e9871-111">CZ 入口的目标 qubit。</span><span class="sxs-lookup"><span data-stu-id="e9871-111">Target qubit for the CZ gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="e9871-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="e9871-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="e9871-113">注解</span><span class="sxs-lookup"><span data-stu-id="e9871-113">Remarks</span></span>

<span data-ttu-id="e9871-114">等效于：</span><span class="sxs-lookup"><span data-stu-id="e9871-114">Equivalent to:</span></span>

```qsharp
Controlled Z([control], target);
```