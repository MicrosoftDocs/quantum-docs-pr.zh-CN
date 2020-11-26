---
uid: Microsoft.Quantum.Canon.ApplyIfElseRA
title: ApplyIfElseRA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseRA
qsharp.summary: Applies one of two adjointable operations, depending on the value of a classical result.
ms.openlocfilehash: 3ebd09b1e5876ff397f3524ba828ba26a271e91e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218591"
---
# <a name="applyifelsera-operation"></a><span data-ttu-id="b7e8b-102">ApplyIfElseRA 操作</span><span class="sxs-lookup"><span data-stu-id="b7e8b-102">ApplyIfElseRA operation</span></span>

<span data-ttu-id="b7e8b-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b7e8b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b7e8b-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b7e8b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b7e8b-105">应用两个 adjointable 操作之一，具体取决于古典结果的值。</span><span class="sxs-lookup"><span data-stu-id="b7e8b-105">Applies one of two adjointable operations, depending on the value of a classical result.</span></span>

```qsharp
operation ApplyIfElseRA<'T, 'U> (result : Result, (zeroOp : ('T => Unit is Adj), zeroInput : 'T), (oneOp : ('U => Unit is Adj), oneInput : 'U)) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="b7e8b-106">描述</span><span class="sxs-lookup"><span data-stu-id="b7e8b-106">Description</span></span>

<span data-ttu-id="b7e8b-107">如果结果为 `result` ，则在等于时应用该操作， `zeroOp` `zeroInput` `result` `Zero` 并应用 `oneOp(oneInput)` `result == One` 该操作。</span><span class="sxs-lookup"><span data-stu-id="b7e8b-107">Given a result `result`, applies the operation `zeroOp` with `zeroInput` as its input when `result` is equal to `Zero`, and applies `oneOp(oneInput)` when `result == One`.</span></span>

## <a name="input"></a><span data-ttu-id="b7e8b-108">输入</span><span class="sxs-lookup"><span data-stu-id="b7e8b-108">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="b7e8b-109">结果：__无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="b7e8b-109">result : __invalid<Result>__</span></span>

<span data-ttu-id="b7e8b-110">用于确定是否应用或的测量 `zeroOp` 结果 `oneOp` 。</span><span class="sxs-lookup"><span data-stu-id="b7e8b-110">The measurement result used to determine if `zeroOp` or `oneOp` is applied.</span></span>


### <a name="zeroop--t--unit--is-adj"></a><span data-ttu-id="b7e8b-111">zeroOp： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词</span><span class="sxs-lookup"><span data-stu-id="b7e8b-111">zeroOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="b7e8b-112">在时要应用的 adjointable 操作 `result == Zero` 。</span><span class="sxs-lookup"><span data-stu-id="b7e8b-112">The adjointable operation to be applied when `result == Zero`.</span></span>


### <a name="zeroinput--t"></a><span data-ttu-id="b7e8b-113">zeroInput： t</span><span class="sxs-lookup"><span data-stu-id="b7e8b-113">zeroInput : 'T</span></span>

<span data-ttu-id="b7e8b-114">要提供给的 `zeroOp` 时间 `result == Zero` 。</span><span class="sxs-lookup"><span data-stu-id="b7e8b-114">The input to be provided to `zeroOp` when `result == Zero`.</span></span>


### <a name="oneop--u--unit--is-adj"></a><span data-ttu-id="b7e8b-115">oneOp： ' U => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词</span><span class="sxs-lookup"><span data-stu-id="b7e8b-115">oneOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="b7e8b-116">在时要应用的 adjointable 操作 `result == One` 。</span><span class="sxs-lookup"><span data-stu-id="b7e8b-116">The adjointable operation to be applied when `result == One`.</span></span>


### <a name="oneinput--u"></a><span data-ttu-id="b7e8b-117">oneInput： ' U</span><span class="sxs-lookup"><span data-stu-id="b7e8b-117">oneInput : 'U</span></span>

<span data-ttu-id="b7e8b-118">要提供给的 `oneOp` 时间 `result == One` 。</span><span class="sxs-lookup"><span data-stu-id="b7e8b-118">The input to be provided to `oneOp` when `result == One`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b7e8b-119">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b7e8b-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b7e8b-120">类型参数</span><span class="sxs-lookup"><span data-stu-id="b7e8b-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b7e8b-121">找</span><span class="sxs-lookup"><span data-stu-id="b7e8b-121">'T</span></span>

<span data-ttu-id="b7e8b-122">`zeroOp`要有条件地应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="b7e8b-122">The input type of the operation `zeroOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="b7e8b-123">' U</span><span class="sxs-lookup"><span data-stu-id="b7e8b-123">'U</span></span>

<span data-ttu-id="b7e8b-124">`oneOp`要有条件地应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="b7e8b-124">The input type of the operation `oneOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="b7e8b-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b7e8b-125">See Also</span></span>

- [<span data-ttu-id="b7e8b-126">Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="b7e8b-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="b7e8b-127">Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="b7e8b-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="b7e8b-128">Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="b7e8b-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="b7e8b-129">Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="b7e8b-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="b7e8b-130">Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="b7e8b-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)