---
uid: Microsoft.Quantum.Canon.ApplyToTailC
title: ApplyToTailC 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailC
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 5a68cae3fd122416cfd064e0078e03f5c00ab492
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96217282"
---
# <a name="applytotailc-operation"></a><span data-ttu-id="29d85-102">ApplyToTailC 操作</span><span class="sxs-lookup"><span data-stu-id="29d85-102">ApplyToTailC operation</span></span>

<span data-ttu-id="29d85-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="29d85-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="29d85-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="29d85-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="29d85-105">将操作应用到数组的最后一个元素。</span><span class="sxs-lookup"><span data-stu-id="29d85-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTailC<'T> (op : ('T => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="29d85-106">描述</span><span class="sxs-lookup"><span data-stu-id="29d85-106">Description</span></span>

<span data-ttu-id="29d85-107">给定一个操作 `op` 和一个目标数组 `targets` ，适用于 `op(Tail(targets))` 。</span><span class="sxs-lookup"><span data-stu-id="29d85-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="29d85-108">输入</span><span class="sxs-lookup"><span data-stu-id="29d85-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="29d85-109">op： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为 Ctl</span><span class="sxs-lookup"><span data-stu-id="29d85-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="29d85-110">要应用的操作。</span><span class="sxs-lookup"><span data-stu-id="29d85-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="29d85-111">目标： t []</span><span class="sxs-lookup"><span data-stu-id="29d85-111">targets : 'T[]</span></span>

<span data-ttu-id="29d85-112">要应用最后一个目标的数组 `op` 。</span><span class="sxs-lookup"><span data-stu-id="29d85-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="29d85-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="29d85-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="29d85-114">类型参数</span><span class="sxs-lookup"><span data-stu-id="29d85-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="29d85-115">找</span><span class="sxs-lookup"><span data-stu-id="29d85-115">'T</span></span>

<span data-ttu-id="29d85-116">要应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="29d85-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="29d85-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="29d85-117">See Also</span></span>

- [<span data-ttu-id="29d85-118">Canon. ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="29d85-118">Microsoft.Quantum.Canon.ApplyToTail</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [<span data-ttu-id="29d85-119">Canon. ApplyToTailA</span><span class="sxs-lookup"><span data-stu-id="29d85-119">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="29d85-120">Canon. ApplyToTailCA</span><span class="sxs-lookup"><span data-stu-id="29d85-120">Microsoft.Quantum.Canon.ApplyToTailCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailCA)