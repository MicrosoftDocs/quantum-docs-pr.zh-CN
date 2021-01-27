---
uid: Microsoft.Quantum.Canon.ApplyIfElseBCA
title: ApplyIfElseBCA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfElseBCA
qsharp.summary: Applies one of two unitary operations, depending on the value of a classical bit.
ms.openlocfilehash: 3ed9d7cbf277f4c3acd0e6c3b5f920c3e140855d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844972"
---
# <a name="applyifelsebca-operation"></a><span data-ttu-id="a5b2b-102">ApplyIfElseBCA 操作</span><span class="sxs-lookup"><span data-stu-id="a5b2b-102">ApplyIfElseBCA operation</span></span>

<span data-ttu-id="a5b2b-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a5b2b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a5b2b-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a5b2b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a5b2b-105">应用两个单一操作之一，具体取决于传统位的值。</span><span class="sxs-lookup"><span data-stu-id="a5b2b-105">Applies one of two unitary operations, depending on the value of a classical bit.</span></span>

```qsharp
operation ApplyIfElseBCA<'T, 'U> (bit : Bool, (trueOp : ('T => Unit is Adj + Ctl), trueInput : 'T), (falseOp : ('U => Unit is Adj + Ctl), falseInput : 'U)) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="a5b2b-106">说明</span><span class="sxs-lookup"><span data-stu-id="a5b2b-106">Description</span></span>

<span data-ttu-id="a5b2b-107">给定一个位，在为时 `bit` 应用该操作，并在为时应用该操作 `trueOp` `trueInput` `bit` `true` `falseOp(falseInput)` `bit` `false` 。</span><span class="sxs-lookup"><span data-stu-id="a5b2b-107">Given a bit `bit`, applies the operation `trueOp` with `trueInput` as its input when `bit` is `true`, and applies `falseOp(falseInput)` when `bit` is `false`.</span></span>

## <a name="input"></a><span data-ttu-id="a5b2b-108">输入</span><span class="sxs-lookup"><span data-stu-id="a5b2b-108">Input</span></span>

### <a name="bit--bool"></a><span data-ttu-id="a5b2b-109">bit： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="a5b2b-109">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a5b2b-110">用于确定是否 `trueOp` 应用或的布尔值 `falseOp` 。</span><span class="sxs-lookup"><span data-stu-id="a5b2b-110">The boolean value used to determine whether `trueOp` or `falseOp` is applied.</span></span>


### <a name="trueop--t--unit--is-adj--ctl"></a><span data-ttu-id="a5b2b-111">trueOp： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="a5b2b-111">trueOp : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="a5b2b-112">在为时要应用的单一 `bit` 操作 `true` 。</span><span class="sxs-lookup"><span data-stu-id="a5b2b-112">The unitary operation to be applied when `bit` is `true`.</span></span>


### <a name="trueinput--t"></a><span data-ttu-id="a5b2b-113">trueInput： t</span><span class="sxs-lookup"><span data-stu-id="a5b2b-113">trueInput : 'T</span></span>

<span data-ttu-id="a5b2b-114">当为时要向其提供的输入 `trueOp` `bit` `true` 。</span><span class="sxs-lookup"><span data-stu-id="a5b2b-114">The input to be provided to `trueOp` when `bit` is `true`.</span></span>


### <a name="falseop--u--unit--is-adj--ctl"></a><span data-ttu-id="a5b2b-115">falseOp： ' U => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="a5b2b-115">falseOp : 'U => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="a5b2b-116">在为时要应用的单一 `bit` 操作 `false` 。</span><span class="sxs-lookup"><span data-stu-id="a5b2b-116">The unitary operation to be applied when `bit` is `false`.</span></span>


### <a name="falseinput--u"></a><span data-ttu-id="a5b2b-117">falseInput： ' U</span><span class="sxs-lookup"><span data-stu-id="a5b2b-117">falseInput : 'U</span></span>

<span data-ttu-id="a5b2b-118">当为时要向其提供的输入 `falseOp` `bit` `false` 。</span><span class="sxs-lookup"><span data-stu-id="a5b2b-118">The input to be provided to `falseOp` when `bit` is `false`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a5b2b-119">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a5b2b-119">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a5b2b-120">类型参数</span><span class="sxs-lookup"><span data-stu-id="a5b2b-120">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a5b2b-121">找</span><span class="sxs-lookup"><span data-stu-id="a5b2b-121">'T</span></span>

<span data-ttu-id="a5b2b-122">`trueOp`要有条件地应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="a5b2b-122">The input type of the operation `trueOp` to be conditionally applied.</span></span>
### <a name="u"></a><span data-ttu-id="a5b2b-123">' U</span><span class="sxs-lookup"><span data-stu-id="a5b2b-123">'U</span></span>

<span data-ttu-id="a5b2b-124">`falseOp`要有条件地应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="a5b2b-124">The input type of the operation `falseOp` to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="a5b2b-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a5b2b-125">See Also</span></span>

- [<span data-ttu-id="a5b2b-126">Canon. ApplyIfZero</span><span class="sxs-lookup"><span data-stu-id="a5b2b-126">Microsoft.Quantum.Canon.ApplyIfZero</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfZero)
- [<span data-ttu-id="a5b2b-127">Canon. ApplyIfOne</span><span class="sxs-lookup"><span data-stu-id="a5b2b-127">Microsoft.Quantum.Canon.ApplyIfOne</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- [<span data-ttu-id="a5b2b-128">Canon. ApplyIfElseRC</span><span class="sxs-lookup"><span data-stu-id="a5b2b-128">Microsoft.Quantum.Canon.ApplyIfElseRC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRC)
- [<span data-ttu-id="a5b2b-129">Canon. ApplyIfElseRA</span><span class="sxs-lookup"><span data-stu-id="a5b2b-129">Microsoft.Quantum.Canon.ApplyIfElseRA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRA)
- [<span data-ttu-id="a5b2b-130">Canon. ApplyIfElseRCA</span><span class="sxs-lookup"><span data-stu-id="a5b2b-130">Microsoft.Quantum.Canon.ApplyIfElseRCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfElseRCA)