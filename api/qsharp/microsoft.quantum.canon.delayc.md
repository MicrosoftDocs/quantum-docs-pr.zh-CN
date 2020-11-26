---
uid: Microsoft.Quantum.Canon.DelayC
title: DelayC 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayC
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: 7a11c3990802ff36856a90de927b38d2ede8bd9d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216483"
---
# <a name="delayc-operation"></a><span data-ttu-id="09a29-102">DelayC 操作</span><span class="sxs-lookup"><span data-stu-id="09a29-102">DelayC operation</span></span>

<span data-ttu-id="09a29-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="09a29-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="09a29-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="09a29-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="09a29-105">应用给定操作，延迟。</span><span class="sxs-lookup"><span data-stu-id="09a29-105">Applies a given operation with a delay.</span></span>

```qsharp
operation DelayC<'T> (op : ('T => Unit is Ctl), arg : 'T, aux : Unit) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="09a29-106">描述</span><span class="sxs-lookup"><span data-stu-id="09a29-106">Description</span></span>

<span data-ttu-id="09a29-107">给定一个操作和一个对该操作的输入时，只要提供附加输入，就会应用该操作。</span><span class="sxs-lookup"><span data-stu-id="09a29-107">Given an operation and an input to that operation, applies the operation once an additional input is provided.</span></span>
<span data-ttu-id="09a29-108">具体而言，表达式 `Delay(op, arg, _)` 是 `op` 在调用时应用于的操作 `arg` 。</span><span class="sxs-lookup"><span data-stu-id="09a29-108">In particular, the expression `Delay(op, arg, _)` is an operation that applies `op` to `arg` when called.</span></span>
<span data-ttu-id="09a29-109">表达式 `Delay(op,arg,_)` 允许延迟的应用程序 `op` 。</span><span class="sxs-lookup"><span data-stu-id="09a29-109">Expression `Delay(op,arg,_)` allows to delay the application of `op`.</span></span>

## <a name="input"></a><span data-ttu-id="09a29-110">输入</span><span class="sxs-lookup"><span data-stu-id="09a29-110">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="09a29-111">op： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为 Ctl</span><span class="sxs-lookup"><span data-stu-id="09a29-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="09a29-112">要应用的操作。</span><span class="sxs-lookup"><span data-stu-id="09a29-112">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="09a29-113">arg： t</span><span class="sxs-lookup"><span data-stu-id="09a29-113">arg : 'T</span></span>

<span data-ttu-id="09a29-114">将操作应用到的输入。</span><span class="sxs-lookup"><span data-stu-id="09a29-114">The input to which the operation is applied.</span></span>


### <a name="aux--unit"></a><span data-ttu-id="09a29-115">aux： [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="09a29-115">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="09a29-116">用于通过使用部分应用程序延迟操作应用程序的参数。</span><span class="sxs-lookup"><span data-stu-id="09a29-116">Argument used to delay the application of operation by using partial application.</span></span>



## <a name="output--unit"></a><span data-ttu-id="09a29-117">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="09a29-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="09a29-118">类型参数</span><span class="sxs-lookup"><span data-stu-id="09a29-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="09a29-119">找</span><span class="sxs-lookup"><span data-stu-id="09a29-119">'T</span></span>

<span data-ttu-id="09a29-120">要延迟的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="09a29-120">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="09a29-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="09a29-121">See Also</span></span>

- [<span data-ttu-id="09a29-122">Canon。延迟</span><span class="sxs-lookup"><span data-stu-id="09a29-122">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)
- [<span data-ttu-id="09a29-123">Canon。延迟</span><span class="sxs-lookup"><span data-stu-id="09a29-123">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)