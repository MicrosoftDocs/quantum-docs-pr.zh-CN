---
uid: Microsoft.Quantum.Canon.ApplyToHeadC
title: ApplyToHeadC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadC
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 3ff6c25837f1219dd456bf1739a2953ff72e2df9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696208"
---
# <a name="applytoheadc-operation"></a><span data-ttu-id="36c8d-102">ApplyToHeadC 操作</span><span class="sxs-lookup"><span data-stu-id="36c8d-102">ApplyToHeadC operation</span></span>

<span data-ttu-id="36c8d-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="36c8d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="36c8d-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="36c8d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="36c8d-105">将操作应用到数组的第一个元素。</span><span class="sxs-lookup"><span data-stu-id="36c8d-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadC<'T> (op : ('T => Unit is Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="36c8d-106">说明</span><span class="sxs-lookup"><span data-stu-id="36c8d-106">Description</span></span>

<span data-ttu-id="36c8d-107">给定一个操作 `op` 和一个目标数组 `targets` ，适用于 `op(Head(targets))` 。</span><span class="sxs-lookup"><span data-stu-id="36c8d-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="36c8d-108">输入</span><span class="sxs-lookup"><span data-stu-id="36c8d-108">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="36c8d-109">op： t => [单元](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="36c8d-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="36c8d-110">要应用的操作。</span><span class="sxs-lookup"><span data-stu-id="36c8d-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="36c8d-111">目标： t []</span><span class="sxs-lookup"><span data-stu-id="36c8d-111">targets : 'T[]</span></span>

<span data-ttu-id="36c8d-112">要应用第一个目标的目标数组 `op` 。</span><span class="sxs-lookup"><span data-stu-id="36c8d-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="36c8d-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="36c8d-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="36c8d-114">类型参数</span><span class="sxs-lookup"><span data-stu-id="36c8d-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="36c8d-115">找</span><span class="sxs-lookup"><span data-stu-id="36c8d-115">'T</span></span>

<span data-ttu-id="36c8d-116">要应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="36c8d-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="36c8d-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="36c8d-117">See Also</span></span>

- [<span data-ttu-id="36c8d-118">Canon. ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="36c8d-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="36c8d-119">Canon. ApplyToHeadA</span><span class="sxs-lookup"><span data-stu-id="36c8d-119">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="36c8d-120">Canon. ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="36c8d-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)