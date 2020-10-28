---
uid: Microsoft.Quantum.Canon.ApplyIfOne
title: ApplyIfOne 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOne
qsharp.summary: Applies an operation conditioned on a classical result value being one.
ms.openlocfilehash: 8c668423d126f02736bcb541e73e210a761c5719
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696330"
---
# <a name="applyifone-operation"></a><span data-ttu-id="58802-102">ApplyIfOne 操作</span><span class="sxs-lookup"><span data-stu-id="58802-102">ApplyIfOne operation</span></span>

<span data-ttu-id="58802-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="58802-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="58802-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="58802-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="58802-105">应用对经典结果值为1的操作。</span><span class="sxs-lookup"><span data-stu-id="58802-105">Applies an operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOne<'T> (result : Result, (op : ('T => Unit), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="58802-106">说明</span><span class="sxs-lookup"><span data-stu-id="58802-106">Description</span></span>

<span data-ttu-id="58802-107">给定一个操作 `op` 和一个结果值时 `result` ， `op` `target` 如果为， `result` 则应用于 `One` 。</span><span class="sxs-lookup"><span data-stu-id="58802-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="58802-108">如果 `Zero` 为，则不会发生任何事情 `target` 。</span><span class="sxs-lookup"><span data-stu-id="58802-108">If `Zero`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="58802-109">输入</span><span class="sxs-lookup"><span data-stu-id="58802-109">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="58802-110">结果： __无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="58802-110">result : __invalid<Result>__</span></span>

<span data-ttu-id="58802-111">用于控制是否应用 op 的测量结果。</span><span class="sxs-lookup"><span data-stu-id="58802-111">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="58802-112">op： t => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="58802-112">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="58802-113">要有条件地应用的操作。</span><span class="sxs-lookup"><span data-stu-id="58802-113">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="58802-114">目标： t</span><span class="sxs-lookup"><span data-stu-id="58802-114">target : 'T</span></span>

<span data-ttu-id="58802-115">将操作应用到的输入。</span><span class="sxs-lookup"><span data-stu-id="58802-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="58802-116">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="58802-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="58802-117">类型参数</span><span class="sxs-lookup"><span data-stu-id="58802-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="58802-118">找</span><span class="sxs-lookup"><span data-stu-id="58802-118">'T</span></span>

<span data-ttu-id="58802-119">要有条件地应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="58802-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="58802-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="58802-120">See Also</span></span>

- [<span data-ttu-id="58802-121">Canon. ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="58802-121">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="58802-122">Canon. ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="58802-122">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="58802-123">Canon. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="58802-123">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)