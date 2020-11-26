---
uid: Microsoft.Quantum.Arrays._SwapOrderToPermuteArray
title: _SwapOrderToPermuteArray 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: _SwapOrderToPermuteArray
qsharp.summary: Returns the order elements in an array need to be swapped to produce an ordered array. Assumes swaps occur in place.
ms.openlocfilehash: 9df2ec00d91c1124fae960efd15d576b15b0223c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221702"
---
# <a name="_swapordertopermutearray-function"></a><span data-ttu-id="11975-102">_SwapOrderToPermuteArray 函数</span><span class="sxs-lookup"><span data-stu-id="11975-102">_SwapOrderToPermuteArray function</span></span>

<span data-ttu-id="11975-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="11975-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="11975-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="11975-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="11975-105">返回数组中的 order 元素需要进行交换，以生成有序的数组。</span><span class="sxs-lookup"><span data-stu-id="11975-105">Returns the order elements in an array need to be swapped to produce an ordered array.</span></span>
<span data-ttu-id="11975-106">假设发生了交换。</span><span class="sxs-lookup"><span data-stu-id="11975-106">Assumes swaps occur in place.</span></span>

```qsharp
function _SwapOrderToPermuteArray (newOrder : Int[]) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="11975-107">输入</span><span class="sxs-lookup"><span data-stu-id="11975-107">Input</span></span>

### <a name="neworder--int"></a><span data-ttu-id="11975-108">newOrder： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="11975-108">newOrder : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="11975-109">数组，其中包含新数组的索引。</span><span class="sxs-lookup"><span data-stu-id="11975-109">Array with the permutation of the indices of the new array.</span></span> <span data-ttu-id="11975-110">应该存在 $n $ 个元素，每个元素都是 $0 $ 到 $n-$1 的唯一整数。</span><span class="sxs-lookup"><span data-stu-id="11975-110">There should be $n$ elements, each being a unique integer from $0$ to $n-1$.</span></span>



## <a name="output--intint"></a><span data-ttu-id="11975-111">Output： ([int](xref:microsoft.quantum.lang-ref.int)，[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="11975-111">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="11975-112">元组表示要交换的两个索引。</span><span class="sxs-lookup"><span data-stu-id="11975-112">The tuple represents the two indices to be swapped.</span></span> <span data-ttu-id="11975-113">交换从最低索引开始。</span><span class="sxs-lookup"><span data-stu-id="11975-113">The swaps begin at the lowest index.</span></span>

## <a name="remarks"></a><span data-ttu-id="11975-114">备注</span><span class="sxs-lookup"><span data-stu-id="11975-114">Remarks</span></span>

## <a name="psuedocode"></a><span data-ttu-id="11975-115">Psuedocode</span><span class="sxs-lookup"><span data-stu-id="11975-115">Psuedocode</span></span>

<span data-ttu-id="11975-116">对于 0.. Length 中的 (索引 (newOrder) -1) {while newOrder [index]！ = index {Switch newOrder [index] with newOrder [newOrder [index]]}}</span><span class="sxs-lookup"><span data-stu-id="11975-116">for (index in 0..Length(newOrder) - 1) { while newOrder[index] != index { Switch newOrder[index] with newOrder[newOrder[index]] } }</span></span>