---
uid: Microsoft.Quantum.Canon.ApplyToRest
title: ApplyToRest 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRest
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: fe49361f3c2259960eaa58d47df9b69b30b572a8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208256"
---
# <a name="applytorest-operation"></a><span data-ttu-id="abac3-102">ApplyToRest 操作</span><span class="sxs-lookup"><span data-stu-id="abac3-102">ApplyToRest operation</span></span>

<span data-ttu-id="abac3-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="abac3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="abac3-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="abac3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="abac3-105">将操作应用到数组中除第一个元素之外的所有元素。</span><span class="sxs-lookup"><span data-stu-id="abac3-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRest<'T> (op : ('T[] => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="abac3-106">描述</span><span class="sxs-lookup"><span data-stu-id="abac3-106">Description</span></span>

<span data-ttu-id="abac3-107">给定一个操作 `op` 和一个目标数组 `targets` ，适用于 `op(Rest(targets))` 。</span><span class="sxs-lookup"><span data-stu-id="abac3-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="abac3-108">输入</span><span class="sxs-lookup"><span data-stu-id="abac3-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="abac3-109">op： t [] => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="abac3-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="abac3-110">要应用的操作。</span><span class="sxs-lookup"><span data-stu-id="abac3-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="abac3-111">目标： t []</span><span class="sxs-lookup"><span data-stu-id="abac3-111">targets : 'T[]</span></span>

<span data-ttu-id="abac3-112">目标数组，其中除第一个以外的所有将应用于 `op` 。</span><span class="sxs-lookup"><span data-stu-id="abac3-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="abac3-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="abac3-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="abac3-114">类型参数</span><span class="sxs-lookup"><span data-stu-id="abac3-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="abac3-115">找</span><span class="sxs-lookup"><span data-stu-id="abac3-115">'T</span></span>

<span data-ttu-id="abac3-116">要应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="abac3-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="abac3-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="abac3-117">See Also</span></span>

- [<span data-ttu-id="abac3-118">Canon. ApplyToRestA</span><span class="sxs-lookup"><span data-stu-id="abac3-118">Microsoft.Quantum.Canon.ApplyToRestA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [<span data-ttu-id="abac3-119">Canon. ApplyToRestC</span><span class="sxs-lookup"><span data-stu-id="abac3-119">Microsoft.Quantum.Canon.ApplyToRestC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestC)
- [<span data-ttu-id="abac3-120">Canon. ApplyToRestCA</span><span class="sxs-lookup"><span data-stu-id="abac3-120">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)