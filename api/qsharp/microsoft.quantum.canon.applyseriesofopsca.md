---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsCA
title: ApplySeriesOfOpsCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsCA
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Adjoint + Controlled)
ms.openlocfilehash: 2327a693e528cf46f95eae5ee052e9dd9b6ee187
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696263"
---
# <a name="applyseriesofopsca-operation"></a><span data-ttu-id="02070-102">ApplySeriesOfOpsCA 操作</span><span class="sxs-lookup"><span data-stu-id="02070-102">ApplySeriesOfOpsCA operation</span></span>

<span data-ttu-id="02070-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="02070-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="02070-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="02070-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="02070-105">在数组上按顺序应用 ops 及其目标的列表。</span><span class="sxs-lookup"><span data-stu-id="02070-105">Applies a list of ops and their targets sequentially on an array.</span></span> <span data-ttu-id="02070-106"> (Adjoint + 受控) </span><span class="sxs-lookup"><span data-stu-id="02070-106">(Adjoint + Controlled)</span></span>

```qsharp
operation ApplySeriesOfOpsCA<'T> (listOfOps : ('T[] => Unit is Adj + Ctl)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="02070-107">输入</span><span class="sxs-lookup"><span data-stu-id="02070-107">Input</span></span>

### <a name="listofops--t--unit-adj--ctl"></a><span data-ttu-id="02070-108">listOfOps： t [] => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl []</span><span class="sxs-lookup"><span data-stu-id="02070-108">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl[]</span></span>

<span data-ttu-id="02070-109">要应用的 ops 列表，每个操作都采用 "t" 数组。</span><span class="sxs-lookup"><span data-stu-id="02070-109">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="02070-110">它们按顺序应用，最小索引优先。</span><span class="sxs-lookup"><span data-stu-id="02070-110">They are applied sequentially, lowest index first.</span></span>
<span data-ttu-id="02070-111">每个都必须同时具有 Adjoint 和受控函子。</span><span class="sxs-lookup"><span data-stu-id="02070-111">Each must have both an Adjoint and Controlled functor.</span></span>


### <a name="targets--int"></a><span data-ttu-id="02070-112">目标： [Int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="02070-112">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="02070-113">描述 op 目标的嵌套数组。</span><span class="sxs-lookup"><span data-stu-id="02070-113">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="02070-114">每个数组都应包含一个整数列表，其中包含描述要使用的索引的整数。</span><span class="sxs-lookup"><span data-stu-id="02070-114">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="02070-115">注册： t []</span><span class="sxs-lookup"><span data-stu-id="02070-115">register : 'T[]</span></span>

<span data-ttu-id="02070-116">要对其进行操作的 Qubit 寄存器。</span><span class="sxs-lookup"><span data-stu-id="02070-116">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="02070-117">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="02070-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="02070-118">类型参数</span><span class="sxs-lookup"><span data-stu-id="02070-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="02070-119">找</span><span class="sxs-lookup"><span data-stu-id="02070-119">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="02070-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="02070-120">See Also</span></span>

- [<span data-ttu-id="02070-121">Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="02070-121">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)