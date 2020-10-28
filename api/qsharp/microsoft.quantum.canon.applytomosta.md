---
uid: Microsoft.Quantum.Canon.ApplyToMostA
title: ApplyToMostA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostA
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 994cada2952809dc84a70b76dc4ede8286c89855
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696202"
---
# <a name="applytomosta-operation"></a><span data-ttu-id="d5935-102">ApplyToMostA 操作</span><span class="sxs-lookup"><span data-stu-id="d5935-102">ApplyToMostA operation</span></span>

<span data-ttu-id="d5935-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d5935-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d5935-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d5935-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d5935-105">将操作应用到数组中除最后一个元素之外的所有元素。</span><span class="sxs-lookup"><span data-stu-id="d5935-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostA<'T> (op : ('T[] => Unit is Adj), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="d5935-106">说明</span><span class="sxs-lookup"><span data-stu-id="d5935-106">Description</span></span>

<span data-ttu-id="d5935-107">给定一个操作 `op` 和一个目标数组 `targets` ，适用于 `op(Most(targets))` 。</span><span class="sxs-lookup"><span data-stu-id="d5935-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="d5935-108">输入</span><span class="sxs-lookup"><span data-stu-id="d5935-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="d5935-109">op： t [] => [单位](xref:microsoft.quantum.lang-ref.unit) 形容词</span><span class="sxs-lookup"><span data-stu-id="d5935-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="d5935-110">要应用的操作。</span><span class="sxs-lookup"><span data-stu-id="d5935-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="d5935-111">目标： t []</span><span class="sxs-lookup"><span data-stu-id="d5935-111">targets : 'T[]</span></span>

<span data-ttu-id="d5935-112">目标的数组，其中除最后一个外的所有将应用于 `op` 。</span><span class="sxs-lookup"><span data-stu-id="d5935-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="d5935-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="d5935-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="d5935-114">类型参数</span><span class="sxs-lookup"><span data-stu-id="d5935-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d5935-115">找</span><span class="sxs-lookup"><span data-stu-id="d5935-115">'T</span></span>

<span data-ttu-id="d5935-116">要应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="d5935-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="d5935-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d5935-117">See Also</span></span>

- [<span data-ttu-id="d5935-118">Canon. ApplyToMost</span><span class="sxs-lookup"><span data-stu-id="d5935-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="d5935-119">Canon. ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="d5935-119">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)
- [<span data-ttu-id="d5935-120">Canon. ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="d5935-120">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)