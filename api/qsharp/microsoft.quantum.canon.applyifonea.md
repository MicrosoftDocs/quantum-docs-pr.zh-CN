---
uid: Microsoft.Quantum.Canon.ApplyIfOneA
title: ApplyIfOneA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneA
qsharp.summary: Applies an adjointable operation conditioned on a classical result value being one.
ms.openlocfilehash: 1593f565e950a9410df0ae9de59e6d0e6a7b99b0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844928"
---
# <a name="applyifonea-operation"></a><span data-ttu-id="0a9f4-102">ApplyIfOneA 操作</span><span class="sxs-lookup"><span data-stu-id="0a9f4-102">ApplyIfOneA operation</span></span>

<span data-ttu-id="0a9f4-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="0a9f4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="0a9f4-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0a9f4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0a9f4-105">应用一个 adjointable 操作，该操作可将传统结果值视为1。</span><span class="sxs-lookup"><span data-stu-id="0a9f4-105">Applies an adjointable operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOneA<'T> (result : Result, (op : ('T => Unit is Adj), target : 'T)) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="0a9f4-106">说明</span><span class="sxs-lookup"><span data-stu-id="0a9f4-106">Description</span></span>

<span data-ttu-id="0a9f4-107">给定一个操作 `op` 和一个结果值时 `result` ， `op` `target` 如果为， `result` 则应用于 `One` 。</span><span class="sxs-lookup"><span data-stu-id="0a9f4-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="0a9f4-108">如果 `Zero` 为，则不会发生任何事情 `target` 。</span><span class="sxs-lookup"><span data-stu-id="0a9f4-108">If `Zero`, nothing happens to the `target`.</span></span>
<span data-ttu-id="0a9f4-109">后缀 `A` 指示要应用的操作是 adjointable。</span><span class="sxs-lookup"><span data-stu-id="0a9f4-109">The suffix `A` indicates that the operation to be applied is adjointable.</span></span>

## <a name="input"></a><span data-ttu-id="0a9f4-110">输入</span><span class="sxs-lookup"><span data-stu-id="0a9f4-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="0a9f4-111">结果：__无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="0a9f4-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="0a9f4-112">用于控制是否应用 op 的测量结果。</span><span class="sxs-lookup"><span data-stu-id="0a9f4-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit--is-adj"></a><span data-ttu-id="0a9f4-113">op： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词</span><span class="sxs-lookup"><span data-stu-id="0a9f4-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="0a9f4-114">要有条件地应用的操作。</span><span class="sxs-lookup"><span data-stu-id="0a9f4-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="0a9f4-115">目标： t</span><span class="sxs-lookup"><span data-stu-id="0a9f4-115">target : 'T</span></span>

<span data-ttu-id="0a9f4-116">将操作应用到的输入。</span><span class="sxs-lookup"><span data-stu-id="0a9f4-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="0a9f4-117">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="0a9f4-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="0a9f4-118">类型参数</span><span class="sxs-lookup"><span data-stu-id="0a9f4-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0a9f4-119">找</span><span class="sxs-lookup"><span data-stu-id="0a9f4-119">'T</span></span>

<span data-ttu-id="0a9f4-120">要有条件地应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="0a9f4-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="0a9f4-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0a9f4-121">See Also</span></span>

- [<span data-ttu-id="0a9f4-122">Canon. ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="0a9f4-122">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="0a9f4-123">Canon. ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="0a9f4-123">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="0a9f4-124">Canon. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="0a9f4-124">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)