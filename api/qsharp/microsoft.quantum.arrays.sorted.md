---
uid: Microsoft.Quantum.Arrays.Sorted
title: 已排序函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Sorted
qsharp.summary: Given an array, returns the elements of that array sorted by a given comparison function.
ms.openlocfilehash: bd8b869e03c7f4687c456a944e07a811ae0d2ce2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220223"
---
# <a name="sorted-function"></a><span data-ttu-id="6bca4-102">已排序函数</span><span class="sxs-lookup"><span data-stu-id="6bca4-102">Sorted function</span></span>

<span data-ttu-id="6bca4-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="6bca4-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="6bca4-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6bca4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6bca4-105">给定一个数组，返回该数组的元素，这些元素按给定的比较函数排序。</span><span class="sxs-lookup"><span data-stu-id="6bca4-105">Given an array, returns the elements of that array sorted by a given comparison function.</span></span>

```qsharp
function Sorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="6bca4-106">输入</span><span class="sxs-lookup"><span data-stu-id="6bca4-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="6bca4-107">比较： ( 不) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="6bca4-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6bca4-108">比较两个元素的函数，如果为，则将 `a` 其视为小于或等于 `b` `comparison(a, b)` `true` 。</span><span class="sxs-lookup"><span data-stu-id="6bca4-108">A function that compares two elements such that `a` is considered to be less than or equal to `b` if `comparison(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="6bca4-109">array： t []</span><span class="sxs-lookup"><span data-stu-id="6bca4-109">array : 'T[]</span></span>

<span data-ttu-id="6bca4-110">要排序的数组。</span><span class="sxs-lookup"><span data-stu-id="6bca4-110">The array to be sorted.</span></span>



## <a name="output--t"></a><span data-ttu-id="6bca4-111">输出： t []</span><span class="sxs-lookup"><span data-stu-id="6bca4-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="6bca4-112">类型参数</span><span class="sxs-lookup"><span data-stu-id="6bca4-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6bca4-113">找</span><span class="sxs-lookup"><span data-stu-id="6bca4-113">'T</span></span>

<span data-ttu-id="6bca4-114">的每个元素的类型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="6bca4-114">The type of each element of `array`.</span></span>

## <a name="remarks"></a><span data-ttu-id="6bca4-115">备注</span><span class="sxs-lookup"><span data-stu-id="6bca4-115">Remarks</span></span>

<span data-ttu-id="6bca4-116">假定函数是 `comparison` 可传递的，因此，如果 `comparison(a, b)` 和，则 `comparison(b, c)` `comparison(a, c)` 假定为。</span><span class="sxs-lookup"><span data-stu-id="6bca4-116">The function `comparison` is assumed to be transitive, such that if `comparison(a, b)` and `comparison(b, c)`, then `comparison(a, c)` is assumed.</span></span> <span data-ttu-id="6bca4-117">如果此属性不存在，则此函数的输出可能不正确。</span><span class="sxs-lookup"><span data-stu-id="6bca4-117">If this property does not hold, then the output of this function may be incorrect.</span></span>

<span data-ttu-id="6bca4-118">由于这是一个函数，即使两个元素在下被视为相等，结果也完全是确定性的 `comparison` ; 即，当 `comparison(a, b)` 和 `comparison(b, a)` 都是时 `true` 。</span><span class="sxs-lookup"><span data-stu-id="6bca4-118">As this is a function, the results are completely determinstic, even when two elements are considered equal under `comparison`; that is, when `comparison(a, b)` and `comparison(b, a)` are both `true`.</span></span>
<span data-ttu-id="6bca4-119">具体而言，此函数执行的排序保证是稳定的，因此，如果中的两个 `a` 元素 `b` 在中按顺序发生 `array` ，并被视为相等 `comparison` ，则在 `a` 输出中也将出现 `b` 在之前。</span><span class="sxs-lookup"><span data-stu-id="6bca4-119">In particular, the sort performed by this function is guaranteed to be stable, so that if two elements `a` and `b` occur in that order within `array` and are considered equal under `comparison`, then `a` will also appear before `b` in the output.</span></span>

<span data-ttu-id="6bca4-120">例如：</span><span class="sxs-lookup"><span data-stu-id="6bca4-120">For example:</span></span>

```Q#
function LastDigitLessThanOrEqual(left : Int, right : Int) : Bool {
    return LessThanOrEqualI(
        left % 10, right % 10
    );
}

function SortedByLastDigit() : Int[] {
    return Sorted(LastDigitLessThanOrEqual, [3, 37, 11, 17]);
}
// returns [11, 3, 37, 17].
```