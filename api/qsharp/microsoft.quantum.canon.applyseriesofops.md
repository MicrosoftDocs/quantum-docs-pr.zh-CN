---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOps
title: ApplySeriesOfOps 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOps
qsharp.summary: Applies a list of ops and their targets sequentially on an array.
ms.openlocfilehash: aff0bcb831960153166e88aef1f05e000125d5d8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696268"
---
# <a name="applyseriesofops-operation"></a><span data-ttu-id="2199a-102">ApplySeriesOfOps 操作</span><span class="sxs-lookup"><span data-stu-id="2199a-102">ApplySeriesOfOps operation</span></span>

<span data-ttu-id="2199a-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2199a-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2199a-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2199a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2199a-105">在数组上按顺序应用 ops 及其目标的列表。</span><span class="sxs-lookup"><span data-stu-id="2199a-105">Applies a list of ops and their targets sequentially on an array.</span></span>

```qsharp
operation ApplySeriesOfOps<'T> (listOfOps : ('T[] => Unit)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="2199a-106">输入</span><span class="sxs-lookup"><span data-stu-id="2199a-106">Input</span></span>

### <a name="listofops--t--unit-"></a><span data-ttu-id="2199a-107">listOfOps： t [] => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span><span class="sxs-lookup"><span data-stu-id="2199a-107">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span></span>

<span data-ttu-id="2199a-108">要应用的 ops 列表，每个操作都采用 "t" 数组。</span><span class="sxs-lookup"><span data-stu-id="2199a-108">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="2199a-109">它们按顺序应用，最小索引优先。</span><span class="sxs-lookup"><span data-stu-id="2199a-109">They are applied sequentially, lowest index first.</span></span>


### <a name="targets--int"></a><span data-ttu-id="2199a-110">目标： [Int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="2199a-110">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="2199a-111">描述 op 目标的嵌套数组。</span><span class="sxs-lookup"><span data-stu-id="2199a-111">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="2199a-112">每个数组都应包含一个整数列表，其中包含描述要使用的索引的整数。</span><span class="sxs-lookup"><span data-stu-id="2199a-112">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="2199a-113">注册： t []</span><span class="sxs-lookup"><span data-stu-id="2199a-113">register : 'T[]</span></span>

<span data-ttu-id="2199a-114">要对其进行操作的 Qubit 寄存器。</span><span class="sxs-lookup"><span data-stu-id="2199a-114">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="2199a-115">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2199a-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2199a-116">类型参数</span><span class="sxs-lookup"><span data-stu-id="2199a-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2199a-117">找</span><span class="sxs-lookup"><span data-stu-id="2199a-117">'T</span></span>



## <a name="see-also"></a><span data-ttu-id="2199a-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2199a-118">See Also</span></span>

- [<span data-ttu-id="2199a-119">Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="2199a-119">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)