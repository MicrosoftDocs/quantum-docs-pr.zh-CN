---
uid: Microsoft.Quantum.Canon.ApplyIfOneCA
title: ApplyIfOneCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneCA
qsharp.summary: Applies a unitary operation conditioned on a classical result value being one.
ms.openlocfilehash: 973dd3c5f9f3e9ad03c0626a38779f499b7ce657
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696325"
---
# <a name="applyifoneca-operation"></a><span data-ttu-id="9e338-102">ApplyIfOneCA 操作</span><span class="sxs-lookup"><span data-stu-id="9e338-102">ApplyIfOneCA operation</span></span>

<span data-ttu-id="9e338-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9e338-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9e338-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9e338-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9e338-105">将一个条件为的单一操作应用于传统结果值为1的值。</span><span class="sxs-lookup"><span data-stu-id="9e338-105">Applies a unitary operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOneCA<'T> (result : Result, (op : ('T => Unit is Adj + Ctl), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="9e338-106">说明</span><span class="sxs-lookup"><span data-stu-id="9e338-106">Description</span></span>

<span data-ttu-id="9e338-107">给定一个操作 `op` 和一个结果值时 `result` ， `op` `target` 如果为， `result` 则应用于 `One` 。</span><span class="sxs-lookup"><span data-stu-id="9e338-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="9e338-108">如果 `Zero` 为，则不会发生任何事情 `target` 。</span><span class="sxs-lookup"><span data-stu-id="9e338-108">If `Zero`, nothing happens to the `target`.</span></span>
<span data-ttu-id="9e338-109">后缀 `CA` 指示要应用的操作是单一 (可控和 adjointable) 。</span><span class="sxs-lookup"><span data-stu-id="9e338-109">The suffix `CA` indicates that the operation to be applied is unitary (controllable and adjointable).</span></span>

## <a name="input"></a><span data-ttu-id="9e338-110">输入</span><span class="sxs-lookup"><span data-stu-id="9e338-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="9e338-111">结果： __无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="9e338-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="9e338-112">用于控制是否应用 op 的测量结果。</span><span class="sxs-lookup"><span data-stu-id="9e338-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit-adj--ctl"></a><span data-ttu-id="9e338-113">op： t => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="9e338-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="9e338-114">要有条件地应用的操作。</span><span class="sxs-lookup"><span data-stu-id="9e338-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="9e338-115">目标： t</span><span class="sxs-lookup"><span data-stu-id="9e338-115">target : 'T</span></span>

<span data-ttu-id="9e338-116">将操作应用到的输入。</span><span class="sxs-lookup"><span data-stu-id="9e338-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9e338-117">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9e338-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9e338-118">类型参数</span><span class="sxs-lookup"><span data-stu-id="9e338-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9e338-119">找</span><span class="sxs-lookup"><span data-stu-id="9e338-119">'T</span></span>

<span data-ttu-id="9e338-120">要有条件地应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="9e338-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="9e338-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9e338-121">See Also</span></span>

- [<span data-ttu-id="9e338-122">Canon. ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="9e338-122">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="9e338-123">Canon. ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="9e338-123">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="9e338-124">Canon. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="9e338-124">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)