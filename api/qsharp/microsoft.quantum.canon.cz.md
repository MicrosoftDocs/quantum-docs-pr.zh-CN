---
uid: Microsoft.Quantum.Canon.CZ
title: CZ 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CZ
qsharp.summary: >-
  Applies the controlled-Z (CZ) gate to a pair of qubits.

  $$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.
ms.openlocfilehash: cef1544fb76d561cfd0949c84c487550d523bb85
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840710"
---
# <a name="cz-operation"></a><span data-ttu-id="65b02-102">CZ 操作</span><span class="sxs-lookup"><span data-stu-id="65b02-102">CZ operation</span></span>

<span data-ttu-id="65b02-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="65b02-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="65b02-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="65b02-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="65b02-105">将受控-Z (CZ) 入口应用于一对 qubits。</span><span class="sxs-lookup"><span data-stu-id="65b02-105">Applies the controlled-Z (CZ) gate to a pair of qubits.</span></span>

<span data-ttu-id="65b02-106">$ $ \begin{align} 1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 0 & 0 &-1 \end{align}，$ $，其中的行和列组织为 "量程概念" 指南。</span><span class="sxs-lookup"><span data-stu-id="65b02-106">$$ \begin{align} 1 & 0 & 0 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 0 & 0 & -1 \end{align}, $$ where rows and columns are organized as in the quantum concepts guide.</span></span>

```qsharp
operation CZ (control : Qubit, target : Qubit) : Unit is Adj + Ctl
```


## <a name="input"></a><span data-ttu-id="65b02-107">输入</span><span class="sxs-lookup"><span data-stu-id="65b02-107">Input</span></span>

### <a name="control--qubit"></a><span data-ttu-id="65b02-108">控件： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="65b02-108">control : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="65b02-109">控制 CZ 入口的 qubit。</span><span class="sxs-lookup"><span data-stu-id="65b02-109">Control qubit for the CZ gate.</span></span>


### <a name="target--qubit"></a><span data-ttu-id="65b02-110">目标： [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="65b02-110">target : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="65b02-111">CZ 入口的目标 qubit。</span><span class="sxs-lookup"><span data-stu-id="65b02-111">Target qubit for the CZ gate.</span></span>



## <a name="output--unit"></a><span data-ttu-id="65b02-112">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="65b02-112">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="65b02-113">备注</span><span class="sxs-lookup"><span data-stu-id="65b02-113">Remarks</span></span>

<span data-ttu-id="65b02-114">等效于：</span><span class="sxs-lookup"><span data-stu-id="65b02-114">Equivalent to:</span></span>

```qsharp
Controlled Z([control], target);
```