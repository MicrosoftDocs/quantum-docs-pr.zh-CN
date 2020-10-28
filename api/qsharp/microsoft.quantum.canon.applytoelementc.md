---
uid: Microsoft.Quantum.Canon.ApplyToElementC
title: ApplyToElementC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementC
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: bd466ff59e6e962be9a7e58b6d298c60b0d1d90d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696237"
---
# <a name="applytoelementc-operation"></a><span data-ttu-id="9e462-102">ApplyToElementC 操作</span><span class="sxs-lookup"><span data-stu-id="9e462-102">ApplyToElementC operation</span></span>

<span data-ttu-id="9e462-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9e462-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9e462-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="9e462-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="9e462-105">将操作应用到数组的给定元素。</span><span class="sxs-lookup"><span data-stu-id="9e462-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementC<'T> (op : ('T => Unit is Ctl), index : Int, targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="9e462-106">说明</span><span class="sxs-lookup"><span data-stu-id="9e462-106">Description</span></span>

<span data-ttu-id="9e462-107">给定一个操作 `op` 、一个索引 `index` 和一个目标数组 `targets` ，适用于 `op(targets[index])` 。</span><span class="sxs-lookup"><span data-stu-id="9e462-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="9e462-108">输入</span><span class="sxs-lookup"><span data-stu-id="9e462-108">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="9e462-109">op： t => [单元](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="9e462-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="9e462-110">要应用的操作。</span><span class="sxs-lookup"><span data-stu-id="9e462-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="9e462-111">索引： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="9e462-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="9e462-112">目标数组中的索引。</span><span class="sxs-lookup"><span data-stu-id="9e462-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="9e462-113">目标： t []</span><span class="sxs-lookup"><span data-stu-id="9e462-113">targets : 'T[]</span></span>

<span data-ttu-id="9e462-114">的可能目标的数组 `op` 。</span><span class="sxs-lookup"><span data-stu-id="9e462-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9e462-115">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9e462-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9e462-116">类型参数</span><span class="sxs-lookup"><span data-stu-id="9e462-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9e462-117">找</span><span class="sxs-lookup"><span data-stu-id="9e462-117">'T</span></span>

<span data-ttu-id="9e462-118">要应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="9e462-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="9e462-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9e462-119">See Also</span></span>

- [<span data-ttu-id="9e462-120">Canon. ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="9e462-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="9e462-121">Canon. ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="9e462-121">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)
- [<span data-ttu-id="9e462-122">Canon. ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="9e462-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)