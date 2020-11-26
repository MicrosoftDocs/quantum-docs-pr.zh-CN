---
uid: Microsoft.Quantum.Canon.ApplyIfC
title: ApplyIfC 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfC
qsharp.summary: Applies a controllable operation conditioned on a classical bit.
ms.openlocfilehash: 35430cb7cf491965b7b69ace6d3f41599dbadd51
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218710"
---
# <a name="applyifc-operation"></a><span data-ttu-id="1cbbb-102">ApplyIfC 操作</span><span class="sxs-lookup"><span data-stu-id="1cbbb-102">ApplyIfC operation</span></span>

<span data-ttu-id="1cbbb-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="1cbbb-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="1cbbb-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1cbbb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1cbbb-105">应用采用传统位的可控操作。</span><span class="sxs-lookup"><span data-stu-id="1cbbb-105">Applies a controllable operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfC<'T> (op : ('T => Unit is Ctl), bit : Bool, target : 'T) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="1cbbb-106">描述</span><span class="sxs-lookup"><span data-stu-id="1cbbb-106">Description</span></span>

<span data-ttu-id="1cbbb-107">给定一个操作 `op` 和一个位值 `bit` 后， `op` 如果为，则应用于 `target` `bit` `true` 。</span><span class="sxs-lookup"><span data-stu-id="1cbbb-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="1cbbb-108">如果 `false` 为，则不会发生任何事情 `target` 。</span><span class="sxs-lookup"><span data-stu-id="1cbbb-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="1cbbb-109">后缀 `C` 指示要应用的操作可控制。</span><span class="sxs-lookup"><span data-stu-id="1cbbb-109">The suffix `C` indicates that the operation to be applied is controllable.</span></span>

## <a name="input"></a><span data-ttu-id="1cbbb-110">输入</span><span class="sxs-lookup"><span data-stu-id="1cbbb-110">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="1cbbb-111">op： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为 Ctl</span><span class="sxs-lookup"><span data-stu-id="1cbbb-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="1cbbb-112">要有条件地应用的操作。</span><span class="sxs-lookup"><span data-stu-id="1cbbb-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="1cbbb-113">bit： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="1cbbb-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="1cbbb-114">用于控制是否应用 op 的布尔值。</span><span class="sxs-lookup"><span data-stu-id="1cbbb-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="1cbbb-115">目标： t</span><span class="sxs-lookup"><span data-stu-id="1cbbb-115">target : 'T</span></span>

<span data-ttu-id="1cbbb-116">将操作应用到的输入。</span><span class="sxs-lookup"><span data-stu-id="1cbbb-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="1cbbb-117">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="1cbbb-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1cbbb-118">类型参数</span><span class="sxs-lookup"><span data-stu-id="1cbbb-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1cbbb-119">找</span><span class="sxs-lookup"><span data-stu-id="1cbbb-119">'T</span></span>

<span data-ttu-id="1cbbb-120">要有条件地应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="1cbbb-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="1cbbb-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1cbbb-121">See Also</span></span>

- [<span data-ttu-id="1cbbb-122">Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="1cbbb-122">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="1cbbb-123">Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="1cbbb-123">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="1cbbb-124">Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="1cbbb-124">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)