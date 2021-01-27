---
uid: Microsoft.Quantum.Canon.ApplyToMostA
title: ApplyToMostA 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostA
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: eb793b3d6bc1f75a14e97420d36d0aea3038e0f5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850572"
---
# <a name="applytomosta-operation"></a><span data-ttu-id="c44e1-102">ApplyToMostA 操作</span><span class="sxs-lookup"><span data-stu-id="c44e1-102">ApplyToMostA operation</span></span>

<span data-ttu-id="c44e1-103">命名空间： [Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="c44e1-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="c44e1-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c44e1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c44e1-105">将操作应用到数组中除最后一个元素之外的所有元素。</span><span class="sxs-lookup"><span data-stu-id="c44e1-105">Applies an operation to all but the last element of an array.</span></span>

```qsharp
operation ApplyToMostA<'T> (op : ('T[] => Unit is Adj), targets : 'T[]) : Unit is Adj
```


## <a name="description"></a><span data-ttu-id="c44e1-106">说明</span><span class="sxs-lookup"><span data-stu-id="c44e1-106">Description</span></span>

<span data-ttu-id="c44e1-107">给定一个操作 `op` 和一个目标数组 `targets` ，适用于 `op(Most(targets))` 。</span><span class="sxs-lookup"><span data-stu-id="c44e1-107">Given an operation `op` and an array of targets `targets`, applies `op(Most(targets))`.</span></span>

## <a name="input"></a><span data-ttu-id="c44e1-108">输入</span><span class="sxs-lookup"><span data-stu-id="c44e1-108">Input</span></span>

### <a name="op--t--unit--is-adj"></a><span data-ttu-id="c44e1-109">op： t [] => [单位](xref:microsoft.quantum.lang-ref.unit)  为形容词</span><span class="sxs-lookup"><span data-stu-id="c44e1-109">op : 'T[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj</span></span>

<span data-ttu-id="c44e1-110">要应用的操作。</span><span class="sxs-lookup"><span data-stu-id="c44e1-110">An operation to be applied.</span></span>


### <a name="targets--t"></a><span data-ttu-id="c44e1-111">目标： t []</span><span class="sxs-lookup"><span data-stu-id="c44e1-111">targets : 'T[]</span></span>

<span data-ttu-id="c44e1-112">目标的数组，其中除最后一个外的所有将应用于 `op` 。</span><span class="sxs-lookup"><span data-stu-id="c44e1-112">An array of targets, of which all but the last will be applied to `op`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c44e1-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c44e1-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c44e1-114">类型参数</span><span class="sxs-lookup"><span data-stu-id="c44e1-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c44e1-115">找</span><span class="sxs-lookup"><span data-stu-id="c44e1-115">'T</span></span>

<span data-ttu-id="c44e1-116">要应用的操作的输入类型。</span><span class="sxs-lookup"><span data-stu-id="c44e1-116">The input type of the operation to be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="c44e1-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c44e1-117">See Also</span></span>

- [<span data-ttu-id="c44e1-118">Canon. ApplyToMost</span><span class="sxs-lookup"><span data-stu-id="c44e1-118">Microsoft.Quantum.Canon.ApplyToMost</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [<span data-ttu-id="c44e1-119">Canon. ApplyToMostC</span><span class="sxs-lookup"><span data-stu-id="c44e1-119">Microsoft.Quantum.Canon.ApplyToMostC</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostC)
- [<span data-ttu-id="c44e1-120">Canon. ApplyToMostCA</span><span class="sxs-lookup"><span data-stu-id="c44e1-120">Microsoft.Quantum.Canon.ApplyToMostCA</span></span>](xref:Microsoft.Quantum.Canon.ApplyToMostCA)