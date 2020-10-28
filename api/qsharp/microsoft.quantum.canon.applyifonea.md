---
uid: Microsoft.Quantum.Canon.ApplyIfOneA
title: ApplyIfOneA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneA
qsharp.summary: Applies an adjointable operation conditioned on a classical result value being one.
ms.openlocfilehash: 76c15aba6042c2801ecfe8470e82099c54ba3846
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696329"
---
# <a name="applyifonea-operation"></a><span data-ttu-id="7fc93-102">ApplyIfOneA 操作</span><span class="sxs-lookup"><span data-stu-id="7fc93-102">ApplyIfOneA operation</span></span>

<span data-ttu-id="7fc93-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7fc93-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7fc93-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7fc93-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7fc93-105">应用一个 adjointable 操作，该操作可将传统结果值视为1。</span><span class="sxs-lookup"><span data-stu-id="7fc93-105">Applies an adjointable operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOneA<'T> (result : Result, (op : ('T => Unit is Adj), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="7fc93-106">说明</span><span class="sxs-lookup"><span data-stu-id="7fc93-106">Description</span></span>

<span data-ttu-id="7fc93-107">给定一个操作 `op` 和一个结果值时 `result` ， `op` `target` 如果为， `result` 则应用于 `One` 。</span><span class="sxs-lookup"><span data-stu-id="7fc93-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="7fc93-108">如果 `Zero` 为，则不会发生任何事情 `target` 。</span><span class="sxs-lookup"><span data-stu-id="7fc93-108">If `Zero`, nothing happens to the `target`.</span></span>
<span data-ttu-id="7fc93-109">后缀 `A` 指示要应用的操作是 adjointable。</span><span class="sxs-lookup"><span data-stu-id="7fc93-109">The suffix `A` indicates that the operation to be applied is adjointable.</span></span>

## <a name="input"></a><span data-ttu-id="7fc93-110">输入</span><span class="sxs-lookup"><span data-stu-id="7fc93-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="7fc93-111">结果： __无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="7fc93-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="7fc93-112">用于控制是否应用 op 的测量结果。</span><span class="sxs-lookup"><span data-stu-id="7fc93-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit-adj"></a><span data-ttu-id="7fc93-113">op： t => [单位](xref:microsoft.quantum.lang-ref.unit) 形容词</span><span class="sxs-lookup"><span data-stu-id="7fc93-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="7fc93-114">要有条件地应用的操作。</span><span class="sxs-lookup"><span data-stu-id="7fc93-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="7fc93-115">目标： t</span><span class="sxs-lookup"><span data-stu-id="7fc93-115">target : 'T</span></span>

<span data-ttu-id="7fc93-116">将操作应用到的输入。</span><span class="sxs-lookup"><span data-stu-id="7fc93-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7fc93-117">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7fc93-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7fc93-118">类型参数</span><span class="sxs-lookup"><span data-stu-id="7fc93-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7fc93-119">找</span><span class="sxs-lookup"><span data-stu-id="7fc93-119">'T</span></span>

<span data-ttu-id="7fc93-120">要有条件地应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="7fc93-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="7fc93-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7fc93-121">See Also</span></span>

- [<span data-ttu-id="7fc93-122">Canon. ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="7fc93-122">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="7fc93-123">Canon. ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="7fc93-123">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="7fc93-124">Canon. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="7fc93-124">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)