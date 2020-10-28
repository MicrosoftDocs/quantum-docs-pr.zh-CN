---
uid: Microsoft.Quantum.Canon.ApplyToElement
title: ApplyToElement 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElement
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 5c321d95c9b79bc50827c2b50c406b164e143dc6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696245"
---
# <a name="applytoelement-operation"></a><span data-ttu-id="4b349-102">ApplyToElement 操作</span><span class="sxs-lookup"><span data-stu-id="4b349-102">ApplyToElement operation</span></span>

<span data-ttu-id="4b349-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="4b349-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="4b349-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="4b349-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="4b349-105">将操作应用到数组的给定元素。</span><span class="sxs-lookup"><span data-stu-id="4b349-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElement<'T> (op : ('T => Unit), index : Int, targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="4b349-106">说明</span><span class="sxs-lookup"><span data-stu-id="4b349-106">Description</span></span>

<span data-ttu-id="4b349-107">给定一个操作 `op` 、一个索引 `index` 和一个目标数组 `targets` ，适用于 `op(targets[index])` 。</span><span class="sxs-lookup"><span data-stu-id="4b349-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="4b349-108">输入</span><span class="sxs-lookup"><span data-stu-id="4b349-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="4b349-109">op： t => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4b349-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="4b349-110">要应用的操作。</span><span class="sxs-lookup"><span data-stu-id="4b349-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="4b349-111">索引： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4b349-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4b349-112">目标数组中的索引。</span><span class="sxs-lookup"><span data-stu-id="4b349-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="4b349-113">目标： t []</span><span class="sxs-lookup"><span data-stu-id="4b349-113">targets : 'T[]</span></span>

<span data-ttu-id="4b349-114">的可能目标的数组 `op` 。</span><span class="sxs-lookup"><span data-stu-id="4b349-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="4b349-115">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="4b349-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="4b349-116">类型参数</span><span class="sxs-lookup"><span data-stu-id="4b349-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="4b349-117">找</span><span class="sxs-lookup"><span data-stu-id="4b349-117">'T</span></span>

<span data-ttu-id="4b349-118">要应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="4b349-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="4b349-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4b349-119">See Also</span></span>

- [<span data-ttu-id="4b349-120">Canon. ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="4b349-120">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="4b349-121">Canon. ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="4b349-121">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)
- [<span data-ttu-id="4b349-122">Canon. ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="4b349-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)