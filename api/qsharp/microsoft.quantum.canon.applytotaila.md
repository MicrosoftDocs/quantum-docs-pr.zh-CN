---
uid: Microsoft.Quantum.Canon.ApplyToTailA
title: ApplyToTailA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailA
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: a84fa6c53f3e11bef82b8b83fffa1451a8299511
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696169"
---
# <a name="applytotaila-operation"></a><span data-ttu-id="df6ec-102">ApplyToTailA 操作</span><span class="sxs-lookup"><span data-stu-id="df6ec-102">ApplyToTailA operation</span></span>

<span data-ttu-id="df6ec-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="df6ec-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="df6ec-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="df6ec-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="df6ec-105">将操作应用到数组的最后一个元素。</span><span class="sxs-lookup"><span data-stu-id="df6ec-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTailA<'T> (op : ('T => Unit is Adj), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="df6ec-106">说明</span><span class="sxs-lookup"><span data-stu-id="df6ec-106">Description</span></span>

<span data-ttu-id="df6ec-107">给定一个操作 `op` 和一个目标数组 `targets` ，适用于 `op(Tail(targets))` 。</span><span class="sxs-lookup"><span data-stu-id="df6ec-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="df6ec-108">输入</span><span class="sxs-lookup"><span data-stu-id="df6ec-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="df6ec-109">op： t => [单位](xref:microsoft.quantum.lang-ref.unit) 形容词</span><span class="sxs-lookup"><span data-stu-id="df6ec-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="df6ec-110">要应用的操作。</span><span class="sxs-lookup"><span data-stu-id="df6ec-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="df6ec-111">目标： t []</span><span class="sxs-lookup"><span data-stu-id="df6ec-111">targets : 'T[]</span></span>

<span data-ttu-id="df6ec-112">要应用最后一个目标的数组 `op` 。</span><span class="sxs-lookup"><span data-stu-id="df6ec-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="df6ec-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="df6ec-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="df6ec-114">类型参数</span><span class="sxs-lookup"><span data-stu-id="df6ec-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="df6ec-115">找</span><span class="sxs-lookup"><span data-stu-id="df6ec-115">'T</span></span>

<span data-ttu-id="df6ec-116">要应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="df6ec-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="df6ec-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="df6ec-117">See Also</span></span>

- [<span data-ttu-id="df6ec-118">Canon. ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="df6ec-118">Microsoft.Quantum.Canon.ApplyToTail</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [<span data-ttu-id="df6ec-119">Canon. ApplyToTailC</span><span class="sxs-lookup"><span data-stu-id="df6ec-119">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)
- [<span data-ttu-id="df6ec-120">Canon. ApplyToTailCA</span><span class="sxs-lookup"><span data-stu-id="df6ec-120">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)