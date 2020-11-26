---
uid: Microsoft.Quantum.Canon.ApplyToTail
title: ApplyToTail 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTail
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 6754d41e63ea0357487fa2f62bd9209843a93347
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207966"
---
# <a name="applytotail-operation"></a><span data-ttu-id="cc80e-102">ApplyToTail 操作</span><span class="sxs-lookup"><span data-stu-id="cc80e-102">ApplyToTail operation</span></span>

<span data-ttu-id="cc80e-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="cc80e-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="cc80e-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cc80e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cc80e-105">将操作应用到数组的最后一个元素。</span><span class="sxs-lookup"><span data-stu-id="cc80e-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTail<'T> (op : ('T => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="cc80e-106">描述</span><span class="sxs-lookup"><span data-stu-id="cc80e-106">Description</span></span>

<span data-ttu-id="cc80e-107">给定一个操作 `op` 和一个目标数组 `targets` ，适用于 `op(Tail(targets))` 。</span><span class="sxs-lookup"><span data-stu-id="cc80e-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="cc80e-108">输入</span><span class="sxs-lookup"><span data-stu-id="cc80e-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="cc80e-109">op： t => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cc80e-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="cc80e-110">要应用的操作。</span><span class="sxs-lookup"><span data-stu-id="cc80e-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="cc80e-111">目标： t []</span><span class="sxs-lookup"><span data-stu-id="cc80e-111">targets : 'T[]</span></span>

<span data-ttu-id="cc80e-112">要应用最后一个目标的数组 `op` 。</span><span class="sxs-lookup"><span data-stu-id="cc80e-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="cc80e-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="cc80e-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="cc80e-114">类型参数</span><span class="sxs-lookup"><span data-stu-id="cc80e-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="cc80e-115">找</span><span class="sxs-lookup"><span data-stu-id="cc80e-115">'T</span></span>

<span data-ttu-id="cc80e-116">要应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="cc80e-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="cc80e-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cc80e-117">See Also</span></span>

- [<span data-ttu-id="cc80e-118">Canon. ApplyToTailA</span><span class="sxs-lookup"><span data-stu-id="cc80e-118">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="cc80e-119">Canon. ApplyToTailC</span><span class="sxs-lookup"><span data-stu-id="cc80e-119">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)
- [<span data-ttu-id="cc80e-120">Canon. ApplyToTailCA</span><span class="sxs-lookup"><span data-stu-id="cc80e-120">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)