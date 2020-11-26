---
uid: Microsoft.Quantum.Canon.ApplyIfOneCA
title: ApplyIfOneCA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfOneCA
qsharp.summary: Applies a unitary operation conditioned on a classical result value being one.
ms.openlocfilehash: 29801ed0bec08d0ab818f237feb17c2a2a7af1e4
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218574"
---
# <a name="applyifoneca-operation"></a><span data-ttu-id="7d169-102">ApplyIfOneCA 操作</span><span class="sxs-lookup"><span data-stu-id="7d169-102">ApplyIfOneCA operation</span></span>

<span data-ttu-id="7d169-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7d169-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7d169-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7d169-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7d169-105">将一个条件为的单一操作应用于传统结果值为1的值。</span><span class="sxs-lookup"><span data-stu-id="7d169-105">Applies a unitary operation conditioned on a classical result value being one.</span></span>

```qsharp
operation ApplyIfOneCA<'T> (result : Result, (op : ('T => Unit is Adj + Ctl), target : 'T)) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="7d169-106">描述</span><span class="sxs-lookup"><span data-stu-id="7d169-106">Description</span></span>

<span data-ttu-id="7d169-107">给定一个操作 `op` 和一个结果值时 `result` ， `op` `target` 如果为， `result` 则应用于 `One` 。</span><span class="sxs-lookup"><span data-stu-id="7d169-107">Given an operation `op` and a result value `result`, applies `op` to the `target` if `result` is `One`.</span></span> <span data-ttu-id="7d169-108">如果 `Zero` 为，则不会发生任何事情 `target` 。</span><span class="sxs-lookup"><span data-stu-id="7d169-108">If `Zero`, nothing happens to the `target`.</span></span>
<span data-ttu-id="7d169-109">后缀 `CA` 指示要应用的操作是单一 (可控和 adjointable) 。</span><span class="sxs-lookup"><span data-stu-id="7d169-109">The suffix `CA` indicates that the operation to be applied is unitary (controllable and adjointable).</span></span>

## <a name="input"></a><span data-ttu-id="7d169-110">输入</span><span class="sxs-lookup"><span data-stu-id="7d169-110">Input</span></span>

### <a name="result--__invalidresult__"></a><span data-ttu-id="7d169-111">结果：__无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="7d169-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="7d169-112">用于控制是否应用 op 的测量结果。</span><span class="sxs-lookup"><span data-stu-id="7d169-112">A measurement result that controls whether op is applied or not.</span></span>


### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="7d169-113">op： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="7d169-113">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="7d169-114">要有条件地应用的操作。</span><span class="sxs-lookup"><span data-stu-id="7d169-114">An operation to be conditionally applied.</span></span>


### <a name="target--t"></a><span data-ttu-id="7d169-115">目标： t</span><span class="sxs-lookup"><span data-stu-id="7d169-115">target : 'T</span></span>

<span data-ttu-id="7d169-116">将操作应用到的输入。</span><span class="sxs-lookup"><span data-stu-id="7d169-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7d169-117">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7d169-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7d169-118">类型参数</span><span class="sxs-lookup"><span data-stu-id="7d169-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7d169-119">找</span><span class="sxs-lookup"><span data-stu-id="7d169-119">'T</span></span>

<span data-ttu-id="7d169-120">要有条件地应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="7d169-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="7d169-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7d169-121">See Also</span></span>

- [<span data-ttu-id="7d169-122">Canon. ApplyIfOneC</span><span class="sxs-lookup"><span data-stu-id="7d169-122">Microsoft.Quantum.Canon.ApplyIfOneC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneC)
- [<span data-ttu-id="7d169-123">Canon. ApplyIfOneA</span><span class="sxs-lookup"><span data-stu-id="7d169-123">Microsoft.Quantum.Canon.ApplyIfOneA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneA)
- [<span data-ttu-id="7d169-124">Canon. ApplyIfOneCA</span><span class="sxs-lookup"><span data-stu-id="7d169-124">Microsoft.Quantum.Canon.ApplyIfOneCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfOneCA)