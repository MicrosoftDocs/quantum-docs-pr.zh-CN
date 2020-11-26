---
uid: Microsoft.Quantum.Canon.ApplyIfElseRCA
title: ApplyIfElseRCA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseRCA
qsharp.summary: Applies one of two unitary operations, depending on the value of a classical result.
ms.openlocfilehash: dfd1c16a25a2da507024813a380386c8f4e49d30
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218744"
---
# <a name="applyifelserca-operation"></a><span data-ttu-id="d68d0-102">ApplyIfElseRCA 操作</span><span class="sxs-lookup"><span data-stu-id="d68d0-102">ApplyIfElseRCA operation</span></span>

<span data-ttu-id="d68d0-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d68d0-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d68d0-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d68d0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d68d0-105">应用两个单一操作中的一个，具体取决于古典结果的值。</span><span class="sxs-lookup"><span data-stu-id="d68d0-105">Applies one of two unitary operations, depending on the value of a classical result.</span></span>

```qsharp
operation ApplyIfElseRCA<'T, 'U> (result : Result, (zeroOp : ('T => Unit is Adj + Ctl), zeroInput : 'T), (oneOp : ('U => Unit is Adj + Ctl), oneInput : 'U)) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="d68d0-106">描述</span><span class="sxs-lookup"><span data-stu-id="d68d0-106">Description</span></span>

<span data-ttu-id="d68d0-107">如果结果为 `result` ，则在等于时应用该操作， `zeroOp` `zeroInput` `result` `Zero` 并应用 `oneOp(oneInput)` `result == One` 该操作。</span><span class="sxs-lookup"><span data-stu-id="d68d0-107">Given a result `result`, applies the operation `zeroOp` with `zeroInput` as its input when `result` is equal to `Zero`, and applies `oneOp(oneInput)` when `result == One`.</span></span>

## <a name="input"></a><span data-ttu-id="d68d0-108">输入</span><span class="sxs-lookup"><span data-stu-id="d68d0-108">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="d68d0-109">结果：__无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="d68d0-109">result : __invalid<Result>__</span></span>

<span data-ttu-id="d68d0-110">用于确定是否应用或的测量 `zeroOp` 结果 `oneOp` 。</span><span class="sxs-lookup"><span data-stu-id="d68d0-110">The measurement result used to determine if `zeroOp` or `oneOp` is applied.</span></span>


### <a name="zeroop--t--unit--is-adj--ctl"></a><span data-ttu-id="d68d0-111">zeroOp： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="d68d0-111">zeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="d68d0-112">在时要应用的单一操作 `result == Zero` 。</span><span class="sxs-lookup"><span data-stu-id="d68d0-112">The unitary operation to be applied when `result == Zero`.</span></span>


### <a name="zeroinput--t"></a><span data-ttu-id="d68d0-113">zeroInput： t</span><span class="sxs-lookup"><span data-stu-id="d68d0-113">zeroInput : 'T</span></span>

<span data-ttu-id="d68d0-114">要提供给的 `zeroOp` 时间 `result == Zero` 。</span><span class="sxs-lookup"><span data-stu-id="d68d0-114">The input to be provided to `zeroOp` when `result == Zero`.</span></span>


### <a name="oneop--u--unit--is-adj--ctl"></a><span data-ttu-id="d68d0-115">oneOp： ' U => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="d68d0-115">oneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="d68d0-116">在时要应用的单一操作 `result == One` 。</span><span class="sxs-lookup"><span data-stu-id="d68d0-116">The unitary operation to be applied when `result == One`.</span></span>


### <a name="oneinput--u"></a><span data-ttu-id="d68d0-117">oneInput： ' U</span><span class="sxs-lookup"><span data-stu-id="d68d0-117">oneInput : 'U</span></span>

<span data-ttu-id="d68d0-118">要提供给的 `oneOp` 时间 `result == One` 。</span><span class="sxs-lookup"><span data-stu-id="d68d0-118">The input to be provided to `oneOp` when `result == One`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d68d0-119">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d68d0-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d68d0-120">类型参数</span><span class="sxs-lookup"><span data-stu-id="d68d0-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d68d0-121">找</span><span class="sxs-lookup"><span data-stu-id="d68d0-121">'T</span></span>

<span data-ttu-id="d68d0-122">`zeroOp`要有条件地应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="d68d0-122">The input type of the operation `zeroOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="d68d0-123">' U</span><span class="sxs-lookup"><span data-stu-id="d68d0-123">'U</span></span>

<span data-ttu-id="d68d0-124">`oneOp`要有条件地应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="d68d0-124">The input type of the operation `oneOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="d68d0-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d68d0-125">See Also</span></span>

- [<span data-ttu-id="d68d0-126">Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="d68d0-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="d68d0-127">Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="d68d0-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="d68d0-128">Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="d68d0-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="d68d0-129">Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="d68d0-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="d68d0-130">Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="d68d0-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)