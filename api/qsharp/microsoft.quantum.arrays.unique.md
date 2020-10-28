---
uid: Microsoft.Quantum.Arrays.Unique
title: Unique 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unique
qsharp.summary: Returns a new array that has no equal adjacent elements.
ms.openlocfilehash: c5d40bb82f2de640e9c78eef0c27e4766b477826
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696441"
---
# <a name="unique-function"></a><span data-ttu-id="a669c-102">Unique 函数</span><span class="sxs-lookup"><span data-stu-id="a669c-102">Unique function</span></span>

<span data-ttu-id="a669c-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a669c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a669c-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a669c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a669c-105">返回一个没有相等相邻元素的新数组。</span><span class="sxs-lookup"><span data-stu-id="a669c-105">Returns a new array that has no equal adjacent elements.</span></span>

```qsharp
function Unique<'T> (equal : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="a669c-106">说明</span><span class="sxs-lookup"><span data-stu-id="a669c-106">Description</span></span>

<span data-ttu-id="a669c-107">如果给定了某个元素数组和一个用于测试相等性的函数，则此函数将返回一个新数组，其中保留了元素的相对顺序，但所有相等的相邻元素仅筛选为一个元素。</span><span class="sxs-lookup"><span data-stu-id="a669c-107">Given some array of elements and a function to test equality, this function returns a new array in which the relative order of elements is kept, but all adjacent elements which are equal are filtered to just a single element.</span></span>

## <a name="input"></a><span data-ttu-id="a669c-108">输入</span><span class="sxs-lookup"><span data-stu-id="a669c-108">Input</span></span>

### <a name="equal--tt---bool"></a><span data-ttu-id="a669c-109">等于： ( 不，不) ->[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="a669c-109">equal : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="a669c-110">比较两个元素的函数，如果为，则此函数将 `a` 视为等于 `b` `equal(a, b)` `true` 。</span><span class="sxs-lookup"><span data-stu-id="a669c-110">A function that compares two elements such that `a` is considered to be equal to `b` if `equal(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="a669c-111">array： t []</span><span class="sxs-lookup"><span data-stu-id="a669c-111">array : 'T[]</span></span>

<span data-ttu-id="a669c-112">要针对唯一元素进行筛选的数组。</span><span class="sxs-lookup"><span data-stu-id="a669c-112">The array to be filtered for unique elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="a669c-113">输出： t []</span><span class="sxs-lookup"><span data-stu-id="a669c-113">Output : 'T[]</span></span>

<span data-ttu-id="a669c-114">不具有相等相邻元素的数组。</span><span class="sxs-lookup"><span data-stu-id="a669c-114">Array with no equal adjacent elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a669c-115">类型参数</span><span class="sxs-lookup"><span data-stu-id="a669c-115">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a669c-116">找</span><span class="sxs-lookup"><span data-stu-id="a669c-116">'T</span></span>

<span data-ttu-id="a669c-117">的每个元素的类型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="a669c-117">The type of each element of `array`.</span></span>

## <a name="remarks"></a><span data-ttu-id="a669c-118">注解</span><span class="sxs-lookup"><span data-stu-id="a669c-118">Remarks</span></span>

<span data-ttu-id="a669c-119">如果有多个元素相等但并不相邻，则输出数组中将出现多个匹配项。</span><span class="sxs-lookup"><span data-stu-id="a669c-119">If there are multiple elements that are equal but not next to each other, there will be multiple occurrences in the output array.</span></span>  <span data-ttu-id="a669c-120">将此函数与结合使用 `Sorted` ，以获取包含整体唯一元素的数组。</span><span class="sxs-lookup"><span data-stu-id="a669c-120">Use this function together with `Sorted` to get an array with overall unique elements.</span></span>