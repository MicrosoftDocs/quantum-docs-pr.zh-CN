---
uid: Microsoft.Quantum.Arrays.Filtered
title: 筛选函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Filtered
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: 4c786c69b0896b517f108611e32501867838aeb1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696522"
---
# <a name="filtered-function"></a><span data-ttu-id="0b497-102">筛选函数</span><span class="sxs-lookup"><span data-stu-id="0b497-102">Filtered function</span></span>

<span data-ttu-id="0b497-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="0b497-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="0b497-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0b497-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0b497-105">给定为数组元素定义的数组和谓词后，将返回一个数组，其中包含满足谓词的元素。</span><span class="sxs-lookup"><span data-stu-id="0b497-105">Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.</span></span>

```qsharp
function Filtered<'T> (predicate : ('T -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="0b497-106">输入</span><span class="sxs-lookup"><span data-stu-id="0b497-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="0b497-107">谓词：不 >[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="0b497-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="0b497-108">从 `'T` 到用于筛选元素的布尔值的函数。</span><span class="sxs-lookup"><span data-stu-id="0b497-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="0b497-109">array： t []</span><span class="sxs-lookup"><span data-stu-id="0b497-109">array : 'T[]</span></span>

<span data-ttu-id="0b497-110">上的元素的数组 `'T` 。</span><span class="sxs-lookup"><span data-stu-id="0b497-110">An array of elements over `'T`.</span></span>



## <a name="output--t"></a><span data-ttu-id="0b497-111">输出： t []</span><span class="sxs-lookup"><span data-stu-id="0b497-111">Output : 'T[]</span></span>

<span data-ttu-id="0b497-112">`'T[]`满足谓词的元素的数组。</span><span class="sxs-lookup"><span data-stu-id="0b497-112">An array `'T[]` of elements that satisfy the predicate.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="0b497-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="0b497-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0b497-114">找</span><span class="sxs-lookup"><span data-stu-id="0b497-114">'T</span></span>

<span data-ttu-id="0b497-115">元素的类型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="0b497-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="0b497-116">注解</span><span class="sxs-lookup"><span data-stu-id="0b497-116">Remarks</span></span>

<span data-ttu-id="0b497-117">函数是为泛型类型定义的，也就是说，只要有一个数组 `'T[]` 和一个谓词，就 `'T -> Bool` 可以筛选元素。</span><span class="sxs-lookup"><span data-stu-id="0b497-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a predicate `'T -> Bool` we can filter elements.</span></span>