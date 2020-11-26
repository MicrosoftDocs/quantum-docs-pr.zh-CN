---
uid: Microsoft.Quantum.Canon.ApplyIfA
title: ApplyIfA 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfA
qsharp.summary: Applies a adjointable operation conditioned on a classical bit.
ms.openlocfilehash: d2880bbb95ebaf621ef9e5885051b94f32a3f1cc
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96218761"
---
# <a name="applyifa-operation"></a><span data-ttu-id="9b3c3-102">ApplyIfA 操作</span><span class="sxs-lookup"><span data-stu-id="9b3c3-102">ApplyIfA operation</span></span>

<span data-ttu-id="9b3c3-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="9b3c3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="9b3c3-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9b3c3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9b3c3-105">应用以传统位为依据的 adjointable 操作。</span><span class="sxs-lookup"><span data-stu-id="9b3c3-105">Applies a adjointable operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfA<'T> (op : ('T => Unit is Adj), bit : Bool, target : 'T) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="9b3c3-106">描述</span><span class="sxs-lookup"><span data-stu-id="9b3c3-106">Description</span></span>

<span data-ttu-id="9b3c3-107">给定一个操作 `op` 和一个位值 `bit` 后， `op` 如果为，则应用于 `target` `bit` `true` 。</span><span class="sxs-lookup"><span data-stu-id="9b3c3-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="9b3c3-108">如果 `false` 为，则不会发生任何事情 `target` 。</span><span class="sxs-lookup"><span data-stu-id="9b3c3-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="9b3c3-109">后缀 `A` 指示要应用的操作是 adjointable。</span><span class="sxs-lookup"><span data-stu-id="9b3c3-109">The suffix `A` indicates that the operation to be applied is adjointable.</span></span>

## <a name="input"></a><span data-ttu-id="9b3c3-110">输入</span><span class="sxs-lookup"><span data-stu-id="9b3c3-110">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="9b3c3-111">op： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词</span><span class="sxs-lookup"><span data-stu-id="9b3c3-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="9b3c3-112">要有条件地应用的操作。</span><span class="sxs-lookup"><span data-stu-id="9b3c3-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="9b3c3-113">bit： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="9b3c3-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="9b3c3-114">用于控制是否应用 op 的布尔值。</span><span class="sxs-lookup"><span data-stu-id="9b3c3-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="9b3c3-115">目标： t</span><span class="sxs-lookup"><span data-stu-id="9b3c3-115">target : 'T</span></span>

<span data-ttu-id="9b3c3-116">将操作应用到的输入。</span><span class="sxs-lookup"><span data-stu-id="9b3c3-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="9b3c3-117">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9b3c3-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9b3c3-118">类型参数</span><span class="sxs-lookup"><span data-stu-id="9b3c3-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9b3c3-119">找</span><span class="sxs-lookup"><span data-stu-id="9b3c3-119">'T</span></span>

<span data-ttu-id="9b3c3-120">要有条件地应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="9b3c3-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="9b3c3-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9b3c3-121">See Also</span></span>

- [<span data-ttu-id="9b3c3-122">Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="9b3c3-122">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="9b3c3-123">Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="9b3c3-123">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="9b3c3-124">Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="9b3c3-124">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)