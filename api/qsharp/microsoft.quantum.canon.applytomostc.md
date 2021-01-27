---
uid: Microsoft.Quantum.Canon.ApplyToMostC
title: ApplyToMostC 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostC
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 14de9f367aa7d19f64f13186d402239ae1fef3c1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850560"
---
# <a name="applytomostc-operation"></a><span data-ttu-id="c888c-102">ApplyToMostC 操作</span><span class="sxs-lookup"><span data-stu-id="c888c-102">ApplyToMostC operation</span></span>

<span data-ttu-id="c888c-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c888c-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c888c-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c888c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c888c-105">将操作应用到数组中除最后一个元素之外的所有元素。</span><span class="sxs-lookup"><span data-stu-id="c888c-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostC<'T> (op : ('T[] => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="c888c-106">说明</span><span class="sxs-lookup"><span data-stu-id="c888c-106">Description</span></span>

<span data-ttu-id="c888c-107">给定一个操作 `op` 和一个目标数组 `targets` ，适用于 `op(Most(targets))` 。</span><span class="sxs-lookup"><span data-stu-id="c888c-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="c888c-108">输入</span><span class="sxs-lookup"><span data-stu-id="c888c-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="c888c-109">op： t [] => [单位](xref:microsoft.quantum.lang-ref.unit)  为 Ctl</span><span class="sxs-lookup"><span data-stu-id="c888c-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="c888c-110">要应用的操作。</span><span class="sxs-lookup"><span data-stu-id="c888c-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="c888c-111">目标： t []</span><span class="sxs-lookup"><span data-stu-id="c888c-111">targets : 'T[]</span></span>

<span data-ttu-id="c888c-112">目标的数组，其中除最后一个外的所有将应用于 `op` 。</span><span class="sxs-lookup"><span data-stu-id="c888c-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c888c-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c888c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c888c-114">类型参数</span><span class="sxs-lookup"><span data-stu-id="c888c-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c888c-115">找</span><span class="sxs-lookup"><span data-stu-id="c888c-115">'T</span></span>

<span data-ttu-id="c888c-116">要应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="c888c-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="c888c-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c888c-117">See Also</span></span>

- [<span data-ttu-id="c888c-118">Canon. ApplyToMost</span><span class="sxs-lookup"><span data-stu-id="c888c-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="c888c-119">Canon. ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="c888c-119">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="c888c-120">Canon. ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="c888c-120">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)