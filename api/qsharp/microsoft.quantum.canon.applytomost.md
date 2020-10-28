---
uid: Microsoft.Quantum.Canon.ApplyToMost
title: ApplyToMost 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMost
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 2c6c8873859439e71436f6beb0de40dfd1e21f43
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696205"
---
# <a name="applytomost-operation"></a><span data-ttu-id="90bb4-102">ApplyToMost 操作</span><span class="sxs-lookup"><span data-stu-id="90bb4-102">ApplyToMost operation</span></span>

<span data-ttu-id="90bb4-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="90bb4-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="90bb4-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="90bb4-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="90bb4-105">将操作应用到数组中除最后一个元素之外的所有元素。</span><span class="sxs-lookup"><span data-stu-id="90bb4-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMost<'T> (op : ('T[] => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="90bb4-106">说明</span><span class="sxs-lookup"><span data-stu-id="90bb4-106">Description</span></span>

<span data-ttu-id="90bb4-107">给定一个操作 `op` 和一个目标数组 `targets` ，适用于 `op(Most(targets))` 。</span><span class="sxs-lookup"><span data-stu-id="90bb4-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="90bb4-108">输入</span><span class="sxs-lookup"><span data-stu-id="90bb4-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="90bb4-109">op： t [] => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="90bb4-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="90bb4-110">要应用的操作。</span><span class="sxs-lookup"><span data-stu-id="90bb4-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="90bb4-111">目标： t []</span><span class="sxs-lookup"><span data-stu-id="90bb4-111">targets : 'T[]</span></span>

<span data-ttu-id="90bb4-112">目标的数组，其中除最后一个外的所有将应用于 `op` 。</span><span class="sxs-lookup"><span data-stu-id="90bb4-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="90bb4-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="90bb4-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="90bb4-114">类型参数</span><span class="sxs-lookup"><span data-stu-id="90bb4-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="90bb4-115">找</span><span class="sxs-lookup"><span data-stu-id="90bb4-115">'T</span></span>

<span data-ttu-id="90bb4-116">要应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="90bb4-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="90bb4-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="90bb4-117">See Also</span></span>

- [<span data-ttu-id="90bb4-118">Canon. ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="90bb4-118">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="90bb4-119">Canon. ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="90bb4-119">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)
- [<span data-ttu-id="90bb4-120">Canon. ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="90bb4-120">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)