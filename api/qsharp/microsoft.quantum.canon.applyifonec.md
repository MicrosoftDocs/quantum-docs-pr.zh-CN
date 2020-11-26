---
uid: Microsoft.Quantum.Canon.ApplyIfOneC
title: ApplyIfOneC 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneC
qsharp.summary: Applies a controllable operation conditioned on a classical result value being one.
ms.openlocfilehash: 24a00d83c1bbe6b07adb27c58fc70bc76af0a910
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209411"
---
# <a name="applyifonec-operation"></a><span data-ttu-id="f3336-102">ApplyIfOneC 操作</span><span class="sxs-lookup"><span data-stu-id="f3336-102">ApplyIfOneC operation</span></span>

<span data-ttu-id="f3336-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f3336-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f3336-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f3336-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f3336-105">应用以传统结果值为一的可控操作。</span><span class="sxs-lookup"><span data-stu-id="f3336-105">Applies a controllable operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOneC<'T> (result : Result, (op : ('T => Unit is Ctl), target : 'T)) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="f3336-106">描述</span><span class="sxs-lookup"><span data-stu-id="f3336-106">Description</span></span>

<span data-ttu-id="f3336-107">给定一个操作 `op` 和一个结果值时 `result` ， `op` `target` 如果为， `result` 则应用于 `One` 。</span><span class="sxs-lookup"><span data-stu-id="f3336-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="f3336-108">如果 `Zero` 为，则不会发生任何事情 `target` 。</span><span class="sxs-lookup"><span data-stu-id="f3336-108">If `Zero`, nothing happens to the `target`.</span></span>
<span data-ttu-id="f3336-109">后缀 `C` 指示要应用的操作可控制。</span><span class="sxs-lookup"><span data-stu-id="f3336-109">The suffix `C` indicates that the operation to be applied is controllable.</span></span>

## <a name="input"></a><span data-ttu-id="f3336-110">输入</span><span class="sxs-lookup"><span data-stu-id="f3336-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="f3336-111">结果：__无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="f3336-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="f3336-112">用于控制是否应用 op 的测量结果。</span><span class="sxs-lookup"><span data-stu-id="f3336-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="f3336-113">op： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为 Ctl</span><span class="sxs-lookup"><span data-stu-id="f3336-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="f3336-114">要有条件地应用的操作。</span><span class="sxs-lookup"><span data-stu-id="f3336-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="f3336-115">目标： t</span><span class="sxs-lookup"><span data-stu-id="f3336-115">target : 'T</span></span>

<span data-ttu-id="f3336-116">将操作应用到的输入。</span><span class="sxs-lookup"><span data-stu-id="f3336-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f3336-117">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f3336-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f3336-118">类型参数</span><span class="sxs-lookup"><span data-stu-id="f3336-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f3336-119">找</span><span class="sxs-lookup"><span data-stu-id="f3336-119">'T</span></span>

<span data-ttu-id="f3336-120">要有条件地应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="f3336-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="f3336-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f3336-121">See Also</span></span>

- [<span data-ttu-id="f3336-122">Canon. ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="f3336-122">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="f3336-123">Canon. ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="f3336-123">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="f3336-124">Canon. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="f3336-124">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)