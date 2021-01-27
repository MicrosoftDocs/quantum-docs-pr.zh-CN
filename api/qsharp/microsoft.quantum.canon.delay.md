---
uid: Microsoft.Quantum.Canon.Delay
title: 延迟操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Delay
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: c8ba128e44a9b217ec196e39ff1df639ef276784
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840653"
---
# <a name="delay-operation"></a><span data-ttu-id="7c7fc-102">延迟操作</span><span class="sxs-lookup"><span data-stu-id="7c7fc-102">Delay operation</span></span>

<span data-ttu-id="7c7fc-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7c7fc-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7c7fc-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7c7fc-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7c7fc-105">应用给定操作，延迟。</span><span class="sxs-lookup"><span data-stu-id="7c7fc-105">Applies a given operation with a delay.</span></span>

```qsharp
operation Delay<'T, 'U> (op : ('T => 'U), arg : 'T, aux : Unit) : 'U
```


## <a name="description"></a><span data-ttu-id="7c7fc-106">说明</span><span class="sxs-lookup"><span data-stu-id="7c7fc-106">Description</span></span>

<span data-ttu-id="7c7fc-107">给定一个操作和一个对该操作的输入时，只要提供附加输入，就会应用该操作。</span><span class="sxs-lookup"><span data-stu-id="7c7fc-107">Given an operation and an input to that operation, applies the operation once an additional input is provided.</span></span>
<span data-ttu-id="7c7fc-108">具体而言，表达式 `Delay(op, arg, _)` 是 `op` 在调用时应用于的操作 `arg` 。</span><span class="sxs-lookup"><span data-stu-id="7c7fc-108">In particular, the expression `Delay(op, arg, _)` is an operation that applies `op` to `arg` when called.</span></span>
<span data-ttu-id="7c7fc-109">表达式 `Delay(op,arg,_)` 允许延迟的应用程序 `op` 。</span><span class="sxs-lookup"><span data-stu-id="7c7fc-109">Expression `Delay(op,arg,_)` allows to delay the application of `op`.</span></span>

## <a name="input"></a><span data-ttu-id="7c7fc-110">输入</span><span class="sxs-lookup"><span data-stu-id="7c7fc-110">Input</span></span>

### <a name="op--t--u"></a><span data-ttu-id="7c7fc-111">op： t => ' U</span><span class="sxs-lookup"><span data-stu-id="7c7fc-111">op : 'T => 'U</span></span> 

<span data-ttu-id="7c7fc-112">要应用的操作。</span><span class="sxs-lookup"><span data-stu-id="7c7fc-112">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="7c7fc-113">arg： t</span><span class="sxs-lookup"><span data-stu-id="7c7fc-113">arg : 'T</span></span>

<span data-ttu-id="7c7fc-114">将操作应用到的输入。</span><span class="sxs-lookup"><span data-stu-id="7c7fc-114">The input to which the operation is applied.</span></span>


### <a name="aux--unit"></a><span data-ttu-id="7c7fc-115">aux： [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7c7fc-115">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="7c7fc-116">用于通过使用部分应用程序延迟操作应用程序的参数。</span><span class="sxs-lookup"><span data-stu-id="7c7fc-116">Argument used to delay the application of operation by using partial application.</span></span>



## <a name="output--u"></a><span data-ttu-id="7c7fc-117">输出： U</span><span class="sxs-lookup"><span data-stu-id="7c7fc-117">Output : 'U</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7c7fc-118">类型参数</span><span class="sxs-lookup"><span data-stu-id="7c7fc-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7c7fc-119">找</span><span class="sxs-lookup"><span data-stu-id="7c7fc-119">'T</span></span>

<span data-ttu-id="7c7fc-120">要延迟的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="7c7fc-120">The input type of the operation to be delayed.</span></span>
### <a name="u"></a><span data-ttu-id="7c7fc-121">' U</span><span class="sxs-lookup"><span data-stu-id="7c7fc-121">'U</span></span>

<span data-ttu-id="7c7fc-122">要延迟的操作的返回类型。</span><span class="sxs-lookup"><span data-stu-id="7c7fc-122">The return type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="7c7fc-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7c7fc-123">See Also</span></span>

- [<span data-ttu-id="7c7fc-124">Canon. DelayC</span><span class="sxs-lookup"><span data-stu-id="7c7fc-124">Microsoft.Quantum.Canon.DelayC</span></span>](xref:Microsoft.Quantum.Canon.DelayC)
- [<span data-ttu-id="7c7fc-125">Canon. DelayA</span><span class="sxs-lookup"><span data-stu-id="7c7fc-125">Microsoft.Quantum.Canon.DelayA</span></span>](xref:Microsoft.Quantum.Canon.DelayA)
- [<span data-ttu-id="7c7fc-126">Canon. DelayCA</span><span class="sxs-lookup"><span data-stu-id="7c7fc-126">Microsoft.Quantum.Canon.DelayCA</span></span>](xref:Microsoft.Quantum.Canon.DelayCA)
- [<span data-ttu-id="7c7fc-127">Canon。延迟</span><span class="sxs-lookup"><span data-stu-id="7c7fc-127">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)