---
uid: Microsoft.Quantum.Canon.ApplyIfOne
title: ApplyIfOne 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOne
qsharp.summary: Applies an operation conditioned on a classical result value being one.
ms.openlocfilehash: b86aecf3dc3d02d1a6bf0c112bdc45a55a2cf087
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841765"
---
# <a name="applyifone-operation"></a><span data-ttu-id="a713d-102">ApplyIfOne 操作</span><span class="sxs-lookup"><span data-stu-id="a713d-102">ApplyIfOne operation</span></span>

<span data-ttu-id="a713d-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="a713d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="a713d-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a713d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a713d-105">应用对经典结果值为1的操作。</span><span class="sxs-lookup"><span data-stu-id="a713d-105">Applies an operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOne<'T> (result : Result, (op : ('T => Unit), target : 'T)) : Unit
```


## <a name="description"></a><span data-ttu-id="a713d-106">说明</span><span class="sxs-lookup"><span data-stu-id="a713d-106">Description</span></span>

<span data-ttu-id="a713d-107">给定一个操作 `op` 和一个结果值时 `result` ， `op` `target` 如果为， `result` 则应用于 `One` 。</span><span class="sxs-lookup"><span data-stu-id="a713d-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="a713d-108">如果 `Zero` 为，则不会发生任何事情 `target` 。</span><span class="sxs-lookup"><span data-stu-id="a713d-108">If `Zero`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="a713d-109">输入</span><span class="sxs-lookup"><span data-stu-id="a713d-109">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="a713d-110">结果：__无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="a713d-110">result : __invalid<Result>__</span></span>

<span data-ttu-id="a713d-111">用于控制是否应用 op 的测量结果。</span><span class="sxs-lookup"><span data-stu-id="a713d-111">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit"></a><span data-ttu-id="a713d-112">op： t => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a713d-112">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="a713d-113">要有条件地应用的操作。</span><span class="sxs-lookup"><span data-stu-id="a713d-113">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="a713d-114">目标： t</span><span class="sxs-lookup"><span data-stu-id="a713d-114">target : 'T</span></span>

<span data-ttu-id="a713d-115">将操作应用到的输入。</span><span class="sxs-lookup"><span data-stu-id="a713d-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a713d-116">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a713d-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="a713d-117">类型参数</span><span class="sxs-lookup"><span data-stu-id="a713d-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a713d-118">找</span><span class="sxs-lookup"><span data-stu-id="a713d-118">'T</span></span>

<span data-ttu-id="a713d-119">要有条件地应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="a713d-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="a713d-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a713d-120">See Also</span></span>

- [<span data-ttu-id="a713d-121">Canon. ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="a713d-121">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="a713d-122">Canon. ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="a713d-122">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="a713d-123">Canon. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="a713d-123">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)