---
uid: Microsoft.Quantum.Canon.ApplyIfZeroCA
title: ApplyIfZeroCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZeroCA
qsharp.summary: Applies a unitary operation conditioned on a classical result value being zero.
ms.openlocfilehash: 85612bd3dd7af45b7901fef775a7d556eb229608
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696316"
---
# <a name="applyifzeroca-operation"></a><span data-ttu-id="097e1-102">ApplyIfZeroCA 操作</span><span class="sxs-lookup"><span data-stu-id="097e1-102">ApplyIfZeroCA operation</span></span>

<span data-ttu-id="097e1-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="097e1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="097e1-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="097e1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="097e1-105">应用在传统结果值为零的条件运算。</span><span class="sxs-lookup"><span data-stu-id="097e1-105">Applies a unitary operation conditioned on a classical result value being zero.</span></span>

```qsharp
operation ApplyIfZeroCA<'T> (result : Result, (op : ('T => Unit is Adj + Ctl), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="097e1-106">说明</span><span class="sxs-lookup"><span data-stu-id="097e1-106">Description</span></span>

<span data-ttu-id="097e1-107">给定一个操作 `op` 和一个结果值时 `result` ， `op` `target` 如果为， `result` 则应用于 `Zero` 。</span><span class="sxs-lookup"><span data-stu-id="097e1-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `Zero`.</span></span> <span data-ttu-id="097e1-108">如果 `One` 为，则不会发生任何事情 `target` 。</span><span class="sxs-lookup"><span data-stu-id="097e1-108">If `One`, nothing happens to the `target`.</span></span>
<span data-ttu-id="097e1-109">后缀 `CA` 指示要应用的操作是单一 (可控和 adjointable) 。</span><span class="sxs-lookup"><span data-stu-id="097e1-109">The suffix `CA` indicates that the operation to be applied is unitary (controllable and adjointable).</span></span>

## <a name="input"></a><span data-ttu-id="097e1-110">输入</span><span class="sxs-lookup"><span data-stu-id="097e1-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="097e1-111">结果： __无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="097e1-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="097e1-112">用于控制是否应用 op 的测量结果。</span><span class="sxs-lookup"><span data-stu-id="097e1-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit-adj--ctl"></a><span data-ttu-id="097e1-113">op： t => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="097e1-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="097e1-114">要有条件地应用的操作。</span><span class="sxs-lookup"><span data-stu-id="097e1-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="097e1-115">目标： t</span><span class="sxs-lookup"><span data-stu-id="097e1-115">target : 'T</span></span>

<span data-ttu-id="097e1-116">将操作应用到的输入。</span><span class="sxs-lookup"><span data-stu-id="097e1-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="097e1-117">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="097e1-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="097e1-118">类型参数</span><span class="sxs-lookup"><span data-stu-id="097e1-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="097e1-119">找</span><span class="sxs-lookup"><span data-stu-id="097e1-119">'T</span></span>

<span data-ttu-id="097e1-120">要有条件地应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="097e1-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="097e1-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="097e1-121">See Also</span></span>

- [<span data-ttu-id="097e1-122">Canon. ApplyIfZeroC</span><span class="sxs-lookup"><span data-stu-id="097e1-122">Microsoft.Quantum.Canon.ApplyIfZeroC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [<span data-ttu-id="097e1-123">Canon. ApplyIfZeroA</span><span class="sxs-lookup"><span data-stu-id="097e1-123">Microsoft.Quantum.Canon.ApplyIfZeroA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [<span data-ttu-id="097e1-124">Canon. ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="097e1-124">Microsoft.Quantum.Canon.ApplyIfZeroCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)