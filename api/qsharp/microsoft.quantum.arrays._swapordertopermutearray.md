---
uid: Microsoft.Quantum.Arrays._SwapOrderToPermuteArray
title: _SwapOrderToPermuteArray 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: _SwapOrderToPermuteArray
qsharp.summary: Returns the order elements in an array need to be swapped to produce an ordered array. Assumes swaps occur in place.
ms.openlocfilehash: 965f2f3d4f8b366abb27287ce0d27a3b7d7b8fb8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696559"
---
# <a name="_swapordertopermutearray-function"></a><span data-ttu-id="e06c6-102">_SwapOrderToPermuteArray 函数</span><span class="sxs-lookup"><span data-stu-id="e06c6-102">_SwapOrderToPermuteArray function</span></span>

<span data-ttu-id="e06c6-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e06c6-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e06c6-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e06c6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e06c6-105">返回数组中的 order 元素需要进行交换，以生成有序的数组。</span><span class="sxs-lookup"><span data-stu-id="e06c6-105">Returns the order elements in an array need to be swapped to produce an ordered array.</span></span>
<span data-ttu-id="e06c6-106">假设发生了交换。</span><span class="sxs-lookup"><span data-stu-id="e06c6-106">Assumes swaps occur in place.</span></span>

```qsharp
function _SwapOrderToPermuteArray (newOrder : Int[]) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="e06c6-107">输入</span><span class="sxs-lookup"><span data-stu-id="e06c6-107">Input</span></span>

### <a name="neworder--int"></a><span data-ttu-id="e06c6-108">newOrder： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="e06c6-108">newOrder : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="e06c6-109">数组，其中包含新数组的索引。</span><span class="sxs-lookup"><span data-stu-id="e06c6-109">Array with the permutation of the indices of the new array.</span></span> <span data-ttu-id="e06c6-110">应该存在 $n $ 个元素，每个元素都是 $0 $ 到 $n-$1 的唯一整数。</span><span class="sxs-lookup"><span data-stu-id="e06c6-110">There should be $n$ elements, each being a unique integer from $0$ to $n-1$.</span></span>



## <a name="output--intint"></a><span data-ttu-id="e06c6-111">Output： ([int](xref:microsoft.quantum.lang-ref.int)，[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="e06c6-111">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="e06c6-112">元组表示要交换的两个索引。</span><span class="sxs-lookup"><span data-stu-id="e06c6-112">The tuple represents the two indices to be swapped.</span></span> <span data-ttu-id="e06c6-113">交换从最低索引开始。</span><span class="sxs-lookup"><span data-stu-id="e06c6-113">The swaps begin at the lowest index.</span></span>

## <a name="remarks"></a><span data-ttu-id="e06c6-114">注解</span><span class="sxs-lookup"><span data-stu-id="e06c6-114">Remarks</span></span>

## <a name="psuedocode"></a><span data-ttu-id="e06c6-115">Psuedocode</span><span class="sxs-lookup"><span data-stu-id="e06c6-115">Psuedocode</span></span>

<span data-ttu-id="e06c6-116">对于 0.. Length 中的 (索引 (newOrder) -1) {while newOrder [index]！ = index {Switch newOrder [index] with newOrder [newOrder [index]]}}</span><span class="sxs-lookup"><span data-stu-id="e06c6-116">for (index in 0..Length(newOrder) - 1) { while newOrder[index] != index { Switch newOrder[index] with newOrder[newOrder[index]] } }</span></span>