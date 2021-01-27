---
uid: Microsoft.Quantum.Canon.ApplyToElementCA
title: ApplyToElementCA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementCA
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: 420a92ae10d2fc260024968b1846e669c4b62d73
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841474"
---
# <a name="applytoelementca-operation"></a><span data-ttu-id="da349-102">ApplyToElementCA 操作</span><span class="sxs-lookup"><span data-stu-id="da349-102">ApplyToElementCA operation</span></span>

<span data-ttu-id="da349-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="da349-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="da349-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="da349-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="da349-105">将操作应用到数组的给定元素。</span><span class="sxs-lookup"><span data-stu-id="da349-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementCA<'T> (op : ('T => Unit is Adj + Ctl), index : Int, targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="da349-106">说明</span><span class="sxs-lookup"><span data-stu-id="da349-106">Description</span></span>

<span data-ttu-id="da349-107">给定一个操作 `op` 、一个索引 `index` 和一个目标数组 `targets` ，适用于 `op(targets[index])` 。</span><span class="sxs-lookup"><span data-stu-id="da349-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="da349-108">输入</span><span class="sxs-lookup"><span data-stu-id="da349-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="da349-109">op： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="da349-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="da349-110">要应用的操作。</span><span class="sxs-lookup"><span data-stu-id="da349-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="da349-111">索引： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="da349-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="da349-112">目标数组中的索引。</span><span class="sxs-lookup"><span data-stu-id="da349-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="da349-113">目标： t []</span><span class="sxs-lookup"><span data-stu-id="da349-113">targets : 'T[]</span></span>

<span data-ttu-id="da349-114">的可能目标的数组 `op` 。</span><span class="sxs-lookup"><span data-stu-id="da349-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="da349-115">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="da349-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="da349-116">类型参数</span><span class="sxs-lookup"><span data-stu-id="da349-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="da349-117">找</span><span class="sxs-lookup"><span data-stu-id="da349-117">'T</span></span>

<span data-ttu-id="da349-118">要应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="da349-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="da349-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="da349-119">See Also</span></span>

- [<span data-ttu-id="da349-120">Canon. ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="da349-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="da349-121">Canon. ApplyToElementC</span><span class="sxs-lookup"><span data-stu-id="da349-121">Microsoft.Quantum.Canon.ApplyToElementC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementC)
- [<span data-ttu-id="da349-122">Canon. ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="da349-122">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)