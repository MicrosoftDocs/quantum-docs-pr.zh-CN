---
uid: Microsoft.Quantum.Canon.Delay
title: 延迟操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delay
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: f9f0e5c3120eb69bd7431d52d6cde5e846ffbe4d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696075"
---
# <a name="delay-operation"></a><span data-ttu-id="2a260-102">延迟操作</span><span class="sxs-lookup"><span data-stu-id="2a260-102">Delay operation</span></span>

<span data-ttu-id="2a260-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="2a260-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="2a260-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2a260-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2a260-105">应用给定操作，延迟。</span><span class="sxs-lookup"><span data-stu-id="2a260-105">Applies a given operation with a delay.</span></span>

```qsharp
operation Delay<'T, 'U> (op : ('T => 'U), arg : 'T, aux : Unit) : 'U
```


## <a name="description"></a><span data-ttu-id="2a260-106">说明</span><span class="sxs-lookup"><span data-stu-id="2a260-106">Description</span></span>

<span data-ttu-id="2a260-107">给定一个操作和一个对该操作的输入时，只要提供附加输入，就会应用该操作。</span><span class="sxs-lookup"><span data-stu-id="2a260-107">Given an operation and an input to that operation, applies the operation once an additional input is provided.</span></span>
<span data-ttu-id="2a260-108">具体而言，表达式 `Delay(op, arg, _)` 是 `op` 在调用时应用于的操作 `arg` 。</span><span class="sxs-lookup"><span data-stu-id="2a260-108">In particular, the expression `Delay(op, arg, _)` is an operation that applies `op` to `arg` when called.</span></span>
<span data-ttu-id="2a260-109">表达式 `Delay(op,arg,_)` 允许延迟的应用程序 `op` 。</span><span class="sxs-lookup"><span data-stu-id="2a260-109">Expression `Delay(op,arg,_)` allows to delay the application of `op`.</span></span>

## <a name="input"></a><span data-ttu-id="2a260-110">输入</span><span class="sxs-lookup"><span data-stu-id="2a260-110">Input</span></span>

### <a name="op--t--u"></a><span data-ttu-id="2a260-111">op： t => ' U</span><span class="sxs-lookup"><span data-stu-id="2a260-111">op : 'T => 'U</span></span> 

<span data-ttu-id="2a260-112">要应用的操作。</span><span class="sxs-lookup"><span data-stu-id="2a260-112">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="2a260-113">arg： t</span><span class="sxs-lookup"><span data-stu-id="2a260-113">arg : 'T</span></span>

<span data-ttu-id="2a260-114">将操作应用到的输入。</span><span class="sxs-lookup"><span data-stu-id="2a260-114">The input to which the operation is applied.</span></span>


### <a name="aux--unit"></a><span data-ttu-id="2a260-115">aux： [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="2a260-115">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="2a260-116">用于通过使用部分应用程序延迟操作应用程序的参数。</span><span class="sxs-lookup"><span data-stu-id="2a260-116">Argument used to delay the application of operation by using partial application.</span></span>



## <a name="output--u"></a><span data-ttu-id="2a260-117">输出： U</span><span class="sxs-lookup"><span data-stu-id="2a260-117">Output : 'U</span></span>



## <a name="type-parameters"></a><span data-ttu-id="2a260-118">类型参数</span><span class="sxs-lookup"><span data-stu-id="2a260-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2a260-119">找</span><span class="sxs-lookup"><span data-stu-id="2a260-119">'T</span></span>

<span data-ttu-id="2a260-120">要延迟的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="2a260-120">The input type of the operation to be delayed.</span></span>
### <a name="u"></a><span data-ttu-id="2a260-121">' U</span><span class="sxs-lookup"><span data-stu-id="2a260-121">'U</span></span>

<span data-ttu-id="2a260-122">要延迟的操作的返回类型。</span><span class="sxs-lookup"><span data-stu-id="2a260-122">The return type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="2a260-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2a260-123">See Also</span></span>

- [<span data-ttu-id="2a260-124">Canon. DelayC</span><span class="sxs-lookup"><span data-stu-id="2a260-124">Microsoft.Quantum.Canon.DelayC</span></span>](xref:Microsoft.Quantum.Canon.DelayC)
- [<span data-ttu-id="2a260-125">Canon. DelayA</span><span class="sxs-lookup"><span data-stu-id="2a260-125">Microsoft.Quantum.Canon.DelayA</span></span>](xref:Microsoft.Quantum.Canon.DelayA)
- [<span data-ttu-id="2a260-126">Canon. DelayCA</span><span class="sxs-lookup"><span data-stu-id="2a260-126">Microsoft.Quantum.Canon.DelayCA</span></span>](xref:Microsoft.Quantum.Canon.DelayCA)
- [<span data-ttu-id="2a260-127">Canon。延迟</span><span class="sxs-lookup"><span data-stu-id="2a260-127">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)