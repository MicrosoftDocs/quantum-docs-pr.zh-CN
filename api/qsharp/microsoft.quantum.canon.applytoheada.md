---
uid: Microsoft.Quantum.Canon.ApplyToHeadA
title: ApplyToHeadA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToHeadA
qsharp.summary: Applies an operation to the first element of an array.
ms.openlocfilehash: ba060243cb01782fd8529e0b05ee7258a66314f5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696209"
---
# <a name="applytoheada-operation"></a><span data-ttu-id="afdc5-102">ApplyToHeadA 操作</span><span class="sxs-lookup"><span data-stu-id="afdc5-102">ApplyToHeadA operation</span></span>

<span data-ttu-id="afdc5-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="afdc5-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="afdc5-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="afdc5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="afdc5-105">将操作应用到数组的第一个元素。</span><span class="sxs-lookup"><span data-stu-id="afdc5-105">Applies an operation to the first element of an array.</span></span>

```qsharp
operation ApplyToHeadA<'T> (op : ('T => Unit is Adj), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="afdc5-106">说明</span><span class="sxs-lookup"><span data-stu-id="afdc5-106">Description</span></span>

<span data-ttu-id="afdc5-107">给定一个操作 `op` 和一个目标数组 `targets` ，适用于 `op(Head(targets))` 。</span><span class="sxs-lookup"><span data-stu-id="afdc5-107">Given an operation `op` and an array of targets `targets`, applies `op(Head(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="afdc5-108">输入</span><span class="sxs-lookup"><span data-stu-id="afdc5-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="afdc5-109">op： t => [单位](xref:microsoft.quantum.lang-ref.unit) 形容词</span><span class="sxs-lookup"><span data-stu-id="afdc5-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="afdc5-110">要应用的操作。</span><span class="sxs-lookup"><span data-stu-id="afdc5-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="afdc5-111">目标： t []</span><span class="sxs-lookup"><span data-stu-id="afdc5-111">targets : 'T[]</span></span>

<span data-ttu-id="afdc5-112">要应用第一个目标的目标数组 `op` 。</span><span class="sxs-lookup"><span data-stu-id="afdc5-112">An array of targets, of which the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="afdc5-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="afdc5-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="afdc5-114">类型参数</span><span class="sxs-lookup"><span data-stu-id="afdc5-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="afdc5-115">找</span><span class="sxs-lookup"><span data-stu-id="afdc5-115">'T</span></span>

<span data-ttu-id="afdc5-116">要应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="afdc5-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="afdc5-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="afdc5-117">See Also</span></span>

- [<span data-ttu-id="afdc5-118">Canon. ApplyToHead</span><span class="sxs-lookup"><span data-stu-id="afdc5-118">Microsoft.Quantum.Canon.ApplyToHead</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHead)
- [<span data-ttu-id="afdc5-119">Canon. ApplyToHeadC</span><span class="sxs-lookup"><span data-stu-id="afdc5-119">Microsoft.Quantum.Canon.ApplyToHeadC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadC)
- [<span data-ttu-id="afdc5-120">Canon. ApplyToHeadCA</span><span class="sxs-lookup"><span data-stu-id="afdc5-120">Microsoft.Quantum.Canon.ApplyToHeadCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToHeadCA)