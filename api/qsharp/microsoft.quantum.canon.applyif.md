---
uid: Microsoft.Quantum.Canon.ApplyIf
title: ApplyIf 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyIf
qsharp.summary: Applies an operation conditioned on a classical bit.
ms.openlocfilehash: c8f6860a7a3b8af86b0edb048baccbf057dd245a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696351"
---
# <a name="applyif-operation"></a><span data-ttu-id="7b406-102">ApplyIf 操作</span><span class="sxs-lookup"><span data-stu-id="7b406-102">ApplyIf operation</span></span>

<span data-ttu-id="7b406-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7b406-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7b406-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7b406-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7b406-105">应用可在传统上使用的操作。</span><span class="sxs-lookup"><span data-stu-id="7b406-105">Applies an operation conditioned on a classical bit.</span></span>

```qsharp
operation ApplyIf<'T> (op : ('T => Unit), bit : Bool, target : 'T) : Unit
```


## <a name="description"></a><span data-ttu-id="7b406-106">说明</span><span class="sxs-lookup"><span data-stu-id="7b406-106">Description</span></span>

<span data-ttu-id="7b406-107">给定一个操作 `op` 和一个位值 `bit` 后， `op` 如果为，则应用于 `target` `bit` `true` 。</span><span class="sxs-lookup"><span data-stu-id="7b406-107">Given an operation `op` and a bit value `bit`, applies `op` to the `target` if `bit` is `true`.</span></span> <span data-ttu-id="7b406-108">如果 `false` 为，则不会发生任何事情 `target` 。</span><span class="sxs-lookup"><span data-stu-id="7b406-108">If `false`, nothing happens to the `target`.</span></span>

## <a name="input"></a><span data-ttu-id="7b406-109">输入</span><span class="sxs-lookup"><span data-stu-id="7b406-109">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="7b406-110">op： t => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7b406-110">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="7b406-111">要有条件地应用的操作。</span><span class="sxs-lookup"><span data-stu-id="7b406-111">An operation to be conditionally applied.</span></span>


### <a name="bit--bool"></a><span data-ttu-id="7b406-112">bit： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="7b406-112">bit : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="7b406-113">用于控制是否应用 op 的布尔值。</span><span class="sxs-lookup"><span data-stu-id="7b406-113">a boolean that controls whether op is applied or not.</span></span>


### <a name="target--t"></a><span data-ttu-id="7b406-114">目标： t</span><span class="sxs-lookup"><span data-stu-id="7b406-114">target : 'T</span></span>

<span data-ttu-id="7b406-115">将操作应用到的输入。</span><span class="sxs-lookup"><span data-stu-id="7b406-115">The input to which the operation is applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="7b406-116">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="7b406-116">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="7b406-117">类型参数</span><span class="sxs-lookup"><span data-stu-id="7b406-117">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7b406-118">找</span><span class="sxs-lookup"><span data-stu-id="7b406-118">'T</span></span>

<span data-ttu-id="7b406-119">要有条件地应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="7b406-119">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="7b406-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7b406-120">See Also</span></span>

- [<span data-ttu-id="7b406-121">Canon. ApplyIfC</span><span class="sxs-lookup"><span data-stu-id="7b406-121">Microsoft.Quantum.Canon.ApplyIfC</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfC)
- [<span data-ttu-id="7b406-122">Canon. ApplyIfA</span><span class="sxs-lookup"><span data-stu-id="7b406-122">Microsoft.Quantum.Canon.ApplyIfA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfA)
- [<span data-ttu-id="7b406-123">Canon. ApplyIfCA</span><span class="sxs-lookup"><span data-stu-id="7b406-123">Microsoft.Quantum.Canon.ApplyIfCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyIfCA)