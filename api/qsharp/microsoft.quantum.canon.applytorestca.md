---
uid: Microsoft.Quantum.Canon.ApplyToRestCA
title: ApplyToRestCA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestCA
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 3123c7f7b5e5c7f5cb17a34eedc81b3912109883
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208153"
---
# <a name="applytorestca-operation"></a><span data-ttu-id="332b2-102">ApplyToRestCA 操作</span><span class="sxs-lookup"><span data-stu-id="332b2-102">ApplyToRestCA operation</span></span>

<span data-ttu-id="332b2-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="332b2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="332b2-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="332b2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="332b2-105">将操作应用到数组中除第一个元素之外的所有元素。</span><span class="sxs-lookup"><span data-stu-id="332b2-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestCA<'T> (op : ('T[] => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="332b2-106">描述</span><span class="sxs-lookup"><span data-stu-id="332b2-106">Description</span></span>

<span data-ttu-id="332b2-107">给定一个操作 `op` 和一个目标数组 `targets` ，适用于 `op(Rest(targets))` 。</span><span class="sxs-lookup"><span data-stu-id="332b2-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="332b2-108">输入</span><span class="sxs-lookup"><span data-stu-id="332b2-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="332b2-109">op： t [] => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="332b2-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="332b2-110">要应用的操作。</span><span class="sxs-lookup"><span data-stu-id="332b2-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="332b2-111">目标： t []</span><span class="sxs-lookup"><span data-stu-id="332b2-111">targets : 'T[]</span></span>

<span data-ttu-id="332b2-112">目标数组，其中除第一个以外的所有将应用于 `op` 。</span><span class="sxs-lookup"><span data-stu-id="332b2-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="332b2-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="332b2-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="332b2-114">类型参数</span><span class="sxs-lookup"><span data-stu-id="332b2-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="332b2-115">找</span><span class="sxs-lookup"><span data-stu-id="332b2-115">'T</span></span>

<span data-ttu-id="332b2-116">要应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="332b2-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="332b2-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="332b2-117">See Also</span></span>

- [<span data-ttu-id="332b2-118">Canon. ApplyToRest</span><span class="sxs-lookup"><span data-stu-id="332b2-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="332b2-119">Canon. ApplyToRestA</span><span class="sxs-lookup"><span data-stu-id="332b2-119">Microsoft.Quantum.Canon.ApplyToRestA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [<span data-ttu-id="332b2-120">Canon. ApplyToRestC</span><span class="sxs-lookup"><span data-stu-id="332b2-120">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)