---
uid: Microsoft.Quantum.Canon.ApplyIfElseR
title: ApplyIfElseR 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseR
qsharp.summary: Applies one of two operations, depending on the value of a classical result.
ms.openlocfilehash: 0d7cc9f67f9dd0c69a9256f007a3aeab3e457907
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841814"
---
# <a name="applyifelser-operation"></a><span data-ttu-id="c2bf7-102">ApplyIfElseR 操作</span><span class="sxs-lookup"><span data-stu-id="c2bf7-102">ApplyIfElseR operation</span></span>

<span data-ttu-id="c2bf7-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c2bf7-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c2bf7-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c2bf7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c2bf7-105">应用两个操作之一，具体取决于传统结果的值。</span><span class="sxs-lookup"><span data-stu-id="c2bf7-105">Applies one of two operations, depending on the value of a classical result.</span></span>

```qsharp
operation ApplyIfElseR<'T, 'U> (result : Result, (zeroOp : ('T => Unit), zeroInput : 'T), (oneOp : ('U => Unit), oneInput : 'U)) : Unit
```


## <a name="description"></a><span data-ttu-id="c2bf7-106">说明</span><span class="sxs-lookup"><span data-stu-id="c2bf7-106">Description</span></span>

<span data-ttu-id="c2bf7-107">如果结果为 `result` ，则在等于时应用该操作， `zeroOp` `zeroInput` `result` `Zero` 并应用 `oneOp(oneInput)` `result == One` 该操作。</span><span class="sxs-lookup"><span data-stu-id="c2bf7-107">Given a result `result`, applies the operation `zeroOp` with `zeroInput` as its input when `result` is equal to `Zero`, and applies `oneOp(oneInput)` when `result == One`.</span></span>

## <a name="input"></a><span data-ttu-id="c2bf7-108">输入</span><span class="sxs-lookup"><span data-stu-id="c2bf7-108">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="c2bf7-109">结果：__无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="c2bf7-109">result : __invalid<Result>__</span></span>

<span data-ttu-id="c2bf7-110">用于确定是否应用或的测量 `zeroOp` 结果 `oneOp` 。</span><span class="sxs-lookup"><span data-stu-id="c2bf7-110">The measurement result used to determine if `zeroOp` or `oneOp` is applied.</span></span>


### <a name="zeroop--t--unit"></a><span data-ttu-id="c2bf7-111">zeroOp：不等于> [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c2bf7-111">zeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="c2bf7-112">在时要应用的操作 `result == Zero` 。</span><span class="sxs-lookup"><span data-stu-id="c2bf7-112">The operation to be applied when `result == Zero`.</span></span>


### <a name="zeroinput--t"></a><span data-ttu-id="c2bf7-113">zeroInput： t</span><span class="sxs-lookup"><span data-stu-id="c2bf7-113">zeroInput : 'T</span></span>

<span data-ttu-id="c2bf7-114">要提供给的 `zeroOp` 时间 `result == Zero` 。</span><span class="sxs-lookup"><span data-stu-id="c2bf7-114">The input to be provided to `zeroOp` when `result == Zero`.</span></span>


### <a name="oneop--u--unit"></a><span data-ttu-id="c2bf7-115">oneOp： ' U => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c2bf7-115">oneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="c2bf7-116">在时要应用的操作 `result == One` 。</span><span class="sxs-lookup"><span data-stu-id="c2bf7-116">The operation to be applied when `result == One`.</span></span>


### <a name="oneinput--u"></a><span data-ttu-id="c2bf7-117">oneInput： ' U</span><span class="sxs-lookup"><span data-stu-id="c2bf7-117">oneInput : 'U</span></span>

<span data-ttu-id="c2bf7-118">要提供给的 `oneOp` 时间 `result == One` 。</span><span class="sxs-lookup"><span data-stu-id="c2bf7-118">The input to be provided to `oneOp` when `result == One`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c2bf7-119">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c2bf7-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c2bf7-120">类型参数</span><span class="sxs-lookup"><span data-stu-id="c2bf7-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c2bf7-121">找</span><span class="sxs-lookup"><span data-stu-id="c2bf7-121">'T</span></span>

<span data-ttu-id="c2bf7-122">`zeroOp`要有条件地应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="c2bf7-122">The input type of the operation `zeroOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="c2bf7-123">' U</span><span class="sxs-lookup"><span data-stu-id="c2bf7-123">'U</span></span>

<span data-ttu-id="c2bf7-124">`oneOp`要有条件地应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="c2bf7-124">The input type of the operation `oneOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="c2bf7-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c2bf7-125">See Also</span></span>

- [<span data-ttu-id="c2bf7-126">Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="c2bf7-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="c2bf7-127">Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="c2bf7-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="c2bf7-128">Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="c2bf7-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="c2bf7-129">Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="c2bf7-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="c2bf7-130">Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="c2bf7-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)