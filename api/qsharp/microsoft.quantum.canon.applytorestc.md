---
uid: Microsoft.Quantum.Canon.ApplyToRestC
title: ApplyToRestC 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToRestC
qsharp.summary: Applies an operation to all but the first element of an array.
ms.openlocfilehash: 1e533a9f0994b70054aeca2f9ddd97f4e200b03f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850492"
---
# <a name="applytorestc-operation"></a><span data-ttu-id="60509-102">ApplyToRestC 操作</span><span class="sxs-lookup"><span data-stu-id="60509-102">ApplyToRestC operation</span></span>

<span data-ttu-id="60509-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="60509-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="60509-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="60509-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="60509-105">将操作应用到数组中除第一个元素之外的所有元素。</span><span class="sxs-lookup"><span data-stu-id="60509-105">Applies an operation to all but the first element of an array.</span></span>

```qsharp
operation ApplyToRestC<'T> (op : ('T[] => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a><span data-ttu-id="60509-106">说明</span><span class="sxs-lookup"><span data-stu-id="60509-106">Description</span></span>

<span data-ttu-id="60509-107">给定一个操作 `op` 和一个目标数组 `targets` ，适用于 `op(Rest(targets))` 。</span><span class="sxs-lookup"><span data-stu-id="60509-107">Given an operation `op` and an array of targets `targets`, applies `op(Rest(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="60509-108">输入</span><span class="sxs-lookup"><span data-stu-id="60509-108">Input</span></span>

### <a name="op--t--unit--is-ctl"></a><span data-ttu-id="60509-109">op： t [] => [单位](xref:microsoft.quantum.lang-ref.unit)  为 Ctl</span><span class="sxs-lookup"><span data-stu-id="60509-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Ctl</span></span>

<span data-ttu-id="60509-110">要应用的操作。</span><span class="sxs-lookup"><span data-stu-id="60509-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="60509-111">目标： t []</span><span class="sxs-lookup"><span data-stu-id="60509-111">targets : 'T[]</span></span>

<span data-ttu-id="60509-112">目标数组，其中除第一个以外的所有将应用于 `op` 。</span><span class="sxs-lookup"><span data-stu-id="60509-112">An array of targets, of which all but the first will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="60509-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="60509-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="60509-114">类型参数</span><span class="sxs-lookup"><span data-stu-id="60509-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="60509-115">找</span><span class="sxs-lookup"><span data-stu-id="60509-115">'T</span></span>

<span data-ttu-id="60509-116">要应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="60509-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="60509-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="60509-117">See Also</span></span>

- [<span data-ttu-id="60509-118">Canon. ApplyToRest</span><span class="sxs-lookup"><span data-stu-id="60509-118">Microsoft.Quantum.Canon.ApplyToRest</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRest)
- [<span data-ttu-id="60509-119">Canon. ApplyToRestA</span><span class="sxs-lookup"><span data-stu-id="60509-119">Microsoft.Quantum.Canon.ApplyToRestA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestA)
- [<span data-ttu-id="60509-120">Canon. ApplyToRestCA</span><span class="sxs-lookup"><span data-stu-id="60509-120">Microsoft.Quantum.Canon.ApplyToRestCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToRestCA)