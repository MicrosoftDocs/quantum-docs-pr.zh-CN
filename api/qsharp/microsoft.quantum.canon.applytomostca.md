---
uid: Microsoft.Quantum.Canon.ApplyToMostCA
title: ApplyToMostCA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostCA
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 797cbd835446f31b2df60dbb184f888e6d0356aa
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696196"
---
# <a name="applytomostca-operation"></a><span data-ttu-id="beca2-102">ApplyToMostCA 操作</span><span class="sxs-lookup"><span data-stu-id="beca2-102">ApplyToMostCA operation</span></span>

<span data-ttu-id="beca2-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="beca2-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="beca2-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="beca2-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="beca2-105">将操作应用到数组中除最后一个元素之外的所有元素。</span><span class="sxs-lookup"><span data-stu-id="beca2-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostCA<'T> (op : ('T[] => Unit is Adj + Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="beca2-106">说明</span><span class="sxs-lookup"><span data-stu-id="beca2-106">Description</span></span>

<span data-ttu-id="beca2-107">给定一个操作 `op` 和一个目标数组 `targets` ，适用于 `op(Most(targets))` 。</span><span class="sxs-lookup"><span data-stu-id="beca2-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="beca2-108">输入</span><span class="sxs-lookup"><span data-stu-id="beca2-108">Input</span></span>

### <a name="op--t--unit-adj--ctl"></a><span data-ttu-id="beca2-109">op： t [] => [单位](xref:microsoft.quantum.lang-ref.unit) 调整 + Ctl</span><span class="sxs-lookup"><span data-stu-id="beca2-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="beca2-110">要应用的操作。</span><span class="sxs-lookup"><span data-stu-id="beca2-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="beca2-111">目标： t []</span><span class="sxs-lookup"><span data-stu-id="beca2-111">targets : 'T[]</span></span>

<span data-ttu-id="beca2-112">目标的数组，其中除最后一个外的所有将应用于 `op` 。</span><span class="sxs-lookup"><span data-stu-id="beca2-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="beca2-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="beca2-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="beca2-114">类型参数</span><span class="sxs-lookup"><span data-stu-id="beca2-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="beca2-115">找</span><span class="sxs-lookup"><span data-stu-id="beca2-115">'T</span></span>

<span data-ttu-id="beca2-116">要应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="beca2-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="beca2-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="beca2-117">See Also</span></span>

- [<span data-ttu-id="beca2-118">Canon. ApplyToMost</span><span class="sxs-lookup"><span data-stu-id="beca2-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="beca2-119">Canon. ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="beca2-119">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="beca2-120">Canon. ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="beca2-120">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)