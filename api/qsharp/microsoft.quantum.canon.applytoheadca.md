---
uid: Microsoft.Quantum.Canon.ApplyToHeadCA
title: ApplyToHeadCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadCA
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: 5bb016373040b1b66984405ea2bda0b8cb0c5102
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696206"
---
# <a name="applytoheadca-operation"></a><span data-ttu-id="91643-102">ApplyToHeadCA 操作</span><span class="sxs-lookup"><span data-stu-id="91643-102">ApplyToHeadCA operation</span></span>

<span data-ttu-id="91643-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="91643-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="91643-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="91643-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="91643-105">将操作应用到数组的第一个元素。</span><span class="sxs-lookup"><span data-stu-id="91643-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadCA<'T> (op : ('T => Unit is Adj + Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="91643-106">说明</span><span class="sxs-lookup"><span data-stu-id="91643-106">Description</span></span>

<span data-ttu-id="91643-107">给定一个操作 `op` 和一个目标数组 `targets` ，适用于 `op(Head(targets))` 。</span><span class="sxs-lookup"><span data-stu-id="91643-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="91643-108">输入</span><span class="sxs-lookup"><span data-stu-id="91643-108">Input</span></span>

### <a name="op--t--unit-adj--ctl"></a><span data-ttu-id="91643-109">op： t => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="91643-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="91643-110">要应用的操作。</span><span class="sxs-lookup"><span data-stu-id="91643-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="91643-111">目标： t []</span><span class="sxs-lookup"><span data-stu-id="91643-111">targets : 'T[]</span></span>

<span data-ttu-id="91643-112">要应用第一个目标的目标数组 `op` 。</span><span class="sxs-lookup"><span data-stu-id="91643-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="91643-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="91643-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="91643-114">类型参数</span><span class="sxs-lookup"><span data-stu-id="91643-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="91643-115">找</span><span class="sxs-lookup"><span data-stu-id="91643-115">'T</span></span>

<span data-ttu-id="91643-116">要应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="91643-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="91643-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="91643-117">See Also</span></span>

- [<span data-ttu-id="91643-118">Canon. ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="91643-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="91643-119">Canon. ApplyToHeadA</span><span class="sxs-lookup"><span data-stu-id="91643-119">Microsoft.Quantum.Canon.ApplyToHeadA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadA)
- [<span data-ttu-id="91643-120">Canon. ApplyToHeadC</span><span class="sxs-lookup"><span data-stu-id="91643-120">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)