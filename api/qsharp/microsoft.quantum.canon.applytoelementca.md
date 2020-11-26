---
uid: Microsoft.Quantum.Canon.ApplyToElementCA
title: ApplyToElementCA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementCA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 8ae4ece0d3d56ea2be1ce494ab0c5ee7caacbbf8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208850"
---
# <a name="applytoelementca-operation"></a><span data-ttu-id="14c29-102">ApplyToElementCA 操作</span><span class="sxs-lookup"><span data-stu-id="14c29-102">ApplyToElementCA operation</span></span>

<span data-ttu-id="14c29-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="14c29-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="14c29-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="14c29-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="14c29-105">将操作应用到数组的给定元素。</span><span class="sxs-lookup"><span data-stu-id="14c29-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementCA<'T> (op : ('T => Unit is Adj + Ctl), index : Int, targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="14c29-106">描述</span><span class="sxs-lookup"><span data-stu-id="14c29-106">Description</span></span>

<span data-ttu-id="14c29-107">给定一个操作 `op` 、一个索引 `index` 和一个目标数组 `targets` ，适用于 `op(targets[index])` 。</span><span class="sxs-lookup"><span data-stu-id="14c29-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="14c29-108">输入</span><span class="sxs-lookup"><span data-stu-id="14c29-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="14c29-109">op： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="14c29-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="14c29-110">要应用的操作。</span><span class="sxs-lookup"><span data-stu-id="14c29-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="14c29-111">索引： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="14c29-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="14c29-112">目标数组中的索引。</span><span class="sxs-lookup"><span data-stu-id="14c29-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="14c29-113">目标： t []</span><span class="sxs-lookup"><span data-stu-id="14c29-113">targets : 'T[]</span></span>

<span data-ttu-id="14c29-114">的可能目标的数组 `op` 。</span><span class="sxs-lookup"><span data-stu-id="14c29-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="14c29-115">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="14c29-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="14c29-116">类型参数</span><span class="sxs-lookup"><span data-stu-id="14c29-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="14c29-117">找</span><span class="sxs-lookup"><span data-stu-id="14c29-117">'T</span></span>

<span data-ttu-id="14c29-118">要应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="14c29-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="14c29-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="14c29-119">See Also</span></span>

- [<span data-ttu-id="14c29-120">Canon. ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="14c29-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="14c29-121">Canon. ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="14c29-121">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="14c29-122">Canon. ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="14c29-122">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)