---
uid: Microsoft.Quantum.Canon.ApplyToMostCA
title: ApplyToMostCA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostCA
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 2ce76d2a86665fbfa5f5d91df23220c7c80981e3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96208408"
---
# <a name="applytomostca-operation"></a><span data-ttu-id="ee2a3-102">ApplyToMostCA 操作</span><span class="sxs-lookup"><span data-stu-id="ee2a3-102">ApplyToMostCA operation</span></span>

<span data-ttu-id="ee2a3-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ee2a3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ee2a3-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ee2a3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ee2a3-105">将操作应用到数组中除最后一个元素之外的所有元素。</span><span class="sxs-lookup"><span data-stu-id="ee2a3-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostCA<'T> (op : ('T[] => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="ee2a3-106">描述</span><span class="sxs-lookup"><span data-stu-id="ee2a3-106">Description</span></span>

<span data-ttu-id="ee2a3-107">给定一个操作 `op` 和一个目标数组 `targets` ，适用于 `op(Most(targets))` 。</span><span class="sxs-lookup"><span data-stu-id="ee2a3-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="ee2a3-108">输入</span><span class="sxs-lookup"><span data-stu-id="ee2a3-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="ee2a3-109">op： t [] => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="ee2a3-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="ee2a3-110">要应用的操作。</span><span class="sxs-lookup"><span data-stu-id="ee2a3-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="ee2a3-111">目标： t []</span><span class="sxs-lookup"><span data-stu-id="ee2a3-111">targets : 'T[]</span></span>

<span data-ttu-id="ee2a3-112">目标的数组，其中除最后一个外的所有将应用于 `op` 。</span><span class="sxs-lookup"><span data-stu-id="ee2a3-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ee2a3-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ee2a3-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ee2a3-114">类型参数</span><span class="sxs-lookup"><span data-stu-id="ee2a3-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ee2a3-115">找</span><span class="sxs-lookup"><span data-stu-id="ee2a3-115">'T</span></span>

<span data-ttu-id="ee2a3-116">要应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="ee2a3-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="ee2a3-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ee2a3-117">See Also</span></span>

- [<span data-ttu-id="ee2a3-118">Canon. ApplyToMost</span><span class="sxs-lookup"><span data-stu-id="ee2a3-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="ee2a3-119">Canon. ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="ee2a3-119">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="ee2a3-120">Canon. ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="ee2a3-120">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)