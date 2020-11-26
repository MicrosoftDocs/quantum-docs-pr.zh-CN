---
uid: Microsoft.Quantum.Canon.ApplyIfCA
title: ApplyIfCA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfCA
qsharp.summary: Applies a unitary operation conditioned on a classical bit.
ms.openlocfilehash: b0ac469d6dea51951e0d9b2cfceb54253d4b4c5d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209615"
---
# <a name="applyifca-operation"></a><span data-ttu-id="bebaa-102">ApplyIfCA 操作</span><span class="sxs-lookup"><span data-stu-id="bebaa-102">ApplyIfCA operation</span></span>

<span data-ttu-id="bebaa-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="bebaa-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="bebaa-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="bebaa-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="bebaa-105">应用在传统上有条件的单一操作。</span><span class="sxs-lookup"><span data-stu-id="bebaa-105">Applies a unitary operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfCA<'T> (op : ('T => Unit is Ctl + Adj), bit : Bool, target : 'T) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="bebaa-106">描述</span><span class="sxs-lookup"><span data-stu-id="bebaa-106">Description</span></span>

<span data-ttu-id="bebaa-107">给定一个操作 `op` 和一个位值 `bit` 后， `op` 如果为，则应用于 `target` `bit` `true` 。</span><span class="sxs-lookup"><span data-stu-id="bebaa-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="bebaa-108">如果 `false` 为，则不会发生任何事情 `target` 。</span><span class="sxs-lookup"><span data-stu-id="bebaa-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="bebaa-109">后缀 `CA` 指示要应用的操作是单一 (可控和 adjointable) 。</span><span class="sxs-lookup"><span data-stu-id="bebaa-109">The suffix `CA` indicates that the operation to be applied is unitary (controllable and adjointable).</span></span>

## <a name="input"></a><span data-ttu-id="bebaa-110">输入</span><span class="sxs-lookup"><span data-stu-id="bebaa-110">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="bebaa-111">op： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="bebaa-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="bebaa-112">要有条件地应用的操作。</span><span class="sxs-lookup"><span data-stu-id="bebaa-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="bebaa-113">bit： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="bebaa-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="bebaa-114">用于控制是否应用 op 的布尔值。</span><span class="sxs-lookup"><span data-stu-id="bebaa-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="bebaa-115">目标： t</span><span class="sxs-lookup"><span data-stu-id="bebaa-115">target : 'T</span></span>

<span data-ttu-id="bebaa-116">将操作应用到的输入。</span><span class="sxs-lookup"><span data-stu-id="bebaa-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bebaa-117">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bebaa-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="bebaa-118">类型参数</span><span class="sxs-lookup"><span data-stu-id="bebaa-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="bebaa-119">找</span><span class="sxs-lookup"><span data-stu-id="bebaa-119">'T</span></span>

<span data-ttu-id="bebaa-120">要有条件地应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="bebaa-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="bebaa-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bebaa-121">See Also</span></span>

- [<span data-ttu-id="bebaa-122">Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="bebaa-122">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="bebaa-123">Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="bebaa-123">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="bebaa-124">Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="bebaa-124">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)