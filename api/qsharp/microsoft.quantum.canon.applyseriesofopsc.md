---
uid: Microsoft.Quantum.Canon.ApplySeriesOfOpsC
title: ApplySeriesOfOpsC 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplySeriesOfOpsC
qsharp.summary: Applies a list of ops and their targets sequentially on an array. (Controlled)
ms.openlocfilehash: 308256833dc607f685e3a5f2278e374cf3b6ce22
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844651"
---
# <a name="applyseriesofopsc-operation"></a><span data-ttu-id="f88e1-102">ApplySeriesOfOpsC 操作</span><span class="sxs-lookup"><span data-stu-id="f88e1-102">ApplySeriesOfOpsC operation</span></span>

<span data-ttu-id="f88e1-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f88e1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f88e1-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f88e1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f88e1-105">在数组上按顺序应用 ops 及其目标的列表。</span><span class="sxs-lookup"><span data-stu-id="f88e1-105">Applies a list of ops and their targets sequentially on an array.</span></span> <span data-ttu-id="f88e1-106"> (控制) </span><span class="sxs-lookup"><span data-stu-id="f88e1-106">(Controlled)</span></span>

```qsharp
operation ApplySeriesOfOpsC<'T> (listOfOps : ('T[] => Unit is Ctl)[], targets : Int[][], register : 'T[]) : Unit is Ctl
```


## <a name="input"></a><span data-ttu-id="f88e1-107">输入</span><span class="sxs-lookup"><span data-stu-id="f88e1-107">Input</span></span>

### <a name="listofops--t--unit--is-ctl"></a><span data-ttu-id="f88e1-108">listOfOps： t [] => [Unit](xref:microsoft.quantum.lang-ref.unit)  为 Ctl []</span><span class="sxs-lookup"><span data-stu-id="f88e1-108">listOfOps : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl[]</span></span>

<span data-ttu-id="f88e1-109">要应用的 ops 列表，每个操作都采用 "t" 数组。</span><span class="sxs-lookup"><span data-stu-id="f88e1-109">List of ops, each taking a 'T array, to be applied.</span></span> <span data-ttu-id="f88e1-110">它们按顺序应用，最小索引优先。</span><span class="sxs-lookup"><span data-stu-id="f88e1-110">They are applied sequentially, lowest index first.</span></span>
<span data-ttu-id="f88e1-111">每个必须具有受控函子</span><span class="sxs-lookup"><span data-stu-id="f88e1-111">Each must have a Controlled functor</span></span>


### <a name="targets--int"></a><span data-ttu-id="f88e1-112">目标： [Int](xref:microsoft.quantum.lang-ref.int)[] []</span><span class="sxs-lookup"><span data-stu-id="f88e1-112">targets : [Int](xref:microsoft.quantum.lang-ref.int)[][]</span></span>

<span data-ttu-id="f88e1-113">描述 op 目标的嵌套数组。</span><span class="sxs-lookup"><span data-stu-id="f88e1-113">Nested arrays describing the targets of the op.</span></span> <span data-ttu-id="f88e1-114">每个数组都应包含一个整数列表，其中包含描述要使用的索引的整数。</span><span class="sxs-lookup"><span data-stu-id="f88e1-114">Each array should contain a list of ints describing the indices to be used.</span></span>


### <a name="register--t"></a><span data-ttu-id="f88e1-115">注册： t []</span><span class="sxs-lookup"><span data-stu-id="f88e1-115">register : 'T[]</span></span>

<span data-ttu-id="f88e1-116">要对其进行操作的 Qubit 寄存器。</span><span class="sxs-lookup"><span data-stu-id="f88e1-116">Qubit register to be acted upon.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f88e1-117">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f88e1-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f88e1-118">类型参数</span><span class="sxs-lookup"><span data-stu-id="f88e1-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f88e1-119">找</span><span class="sxs-lookup"><span data-stu-id="f88e1-119">'T</span></span>



## <a name="example"></a><span data-ttu-id="f88e1-120">示例</span><span class="sxs-lookup"><span data-stu-id="f88e1-120">Example</span></span>

<span data-ttu-id="f88e1-121">以下应用了 Exp ( [PauliX，PauliY]，0.5) 到 qubits 0，1//then X 到 qubit 2 let ops = [Exp ( [PauliX，PauliY]，0.5，_) ，ApplyToFirstQubitC (X，_) ];let 索引 = [[0，1]，[2]];ApplySeriesOfOpsC (ops，索引，qubitArray) ;</span><span class="sxs-lookup"><span data-stu-id="f88e1-121">// The following applies Exp([PauliX, PauliY], 0.5) to qubits 0, 1 // then X to qubit 2 let ops = [Exp([PauliX, PauliY], 0.5, _), ApplyToFirstQubitC(X, _)]; let indices = [[0, 1], [2]]; ApplySeriesOfOpsC(ops, indices, qubitArray);</span></span>

## <a name="see-also"></a><span data-ttu-id="f88e1-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f88e1-122">See Also</span></span>

- [<span data-ttu-id="f88e1-123">Canon. ApplyOpRepeatedlyOver</span><span class="sxs-lookup"><span data-stu-id="f88e1-123">Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver</span></span>](xref:Microsoft.Quantum.Canon.ApplyOpRepeatedlyOver)