---
uid: Microsoft.Quantum.Canon.DelayC
title: DelayC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayC
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: acb817c3322063353dc08c5d6f8c539391b3bf39
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696071"
---
# <a name="delayc-operation"></a><span data-ttu-id="63c37-102">DelayC 操作</span><span class="sxs-lookup"><span data-stu-id="63c37-102">DelayC operation</span></span>

<span data-ttu-id="63c37-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="63c37-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="63c37-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="63c37-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="63c37-105">应用给定操作，延迟。</span><span class="sxs-lookup"><span data-stu-id="63c37-105">Applies a given operation with a delay.</span></span>

```qsharp
operation DelayC<'T> (op : ('T => Unit is Ctl), arg : 'T, aux : Unit) : Unit
```


## <a name="description"></a><span data-ttu-id="63c37-106">说明</span><span class="sxs-lookup"><span data-stu-id="63c37-106">Description</span></span>

<span data-ttu-id="63c37-107">给定一个操作和一个对该操作的输入时，只要提供附加输入，就会应用该操作。</span><span class="sxs-lookup"><span data-stu-id="63c37-107">Given an operation and an input to that operation, applies the operation once an additional input is provided.</span></span>
<span data-ttu-id="63c37-108">具体而言，表达式 `Delay(op, arg, _)` 是 `op` 在调用时应用于的操作 `arg` 。</span><span class="sxs-lookup"><span data-stu-id="63c37-108">In particular, the expression `Delay(op, arg, _)` is an operation that applies `op` to `arg` when called.</span></span>
<span data-ttu-id="63c37-109">表达式 `Delay(op,arg,_)` 允许延迟的应用程序 `op` 。</span><span class="sxs-lookup"><span data-stu-id="63c37-109">Expression `Delay(op,arg,_)` allows to delay the application of `op`.</span></span>

## <a name="input"></a><span data-ttu-id="63c37-110">输入</span><span class="sxs-lookup"><span data-stu-id="63c37-110">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="63c37-111">op： t => [单元](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="63c37-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="63c37-112">要应用的操作。</span><span class="sxs-lookup"><span data-stu-id="63c37-112">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="63c37-113">arg： t</span><span class="sxs-lookup"><span data-stu-id="63c37-113">arg : 'T</span></span>

<span data-ttu-id="63c37-114">将操作应用到的输入。</span><span class="sxs-lookup"><span data-stu-id="63c37-114">The input to which the operation is applied.</span></span>


### <a name="aux--unit"></a><span data-ttu-id="63c37-115">aux： [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="63c37-115">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="63c37-116">用于通过使用部分应用程序延迟操作应用程序的参数。</span><span class="sxs-lookup"><span data-stu-id="63c37-116">Argument used to delay the application of operation by using partial application.</span></span>



## <a name="output--unit"></a><span data-ttu-id="63c37-117">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="63c37-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="63c37-118">类型参数</span><span class="sxs-lookup"><span data-stu-id="63c37-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="63c37-119">找</span><span class="sxs-lookup"><span data-stu-id="63c37-119">'T</span></span>

<span data-ttu-id="63c37-120">要延迟的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="63c37-120">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="63c37-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="63c37-121">See Also</span></span>

- [<span data-ttu-id="63c37-122">Canon。延迟</span><span class="sxs-lookup"><span data-stu-id="63c37-122">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)
- [<span data-ttu-id="63c37-123">Canon。延迟</span><span class="sxs-lookup"><span data-stu-id="63c37-123">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)