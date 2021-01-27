---
uid: Microsoft.Quantum.Canon.ApplyIfZeroC
title: ApplyIfZeroC 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfZeroC
qsharp.summary: Applies a controllable operation conditioned on a classical result value being zero.
ms.openlocfilehash: 3876e2baf1b3ad5bbfa0097d468b1e88adf05db4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841723"
---
# <a name="applyifzeroc-operation"></a><span data-ttu-id="3bd45-102">ApplyIfZeroC 操作</span><span class="sxs-lookup"><span data-stu-id="3bd45-102">ApplyIfZeroC operation</span></span>

<span data-ttu-id="3bd45-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3bd45-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3bd45-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3bd45-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3bd45-105">应用在传统结果值为零的可控操作。</span><span class="sxs-lookup"><span data-stu-id="3bd45-105">Applies a controllable operation conditioned on a classical result value being zero.</span></span>

```qsharp
operation ApplyIfZeroC<'T> (result : Result, (op : ('T => Unit is Ctl), target : 'T)) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="3bd45-106">说明</span><span class="sxs-lookup"><span data-stu-id="3bd45-106">Description</span></span>

<span data-ttu-id="3bd45-107">给定一个操作 `op` 和一个结果值时 `result` ， `op` `target` 如果为， `result` 则应用于 `Zero` 。</span><span class="sxs-lookup"><span data-stu-id="3bd45-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `Zero`.</span></span> <span data-ttu-id="3bd45-108">如果 `One` 为，则不会发生任何事情 `target` 。</span><span class="sxs-lookup"><span data-stu-id="3bd45-108">If `One`, nothing happens to the `target`.</span></span>
<span data-ttu-id="3bd45-109">后缀 `C` 指示要应用的操作可控制。</span><span class="sxs-lookup"><span data-stu-id="3bd45-109">The suffix `C` indicates that the operation to be applied is controllable.</span></span>

## <a name="input"></a><span data-ttu-id="3bd45-110">输入</span><span class="sxs-lookup"><span data-stu-id="3bd45-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="3bd45-111">结果：__无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="3bd45-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="3bd45-112">用于控制是否应用 op 的测量结果。</span><span class="sxs-lookup"><span data-stu-id="3bd45-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="3bd45-113">op： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为 Ctl</span><span class="sxs-lookup"><span data-stu-id="3bd45-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="3bd45-114">要有条件地应用的操作。</span><span class="sxs-lookup"><span data-stu-id="3bd45-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="3bd45-115">目标： t</span><span class="sxs-lookup"><span data-stu-id="3bd45-115">target : 'T</span></span>

<span data-ttu-id="3bd45-116">将操作应用到的输入。</span><span class="sxs-lookup"><span data-stu-id="3bd45-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3bd45-117">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3bd45-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="3bd45-118">类型参数</span><span class="sxs-lookup"><span data-stu-id="3bd45-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3bd45-119">找</span><span class="sxs-lookup"><span data-stu-id="3bd45-119">'T</span></span>

<span data-ttu-id="3bd45-120">要有条件地应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="3bd45-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="3bd45-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3bd45-121">See Also</span></span>

- [<span data-ttu-id="3bd45-122">Canon. ApplyIfZeroC</span><span class="sxs-lookup"><span data-stu-id="3bd45-122">Microsoft.Quantum.Canon.ApplyIfZeroC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroC)
- [<span data-ttu-id="3bd45-123">Canon. ApplyIfZeroA</span><span class="sxs-lookup"><span data-stu-id="3bd45-123">Microsoft.Quantum.Canon.ApplyIfZeroA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroA)
- [<span data-ttu-id="3bd45-124">Canon. ApplyIfZeroCA</span><span class="sxs-lookup"><span data-stu-id="3bd45-124">Microsoft.Quantum.Canon.ApplyIfZeroCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZeroCA)