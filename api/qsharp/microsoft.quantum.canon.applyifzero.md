---
uid: Microsoft.Quantum.Canon.ApplyIfZero
title: ApplyIfZero 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZero
qsharp.summary: Applies an operation conditioned on a classical result value being zero.
ms.openlocfilehash: 7435150937143a8d1a67afe334b683932a9655de
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696324"
---
# <a name="applyifzero-operation"></a><span data-ttu-id="63954-102">ApplyIfZero 操作</span><span class="sxs-lookup"><span data-stu-id="63954-102">ApplyIfZero operation</span></span>

<span data-ttu-id="63954-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="63954-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="63954-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="63954-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="63954-105">应用对传统结果值为零的操作。</span><span class="sxs-lookup"><span data-stu-id="63954-105">Applies an operation conditioned on a classical result value being zero.</span></span>

```qsharp
operation ApplyIfZero<'T> (result : Result, (op : ('T => Unit), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="63954-106">说明</span><span class="sxs-lookup"><span data-stu-id="63954-106">Description</span></span>

<span data-ttu-id="63954-107">给定一个操作 `op` 和一个结果值时 `result` ， `op` `target` 如果为， `result` 则应用于 `Zero` 。</span><span class="sxs-lookup"><span data-stu-id="63954-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `Zero`.</span></span> <span data-ttu-id="63954-108">如果 `One` 为，则不会发生任何事情 `target` 。</span><span class="sxs-lookup"><span data-stu-id="63954-108">If `One`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="63954-109">输入</span><span class="sxs-lookup"><span data-stu-id="63954-109">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="63954-110">结果： __无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="63954-110">result : __invalid<Result>__</span></span>

<span data-ttu-id="63954-111">用于控制是否应用 op 的测量结果。</span><span class="sxs-lookup"><span data-stu-id="63954-111">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="63954-112">op： t => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="63954-112">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="63954-113">要有条件地应用的操作。</span><span class="sxs-lookup"><span data-stu-id="63954-113">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="63954-114">目标： t</span><span class="sxs-lookup"><span data-stu-id="63954-114">target : 'T</span></span>

<span data-ttu-id="63954-115">将操作应用到的输入。</span><span class="sxs-lookup"><span data-stu-id="63954-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="63954-116">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="63954-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="63954-117">类型参数</span><span class="sxs-lookup"><span data-stu-id="63954-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="63954-118">找</span><span class="sxs-lookup"><span data-stu-id="63954-118">'T</span></span>

<span data-ttu-id="63954-119">要有条件地应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="63954-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="63954-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="63954-120">See Also</span></span>

- [<span data-ttu-id="63954-121">Canon. ApplyIfZeroC</span><span class="sxs-lookup"><span data-stu-id="63954-121">Microsoft.Quantum.Canon.ApplyIfZeroC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [<span data-ttu-id="63954-122">Canon. ApplyIfZeroA</span><span class="sxs-lookup"><span data-stu-id="63954-122">Microsoft.Quantum.Canon.ApplyIfZeroA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [<span data-ttu-id="63954-123">Canon. ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="63954-123">Microsoft.Quantum.Canon.ApplyIfZeroCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)