---
uid: Microsoft.Quantum.Canon.DelayA
title: DelayA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: DelayA
qsharp.summary: Applies a given operation with a delay.
ms.openlocfilehash: 77c40633824ccd9250252804b08d7400936515dd
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696072"
---
# <a name="delaya-operation"></a><span data-ttu-id="36107-102">DelayA 操作</span><span class="sxs-lookup"><span data-stu-id="36107-102">DelayA operation</span></span>

<span data-ttu-id="36107-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="36107-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="36107-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="36107-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="36107-105">应用给定操作，延迟。</span><span class="sxs-lookup"><span data-stu-id="36107-105">Applies a given operation with a delay.</span></span>

```qsharp
operation DelayA<'T> (op : ('T => Unit is Adj), arg : 'T, aux : Unit) : Unit
```


## <a name="description"></a><span data-ttu-id="36107-106">说明</span><span class="sxs-lookup"><span data-stu-id="36107-106">Description</span></span>

<span data-ttu-id="36107-107">给定一个操作和一个对该操作的输入时，只要提供附加输入，就会应用该操作。</span><span class="sxs-lookup"><span data-stu-id="36107-107">Given an operation and an input to that operation, applies the operation once an additional input is provided.</span></span>
<span data-ttu-id="36107-108">具体而言，表达式 `Delay(op, arg, _)` 是 `op` 在调用时应用于的操作 `arg` 。</span><span class="sxs-lookup"><span data-stu-id="36107-108">In particular, the expression `Delay(op, arg, _)` is an operation that applies `op` to `arg` when called.</span></span>
<span data-ttu-id="36107-109">表达式 `Delay(op,arg,_)` 允许延迟的应用程序 `op` 。</span><span class="sxs-lookup"><span data-stu-id="36107-109">Expression `Delay(op,arg,_)` allows to delay the application of `op`.</span></span>

## <a name="input"></a><span data-ttu-id="36107-110">输入</span><span class="sxs-lookup"><span data-stu-id="36107-110">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="36107-111">op： t => [单位](xref:microsoft.quantum.lang-ref.unit) 形容词</span><span class="sxs-lookup"><span data-stu-id="36107-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="36107-112">要应用的操作。</span><span class="sxs-lookup"><span data-stu-id="36107-112">An operation to be applied.</span></span>


### <a name="arg--t"></a><span data-ttu-id="36107-113">arg： t</span><span class="sxs-lookup"><span data-stu-id="36107-113">arg : 'T</span></span>

<span data-ttu-id="36107-114">将操作应用到的输入。</span><span class="sxs-lookup"><span data-stu-id="36107-114">The input to which the operation is applied.</span></span>


### <a name="aux--unit"></a><span data-ttu-id="36107-115">aux： [Unit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="36107-115">aux : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>

<span data-ttu-id="36107-116">用于通过使用部分应用程序延迟操作应用程序的参数。</span><span class="sxs-lookup"><span data-stu-id="36107-116">Argument used to delay the application of operation by using partial application.</span></span>



## <a name="output--unit"></a><span data-ttu-id="36107-117">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="36107-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="36107-118">类型参数</span><span class="sxs-lookup"><span data-stu-id="36107-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="36107-119">找</span><span class="sxs-lookup"><span data-stu-id="36107-119">'T</span></span>

<span data-ttu-id="36107-120">要延迟的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="36107-120">The input type of the operation to be delayed.</span></span>

## <a name="see-also"></a><span data-ttu-id="36107-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="36107-121">See Also</span></span>

- [<span data-ttu-id="36107-122">Canon。延迟</span><span class="sxs-lookup"><span data-stu-id="36107-122">Microsoft.Quantum.Canon.Delay</span></span>](xref:Microsoft.Quantum.Canon.Delay)
- [<span data-ttu-id="36107-123">Canon。延迟</span><span class="sxs-lookup"><span data-stu-id="36107-123">Microsoft.Quantum.Canon.Delayed</span></span>](xref:Microsoft.Quantum.Canon.Delayed)