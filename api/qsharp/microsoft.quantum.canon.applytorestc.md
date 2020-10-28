---
uid: Microsoft.Quantum.Canon.ApplyToRestC
title: ApplyToRestC 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestC
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 55e534b7b7673f300b607a8213418c45c8c7c92c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696186"
---
# <a name="applytorestc-operation"></a><span data-ttu-id="74333-102">ApplyToRestC 操作</span><span class="sxs-lookup"><span data-stu-id="74333-102">ApplyToRestC operation</span></span>

<span data-ttu-id="74333-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="74333-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="74333-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="74333-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="74333-105">将操作应用到数组中除第一个元素之外的所有元素。</span><span class="sxs-lookup"><span data-stu-id="74333-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestC<'T> (op : ('T[] => Unit is Ctl), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="74333-106">说明</span><span class="sxs-lookup"><span data-stu-id="74333-106">Description</span></span>

<span data-ttu-id="74333-107">给定一个操作 `op` 和一个目标数组 `targets` ，适用于 `op(Rest(targets))` 。</span><span class="sxs-lookup"><span data-stu-id="74333-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="74333-108">输入</span><span class="sxs-lookup"><span data-stu-id="74333-108">Input</span></span>

### <a name="op--t--unit-ctl"></a><span data-ttu-id="74333-109">op： t [] => [单元](xref:microsoft.quantum.lang-ref.unit) Ctl</span><span class="sxs-lookup"><span data-stu-id="74333-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Ctl</span></span>

<span data-ttu-id="74333-110">要应用的操作。</span><span class="sxs-lookup"><span data-stu-id="74333-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="74333-111">目标： t []</span><span class="sxs-lookup"><span data-stu-id="74333-111">targets : 'T[]</span></span>

<span data-ttu-id="74333-112">目标数组，其中除第一个以外的所有将应用于 `op` 。</span><span class="sxs-lookup"><span data-stu-id="74333-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="74333-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="74333-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="74333-114">类型参数</span><span class="sxs-lookup"><span data-stu-id="74333-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="74333-115">找</span><span class="sxs-lookup"><span data-stu-id="74333-115">'T</span></span>

<span data-ttu-id="74333-116">要应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="74333-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="74333-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="74333-117">See Also</span></span>

- [<span data-ttu-id="74333-118">Canon. ApplyToRest</span><span class="sxs-lookup"><span data-stu-id="74333-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="74333-119">Canon. ApplyToRestA</span><span class="sxs-lookup"><span data-stu-id="74333-119">Microsoft.Quantum.Canon.ApplyToRestA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [<span data-ttu-id="74333-120">Canon. ApplyToRestCA</span><span class="sxs-lookup"><span data-stu-id="74333-120">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)