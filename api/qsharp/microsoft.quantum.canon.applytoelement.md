---
uid: Microsoft.Quantum.Canon.ApplyToElement
title: ApplyToElement 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElement
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 8cbc42a1c43b4c9a037729671eb3c82d365af580
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217617"
---
# <a name="applytoelement-operation"></a><span data-ttu-id="51b95-102">ApplyToElement 操作</span><span class="sxs-lookup"><span data-stu-id="51b95-102">ApplyToElement operation</span></span>

<span data-ttu-id="51b95-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="51b95-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="51b95-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="51b95-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="51b95-105">将操作应用到数组的给定元素。</span><span class="sxs-lookup"><span data-stu-id="51b95-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElement<'T> (op : ('T => Unit), index : Int, targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="51b95-106">描述</span><span class="sxs-lookup"><span data-stu-id="51b95-106">Description</span></span>

<span data-ttu-id="51b95-107">给定一个操作 `op` 、一个索引 `index` 和一个目标数组 `targets` ，适用于 `op(targets[index])` 。</span><span class="sxs-lookup"><span data-stu-id="51b95-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="51b95-108">输入</span><span class="sxs-lookup"><span data-stu-id="51b95-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="51b95-109">op： t => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="51b95-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="51b95-110">要应用的操作。</span><span class="sxs-lookup"><span data-stu-id="51b95-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="51b95-111">索引： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="51b95-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="51b95-112">目标数组中的索引。</span><span class="sxs-lookup"><span data-stu-id="51b95-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="51b95-113">目标： t []</span><span class="sxs-lookup"><span data-stu-id="51b95-113">targets : 'T[]</span></span>

<span data-ttu-id="51b95-114">的可能目标的数组 `op` 。</span><span class="sxs-lookup"><span data-stu-id="51b95-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="51b95-115">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="51b95-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="51b95-116">类型参数</span><span class="sxs-lookup"><span data-stu-id="51b95-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="51b95-117">找</span><span class="sxs-lookup"><span data-stu-id="51b95-117">'T</span></span>

<span data-ttu-id="51b95-118">要应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="51b95-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="51b95-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="51b95-119">See Also</span></span>

- [<span data-ttu-id="51b95-120">Canon. ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="51b95-120">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="51b95-121">Canon. ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="51b95-121">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)
- [<span data-ttu-id="51b95-122">Canon. ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="51b95-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)