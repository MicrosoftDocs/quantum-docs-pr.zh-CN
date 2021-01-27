---
uid: Microsoft.Quantum.Canon.ApplyToElementC
title: ApplyToElementC 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToElementC
qsharp.summary: Applies an operation to a given element of an array.
ms.openlocfilehash: bc63b6b591781a6283b872ef0c2509094a656b4c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850749"
---
# <a name="applytoelementc-operation"></a><span data-ttu-id="b1521-102">ApplyToElementC 操作</span><span class="sxs-lookup"><span data-stu-id="b1521-102">ApplyToElementC operation</span></span>

<span data-ttu-id="b1521-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b1521-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b1521-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b1521-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b1521-105">将操作应用到数组的给定元素。</span><span class="sxs-lookup"><span data-stu-id="b1521-105">Applies an operation to a given element of an array.</span></span>

```qsharp
operation ApplyToElementC<'T> (op : ('T => Unit is Ctl), index : Int, targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="b1521-106">说明</span><span class="sxs-lookup"><span data-stu-id="b1521-106">Description</span></span>

<span data-ttu-id="b1521-107">给定一个操作 `op` 、一个索引 `index` 和一个目标数组 `targets` ，适用于 `op(targets[index])` 。</span><span class="sxs-lookup"><span data-stu-id="b1521-107">Given an operation `op`, an index `index`, and an array of targets `targets`, applies `op(targets[index])`.</span></span>

## <a name="input"></a><span data-ttu-id="b1521-108">输入</span><span class="sxs-lookup"><span data-stu-id="b1521-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="b1521-109">op： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为 Ctl</span><span class="sxs-lookup"><span data-stu-id="b1521-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="b1521-110">要应用的操作。</span><span class="sxs-lookup"><span data-stu-id="b1521-110">An operation to be applied.</span></span>


### <a name="index--int"></a><span data-ttu-id="b1521-111">索引： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b1521-111">index : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b1521-112">目标数组中的索引。</span><span class="sxs-lookup"><span data-stu-id="b1521-112">An index into the array of targets.</span></span>


### <a name="targets--t"></a><span data-ttu-id="b1521-113">目标： t []</span><span class="sxs-lookup"><span data-stu-id="b1521-113">targets : 'T[]</span></span>

<span data-ttu-id="b1521-114">的可能目标的数组 `op` 。</span><span class="sxs-lookup"><span data-stu-id="b1521-114">An array of possible targets for `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b1521-115">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b1521-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b1521-116">类型参数</span><span class="sxs-lookup"><span data-stu-id="b1521-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b1521-117">找</span><span class="sxs-lookup"><span data-stu-id="b1521-117">'T</span></span>

<span data-ttu-id="b1521-118">要应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="b1521-118">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="b1521-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b1521-119">See Also</span></span>

- [<span data-ttu-id="b1521-120">Canon. ApplyToElement</span><span class="sxs-lookup"><span data-stu-id="b1521-120">Microsoft.Quantum.Canon.ApplyToElement</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElement)
- [<span data-ttu-id="b1521-121">Canon. ApplyToElementA</span><span class="sxs-lookup"><span data-stu-id="b1521-121">Microsoft.Quantum.Canon.ApplyToElementA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementA)
- [<span data-ttu-id="b1521-122">Canon. ApplyToElementCA</span><span class="sxs-lookup"><span data-stu-id="b1521-122">Microsoft.Quantum.Canon.ApplyToElementCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToElementCA)