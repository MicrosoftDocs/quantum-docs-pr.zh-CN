---
uid: Microsoft.Quantum.Canon.ApplyIfElseBCA
title: ApplyIfElseBCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBCA
qsharp.summary: Applies one of two unitary operations, depending on the value of a classical bit.
ms.openlocfilehash: 0ebd086f4c8166a8d6b593200b0a3354c1420c6e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696343"
---
# <a name="applyifelsebca-operation"></a><span data-ttu-id="418f9-102">ApplyIfElseBCA 操作</span><span class="sxs-lookup"><span data-stu-id="418f9-102">ApplyIfElseBCA operation</span></span>

<span data-ttu-id="418f9-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="418f9-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="418f9-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="418f9-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="418f9-105">应用两个单一操作之一，具体取决于传统位的值。</span><span class="sxs-lookup"><span data-stu-id="418f9-105">Applies one of two unitary operations, depending on the value of a classical bit.</span></span>

```qsharp
operation ApplyIfElseBCA<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Adj + Ctl), trueInput : 'T), (falseOp : ('U => Unit is Adj + Ctl), falseInput : 'U)) : Unit
```


## <a name="description"></a><span data-ttu-id="418f9-106">说明</span><span class="sxs-lookup"><span data-stu-id="418f9-106">Description</span></span>

<span data-ttu-id="418f9-107">给定一个位，在为时 `bit` 应用该操作，并在为时应用该操作 `trueOp` `trueInput` `bit` `true` `falseOp(falseInput)` `bit` `false` 。</span><span class="sxs-lookup"><span data-stu-id="418f9-107">Given a bit `bit`, applies the operation `trueOp` with `trueInput` as its input when `bit` is `true`, and applies `falseOp(falseInput)` when `bit` is `false`.</span></span>

## <a name="input"></a><span data-ttu-id="418f9-108">输入</span><span class="sxs-lookup"><span data-stu-id="418f9-108">Input</span></span>

### <a name="bit--bool"></a><span data-ttu-id="418f9-109">bit： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="418f9-109">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="418f9-110">用于确定是否 `trueOp` 应用或的布尔值 `falseOp` 。</span><span class="sxs-lookup"><span data-stu-id="418f9-110">The boolean value used to determine whether `trueOp` or `falseOp` is applied.</span></span>


### <a name="trueop--t--unit-adj--ctl"></a><span data-ttu-id="418f9-111">trueOp：不等于> [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="418f9-111">trueOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="418f9-112">在为时要应用的单一 `bit` 操作 `true` 。</span><span class="sxs-lookup"><span data-stu-id="418f9-112">The unitary operation to be applied when `bit` is `true`.</span></span>


### <a name="trueinput--t"></a><span data-ttu-id="418f9-113">trueInput： t</span><span class="sxs-lookup"><span data-stu-id="418f9-113">trueInput : 'T</span></span>

<span data-ttu-id="418f9-114">当为时要向其提供的输入 `trueOp` `bit` `true` 。</span><span class="sxs-lookup"><span data-stu-id="418f9-114">The input to be provided to `trueOp` when `bit` is `true`.</span></span>


### <a name="falseop--u--unit-adj--ctl"></a><span data-ttu-id="418f9-115">falseOp： ' U => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="418f9-115">falseOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="418f9-116">在为时要应用的单一 `bit` 操作 `false` 。</span><span class="sxs-lookup"><span data-stu-id="418f9-116">The unitary operation to be applied when `bit` is `false`.</span></span>


### <a name="falseinput--u"></a><span data-ttu-id="418f9-117">falseInput： ' U</span><span class="sxs-lookup"><span data-stu-id="418f9-117">falseInput : 'U</span></span>

<span data-ttu-id="418f9-118">当为时要向其提供的输入 `falseOp` `bit` `false` 。</span><span class="sxs-lookup"><span data-stu-id="418f9-118">The input to be provided to `falseOp` when `bit` is `false`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="418f9-119">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="418f9-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="418f9-120">类型参数</span><span class="sxs-lookup"><span data-stu-id="418f9-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="418f9-121">找</span><span class="sxs-lookup"><span data-stu-id="418f9-121">'T</span></span>

<span data-ttu-id="418f9-122">`trueOp`要有条件地应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="418f9-122">The input type of the operation `trueOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="418f9-123">' U</span><span class="sxs-lookup"><span data-stu-id="418f9-123">'U</span></span>

<span data-ttu-id="418f9-124">`falseOp`要有条件地应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="418f9-124">The input type of the operation `falseOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="418f9-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="418f9-125">See Also</span></span>

- [<span data-ttu-id="418f9-126">Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="418f9-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="418f9-127">Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="418f9-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="418f9-128">Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="418f9-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="418f9-129">Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="418f9-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="418f9-130">Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="418f9-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)