---
uid: Microsoft.Quantum.Canon.ApplyIfElseBA
title: ApplyIfElseBA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBA
qsharp.summary: Applies one of two adjointable operations, depending on the value of a classical bit.
ms.openlocfilehash: a85567a49df1f261b95f3553da8dc789ce924e7a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844984"
---
# <a name="applyifelseba-operation"></a><span data-ttu-id="3ec62-102">ApplyIfElseBA 操作</span><span class="sxs-lookup"><span data-stu-id="3ec62-102">ApplyIfElseBA operation</span></span>

<span data-ttu-id="3ec62-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="3ec62-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="3ec62-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3ec62-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3ec62-105">应用两个 adjointable 操作之一，具体取决于传统位的值。</span><span class="sxs-lookup"><span data-stu-id="3ec62-105">Applies one of two adjointable operations, depending on the value of a classical bit.</span></span>

```qsharp
operation ApplyIfElseBA<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Adj), trueInput : 'T), (falseOp : ('U => Unit is Adj), falseInput : 'U)) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="3ec62-106">说明</span><span class="sxs-lookup"><span data-stu-id="3ec62-106">Description</span></span>

<span data-ttu-id="3ec62-107">给定一个位，在为时 `bit` 应用该操作，并在为时应用该操作 `trueOp` `trueInput` `bit` `true` `falseOp(falseInput)` `bit` `false` 。</span><span class="sxs-lookup"><span data-stu-id="3ec62-107">Given a bit `bit`, applies the operation `trueOp` with `trueInput` as its input when `bit` is `true`, and applies `falseOp(falseInput)` when `bit` is `false`.</span></span>

## <a name="input"></a><span data-ttu-id="3ec62-108">输入</span><span class="sxs-lookup"><span data-stu-id="3ec62-108">Input</span></span>

### <a name="bit--bool"></a><span data-ttu-id="3ec62-109">bit： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="3ec62-109">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="3ec62-110">用于确定是否 `trueOp` 应用或的布尔值 `falseOp` 。</span><span class="sxs-lookup"><span data-stu-id="3ec62-110">The boolean value used to determine whether `trueOp` or `falseOp` is applied.</span></span>


### <a name="trueop--t--unit--is-adj"></a><span data-ttu-id="3ec62-111">trueOp： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词</span><span class="sxs-lookup"><span data-stu-id="3ec62-111">trueOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="3ec62-112">当为时要应用的 adjointable `bit` 操作 `true` 。</span><span class="sxs-lookup"><span data-stu-id="3ec62-112">The adjointable operation to be applied when `bit` is `true`.</span></span>


### <a name="trueinput--t"></a><span data-ttu-id="3ec62-113">trueInput： t</span><span class="sxs-lookup"><span data-stu-id="3ec62-113">trueInput : 'T</span></span>

<span data-ttu-id="3ec62-114">当为时要向其提供的输入 `trueOp` `bit` `true` 。</span><span class="sxs-lookup"><span data-stu-id="3ec62-114">The input to be provided to `trueOp` when `bit` is `true`.</span></span>


### <a name="falseop--u--unit--is-adj"></a><span data-ttu-id="3ec62-115">falseOp： ' U => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词</span><span class="sxs-lookup"><span data-stu-id="3ec62-115">falseOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="3ec62-116">当为时要应用的 adjointable `bit` 操作 `false` 。</span><span class="sxs-lookup"><span data-stu-id="3ec62-116">The adjointable operation to be applied when `bit` is `false`.</span></span>


### <a name="falseinput--u"></a><span data-ttu-id="3ec62-117">falseInput： ' U</span><span class="sxs-lookup"><span data-stu-id="3ec62-117">falseInput : 'U</span></span>

<span data-ttu-id="3ec62-118">当为时要向其提供的输入 `falseOp` `bit` `false` 。</span><span class="sxs-lookup"><span data-stu-id="3ec62-118">The input to be provided to `falseOp` when `bit` is `false`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="3ec62-119">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="3ec62-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="3ec62-120">类型参数</span><span class="sxs-lookup"><span data-stu-id="3ec62-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3ec62-121">找</span><span class="sxs-lookup"><span data-stu-id="3ec62-121">'T</span></span>

<span data-ttu-id="3ec62-122">`trueOp`要有条件地应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="3ec62-122">The input type of the operation `trueOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="3ec62-123">' U</span><span class="sxs-lookup"><span data-stu-id="3ec62-123">'U</span></span>

<span data-ttu-id="3ec62-124">`falseOp`要有条件地应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="3ec62-124">The input type of the operation `falseOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="3ec62-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3ec62-125">See Also</span></span>

- [<span data-ttu-id="3ec62-126">Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="3ec62-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="3ec62-127">Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="3ec62-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="3ec62-128">Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="3ec62-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="3ec62-129">Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="3ec62-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="3ec62-130">Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="3ec62-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)