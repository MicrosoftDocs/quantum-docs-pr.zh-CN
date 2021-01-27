---
uid: Microsoft.Quantum.Canon.ApplyToMost
title: ApplyToMost 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMost
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: a3918233e101f3d8956601dcc7d85edcf6196ac7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850592"
---
# <a name="applytomost-operation"></a><span data-ttu-id="b47db-102">ApplyToMost 操作</span><span class="sxs-lookup"><span data-stu-id="b47db-102">ApplyToMost operation</span></span>

<span data-ttu-id="b47db-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="b47db-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="b47db-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b47db-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b47db-105">将操作应用到数组中除最后一个元素之外的所有元素。</span><span class="sxs-lookup"><span data-stu-id="b47db-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMost<'T> (op : ('T[] => Unit), targets : 'T[]) : Unit
```


## <a name="description"></a><span data-ttu-id="b47db-106">说明</span><span class="sxs-lookup"><span data-stu-id="b47db-106">Description</span></span>

<span data-ttu-id="b47db-107">给定一个操作 `op` 和一个目标数组 `targets` ，适用于 `op(Most(targets))` 。</span><span class="sxs-lookup"><span data-stu-id="b47db-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="b47db-108">输入</span><span class="sxs-lookup"><span data-stu-id="b47db-108">Input</span></span>

### <a name="op--t--unit"></a><span data-ttu-id="b47db-109">op： t [] => [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b47db-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="b47db-110">要应用的操作。</span><span class="sxs-lookup"><span data-stu-id="b47db-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="b47db-111">目标： t []</span><span class="sxs-lookup"><span data-stu-id="b47db-111">targets : 'T[]</span></span>

<span data-ttu-id="b47db-112">目标的数组，其中除最后一个外的所有将应用于 `op` 。</span><span class="sxs-lookup"><span data-stu-id="b47db-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="b47db-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="b47db-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="b47db-114">类型参数</span><span class="sxs-lookup"><span data-stu-id="b47db-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b47db-115">找</span><span class="sxs-lookup"><span data-stu-id="b47db-115">'T</span></span>

<span data-ttu-id="b47db-116">要应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="b47db-116">The input type of the operation to be applied.</span></span>

## <a name="example"></a><span data-ttu-id="b47db-117">示例</span><span class="sxs-lookup"><span data-stu-id="b47db-117">Example</span></span>

<span data-ttu-id="b47db-118">以下 Q # 代码段是等效的：</span><span class="sxs-lookup"><span data-stu-id="b47db-118">The following Q# snippets are equivalent:</span></span>

```qsharp
ApplyToMost(ApplyCNOTChain, register);
ApplyCNOTChain(Most(register));
```

## <a name="see-also"></a><span data-ttu-id="b47db-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b47db-119">See Also</span></span>

- [<span data-ttu-id="b47db-120">Canon. ApplyToMostA</span><span class="sxs-lookup"><span data-stu-id="b47db-120">Microsoft.Quantum.Canon.ApplyToMostA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [<span data-ttu-id="b47db-121">Canon. ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="b47db-121">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)
- [<span data-ttu-id="b47db-122">Canon. ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="b47db-122">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)