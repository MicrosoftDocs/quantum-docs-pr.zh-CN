---
uid: Microsoft.Quantum.Canon.ApplyIfElseRC
title: ApplyIfElseRC 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseRC
qsharp.summary: Applies one of two controllable operations, depending on the value of a classical result.
ms.openlocfilehash: b2e4ade84b25b0100fe4b69814c760a672833f06
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209479"
---
# <a name="applyifelserc-operation"></a><span data-ttu-id="61bf6-102">ApplyIfElseRC 操作</span><span class="sxs-lookup"><span data-stu-id="61bf6-102">ApplyIfElseRC operation</span></span>

<span data-ttu-id="61bf6-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="61bf6-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="61bf6-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="61bf6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="61bf6-105">应用两个可控操作之一，具体取决于古典结果的值。</span><span class="sxs-lookup"><span data-stu-id="61bf6-105">Applies one of two controllable operations, depending on the value of a classical result.</span></span>

```qsharp
operation ApplyIfElseRC<'T, 'U> (result : Result, (zeroOp : ('T => Unit is Ctl), zeroInput : 'T), (oneOp : ('U => Unit is Ctl), oneInput : 'U)) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="61bf6-106">描述</span><span class="sxs-lookup"><span data-stu-id="61bf6-106">Description</span></span>

<span data-ttu-id="61bf6-107">如果结果为 `result` ，则在等于时应用该操作， `zeroOp` `zeroInput` `result` `Zero` 并应用 `oneOp(oneInput)` `result == One` 该操作。</span><span class="sxs-lookup"><span data-stu-id="61bf6-107">Given a result `result`, applies the operation `zeroOp` with `zeroInput` as its input when `result` is equal to `Zero`, and applies `oneOp(oneInput)` when `result == One`.</span></span>

## <a name="input"></a><span data-ttu-id="61bf6-108">输入</span><span class="sxs-lookup"><span data-stu-id="61bf6-108">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="61bf6-109">结果：__无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="61bf6-109">result : __invalid<Result>__</span></span>

<span data-ttu-id="61bf6-110">用于确定是否应用或的测量 `zeroOp` 结果 `oneOp` 。</span><span class="sxs-lookup"><span data-stu-id="61bf6-110">The measurement result used to determine if `zeroOp` or `oneOp` is applied.</span></span>


### <a name="zeroop--t--unit--is-ctl"></a><span data-ttu-id="61bf6-111">zeroOp： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为 Ctl</span><span class="sxs-lookup"><span data-stu-id="61bf6-111">zeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="61bf6-112">在时要应用的可控操作 `result == Zero` 。</span><span class="sxs-lookup"><span data-stu-id="61bf6-112">The controllable operation to be applied when `result == Zero`.</span></span>


### <a name="zeroinput--t"></a><span data-ttu-id="61bf6-113">zeroInput： t</span><span class="sxs-lookup"><span data-stu-id="61bf6-113">zeroInput : 'T</span></span>

<span data-ttu-id="61bf6-114">要提供给的 `zeroOp` 时间 `result == Zero` 。</span><span class="sxs-lookup"><span data-stu-id="61bf6-114">The input to be provided to `zeroOp` when `result == Zero`.</span></span>


### <a name="oneop--u--unit--is-ctl"></a><span data-ttu-id="61bf6-115">oneOp： ' U => [单位](xref:microsoft.quantum.lang-ref.unit)  为 Ctl</span><span class="sxs-lookup"><span data-stu-id="61bf6-115">oneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="61bf6-116">在时要应用的可控操作 `result == One` 。</span><span class="sxs-lookup"><span data-stu-id="61bf6-116">The controllable operation to be applied when `result == One`.</span></span>


### <a name="oneinput--u"></a><span data-ttu-id="61bf6-117">oneInput： ' U</span><span class="sxs-lookup"><span data-stu-id="61bf6-117">oneInput : 'U</span></span>

<span data-ttu-id="61bf6-118">要提供给的 `oneOp` 时间 `result == One` 。</span><span class="sxs-lookup"><span data-stu-id="61bf6-118">The input to be provided to `oneOp` when `result == One`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="61bf6-119">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="61bf6-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="61bf6-120">类型参数</span><span class="sxs-lookup"><span data-stu-id="61bf6-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="61bf6-121">找</span><span class="sxs-lookup"><span data-stu-id="61bf6-121">'T</span></span>

<span data-ttu-id="61bf6-122">`zeroOp`要有条件地应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="61bf6-122">The input type of the operation `zeroOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="61bf6-123">' U</span><span class="sxs-lookup"><span data-stu-id="61bf6-123">'U</span></span>

<span data-ttu-id="61bf6-124">`oneOp`要有条件地应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="61bf6-124">The input type of the operation `oneOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="61bf6-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="61bf6-125">See Also</span></span>

- [<span data-ttu-id="61bf6-126">Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="61bf6-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="61bf6-127">Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="61bf6-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="61bf6-128">Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="61bf6-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="61bf6-129">Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="61bf6-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="61bf6-130">Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="61bf6-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)