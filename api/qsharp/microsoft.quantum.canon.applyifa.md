---
uid: Microsoft.Quantum.Canon.ApplyIfA
title: ApplyIfA 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIfA
qsharp.summary: Applies a adjointable operation conditioned on a classical bit.
ms.openlocfilehash: 279a069176ee24ed83406f72170462bf58c790d9
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696352"
---
# <a name="applyifa-operation"></a><span data-ttu-id="eb0ce-102">ApplyIfA 操作</span><span class="sxs-lookup"><span data-stu-id="eb0ce-102">ApplyIfA operation</span></span>

<span data-ttu-id="eb0ce-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="eb0ce-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="eb0ce-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="eb0ce-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="eb0ce-105">应用以传统位为依据的 adjointable 操作。</span><span class="sxs-lookup"><span data-stu-id="eb0ce-105">Applies a adjointable operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIfA<'T> (op : ('T => Unit is Adj), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="eb0ce-106">说明</span><span class="sxs-lookup"><span data-stu-id="eb0ce-106">Description</span></span>

<span data-ttu-id="eb0ce-107">给定一个操作 `op` 和一个位值 `bit` 后， `op` 如果为，则应用于 `target` `bit` `true` 。</span><span class="sxs-lookup"><span data-stu-id="eb0ce-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="eb0ce-108">如果 `false` 为，则不会发生任何事情 `target` 。</span><span class="sxs-lookup"><span data-stu-id="eb0ce-108">If `false`, nothing happens to the `target`.</span></span>
<span data-ttu-id="eb0ce-109">后缀 `A` 指示要应用的操作是 adjointable。</span><span class="sxs-lookup"><span data-stu-id="eb0ce-109">The suffix `A` indicates that the operation to be applied is adjointable.</span></span>

## <a name="input"></a><span data-ttu-id="eb0ce-110">输入</span><span class="sxs-lookup"><span data-stu-id="eb0ce-110">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="eb0ce-111">op： t => [单位](xref:microsoft.quantum.lang-ref.unit) 形容词</span><span class="sxs-lookup"><span data-stu-id="eb0ce-111">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="eb0ce-112">要有条件地应用的操作。</span><span class="sxs-lookup"><span data-stu-id="eb0ce-112">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="eb0ce-113">bit： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="eb0ce-113">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="eb0ce-114">用于控制是否应用 op 的布尔值。</span><span class="sxs-lookup"><span data-stu-id="eb0ce-114">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="eb0ce-115">目标： t</span><span class="sxs-lookup"><span data-stu-id="eb0ce-115">target : 'T</span></span>

<span data-ttu-id="eb0ce-116">将操作应用到的输入。</span><span class="sxs-lookup"><span data-stu-id="eb0ce-116">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="eb0ce-117">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="eb0ce-117">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="eb0ce-118">类型参数</span><span class="sxs-lookup"><span data-stu-id="eb0ce-118">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="eb0ce-119">找</span><span class="sxs-lookup"><span data-stu-id="eb0ce-119">'T</span></span>

<span data-ttu-id="eb0ce-120">要有条件地应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="eb0ce-120">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="eb0ce-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eb0ce-121">See Also</span></span>

- [<span data-ttu-id="eb0ce-122">Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="eb0ce-122">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="eb0ce-123">Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="eb0ce-123">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="eb0ce-124">Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="eb0ce-124">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)