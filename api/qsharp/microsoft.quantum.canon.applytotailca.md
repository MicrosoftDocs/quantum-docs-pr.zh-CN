---
uid: Microsoft.Quantum.Canon.ApplyToTailCA
title: ApplyToTailCA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToTailCA
qsharp.summary: Applies an operation to the last element of an array.
ms.openlocfilehash: 4c702a9d310adae7a4ec404f3cf12893547623b0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98841203"
---
# <a name="applytotailca-operation"></a><span data-ttu-id="ddbd3-102">ApplyToTailCA 操作</span><span class="sxs-lookup"><span data-stu-id="ddbd3-102">ApplyToTailCA operation</span></span>

<span data-ttu-id="ddbd3-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="ddbd3-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="ddbd3-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ddbd3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ddbd3-105">将操作应用到数组的最后一个元素。</span><span class="sxs-lookup"><span data-stu-id="ddbd3-105">Applies an operation to the last element of an array.</span></span>

```qsharp
operation ApplyToTailCA<'T> (op : ('T => Unit is Adj + Ctl), targets : 'T[]) : Unit is Adj + Ctl
```


## <a name="description"></a><span data-ttu-id="ddbd3-106">说明</span><span class="sxs-lookup"><span data-stu-id="ddbd3-106">Description</span></span>

<span data-ttu-id="ddbd3-107">给定一个操作 `op` 和一个目标数组 `targets` ，适用于 `op(Tail(targets))` 。</span><span class="sxs-lookup"><span data-stu-id="ddbd3-107">Given an operation `op` and an array of targets `targets`, applies `op(Tail(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="ddbd3-108">输入</span><span class="sxs-lookup"><span data-stu-id="ddbd3-108">Input</span></span>

### <a name="op--t--unit--is-adj--ctl"></a><span data-ttu-id="ddbd3-109">op： t => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词 + Ctl</span><span class="sxs-lookup"><span data-stu-id="ddbd3-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="ddbd3-110">要应用的操作。</span><span class="sxs-lookup"><span data-stu-id="ddbd3-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="ddbd3-111">目标： t []</span><span class="sxs-lookup"><span data-stu-id="ddbd3-111">targets : 'T[]</span></span>

<span data-ttu-id="ddbd3-112">要应用最后一个目标的数组 `op` 。</span><span class="sxs-lookup"><span data-stu-id="ddbd3-112">An array of targets, of which the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="ddbd3-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="ddbd3-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="ddbd3-114">类型参数</span><span class="sxs-lookup"><span data-stu-id="ddbd3-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ddbd3-115">找</span><span class="sxs-lookup"><span data-stu-id="ddbd3-115">'T</span></span>

<span data-ttu-id="ddbd3-116">要应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="ddbd3-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="ddbd3-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ddbd3-117">See Also</span></span>

- [<span data-ttu-id="ddbd3-118">Canon. ApplyToTail</span><span class="sxs-lookup"><span data-stu-id="ddbd3-118">Microsoft.Quantum.Canon.ApplyToTail</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTail)
- [<span data-ttu-id="ddbd3-119">Canon. ApplyToTailA</span><span class="sxs-lookup"><span data-stu-id="ddbd3-119">Microsoft.Quantum.Canon.ApplyToTailA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailA)
- [<span data-ttu-id="ddbd3-120">Canon. ApplyToTailC</span><span class="sxs-lookup"><span data-stu-id="ddbd3-120">Microsoft.Quantum.Canon.ApplyToTailC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToTailC)