---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOps
title: ApplySeriesOfOps 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOps
qsharp.summary: Applies a list of ops and their targets sequentially on an array.
ms.openlocfilehash: b086b01b0be86bd25a6d6cdef26bfbb53e484cb2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841502"
---
# <a name="applyseriesofops-operation"></a><span data-ttu-id="6f5c2-102">ApplySeriesOfOps 操作</span><span class="sxs-lookup"><span data-stu-id="6f5c2-102">ApplySeriesOfOps operation</span></span>

<span data-ttu-id="6f5c2-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="6f5c2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="6f5c2-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6f5c2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6f5c2-105">在数组上按顺序应用 ops 及其目标的列表。</span><span class="sxs-lookup"><span data-stu-id="6f5c2-105">Applies a list of ops and their targets sequentially on an array.</span></span>

```qsharp
operation ApplySeriesOfOps<'T> (listOfOps : ('T[] => Unit)[], targets : Int[][], register : 'T[]) : Unit
```


## <a name="input"></a><span data-ttu-id="6f5c2-106">输入</span><span class="sxs-lookup"><span data-stu-id="6f5c2-106">Input</span></span>

### <a name="listofops--t--unit-"></a><span data-ttu-id="6f5c2-107">listOfOps： t [] => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span><span class="sxs-lookup"><span data-stu-id="6f5c2-107">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) []</span></span>

<span data-ttu-id="6f5c2-108">要应用的 ops 列表，每个操作都采用 "t" 数组。</span><span class="sxs-lookup"><span data-stu-id="6f5c2-108">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="6f5c2-109">它们按顺序应用，最小索引优先。</span><span class="sxs-lookup"><span data-stu-id="6f5c2-109">They are applied sequentially, lowest index first.</span></span>


### <a name="targets--int"></a><span data-ttu-id="6f5c2-110">目标： [Int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="6f5c2-110">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="6f5c2-111">描述 op 目标的嵌套数组。</span><span class="sxs-lookup"><span data-stu-id="6f5c2-111">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="6f5c2-112">每个数组都应包含一个整数列表，其中包含描述要使用的索引的整数。</span><span class="sxs-lookup"><span data-stu-id="6f5c2-112">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="6f5c2-113">注册： t []</span><span class="sxs-lookup"><span data-stu-id="6f5c2-113">register : 'T[]</span></span>

<span data-ttu-id="6f5c2-114">要对其进行操作的 Qubit 寄存器。</span><span class="sxs-lookup"><span data-stu-id="6f5c2-114">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="6f5c2-115">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="6f5c2-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6f5c2-116">类型参数</span><span class="sxs-lookup"><span data-stu-id="6f5c2-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6f5c2-117">找</span><span class="sxs-lookup"><span data-stu-id="6f5c2-117">'T</span></span>



## <a name="example"></a><span data-ttu-id="6f5c2-118">示例</span><span class="sxs-lookup"><span data-stu-id="6f5c2-118">Example</span></span>

<span data-ttu-id="6f5c2-119">以下应用了 Exp ( [PauliX，PauliY]，0.5) 到 qubits 0，1//then X 到 qubit 2 let ops = [Exp ( [PauliX，PauliY]，0.5，_) ，ApplyToFirstQubit (X，_) ];let 索引 = [[0，1]，[2]];ApplySeriesOfOps (ops，索引，qubitArray) ;</span><span class="sxs-lookup"><span data-stu-id="6f5c2-119">// The following applies Exp([PauliX, PauliY], 0.5) to qubits 0, 1 // then X to qubit 2 let ops = [Exp([PauliX, PauliY], 0.5, _), ApplyToFirstQubit(X, _)]; let indices = [[0, 1], [2]]; ApplySeriesOfOps(ops, indices, qubitArray);</span></span>

## <a name="see-also"></a><span data-ttu-id="6f5c2-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6f5c2-120">See Also</span></span>

- [<span data-ttu-id="6f5c2-121">Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="6f5c2-121">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)