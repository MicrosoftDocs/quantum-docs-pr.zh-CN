---
uid: Microsoft.Quantum.Canon.CZ
title: CZ 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CZ
qsharp.summary: >-
  Applies the controlled-Z (CZ) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: 419082dbf8f96a9fe2dfabeab77e1823cb59a8f2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207201"
---
# <a name="cz-operation"></a><span data-ttu-id="27fc6-102">CZ 操作</span><span class="sxs-lookup"><span data-stu-id="27fc6-102">CZ operation</span></span>

<span data-ttu-id="27fc6-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="27fc6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="27fc6-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="27fc6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="27fc6-105">将受控-Z (CZ) 入口应用于一对 qubits。</span><span class="sxs-lookup"><span data-stu-id="27fc6-105">Applies the controlled-Z (CZ) gate to a pair of qubits.</span></span>

<span data-ttu-id="27fc6-106">$ $ \begin{align} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 0 & 0 &-1 \end{align}，$ $，其中的行和列组织为 "量程概念" 指南。</span><span class="sxs-lookup"><span data-stu-id="27fc6-106">$$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CZ (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="27fc6-107">输入</span><span class="sxs-lookup"><span data-stu-id="27fc6-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="27fc6-108">控件： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="27fc6-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="27fc6-109">控制 CZ 入口的 qubit。</span><span class="sxs-lookup"><span data-stu-id="27fc6-109">Control qubit for the CZ gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="27fc6-110">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="27fc6-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="27fc6-111">CZ 入口的目标 qubit。</span><span class="sxs-lookup"><span data-stu-id="27fc6-111">Target qubit for the CZ gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="27fc6-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="27fc6-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="27fc6-113">备注</span><span class="sxs-lookup"><span data-stu-id="27fc6-113">Remarks</span></span>

<span data-ttu-id="27fc6-114">等效于：</span><span class="sxs-lookup"><span data-stu-id="27fc6-114">Equivalent to:</span></span>

```qsharp
Controlled Z([control], target);
```