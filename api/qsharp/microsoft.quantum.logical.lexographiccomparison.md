---
uid: Microsoft.Quantum.Logical.LexographicComparison
title: LexographicComparison 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LexographicComparison
qsharp.summary: Given a comparison function, returns a new function that lexographically compares two arrays.
ms.openlocfilehash: f0b68974a0ea26907b58971e4fa4b1f06f5714d2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695159"
---
# <a name="lexographiccomparison-function"></a><span data-ttu-id="e45a6-102">LexographicComparison 函数</span><span class="sxs-lookup"><span data-stu-id="e45a6-102">LexographicComparison function</span></span>

<span data-ttu-id="e45a6-103">命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="e45a6-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="e45a6-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e45a6-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e45a6-105">给定比较函数，将返回 lexographically 比较两个数组的新函数。</span><span class="sxs-lookup"><span data-stu-id="e45a6-105">Given a comparison function, returns a new function that lexographically compares two arrays.</span></span>

```qsharp
function LexographicComparison<'T> (elementComparison : (('T, 'T) -> Bool)) : (('T[], 'T[]) -> Bool)
```


## <a name="input"></a><span data-ttu-id="e45a6-106">输入</span><span class="sxs-lookup"><span data-stu-id="e45a6-106">Input</span></span>

### <a name="elementcomparison--tt---bool"></a><span data-ttu-id="e45a6-107">elementComparison： ( t，不) ->[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="e45a6-107">elementComparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e45a6-108">一个函数，它比较两个元素 `x` ，并 `y` 在 `x` 小于或等于时返回 `y` 。</span><span class="sxs-lookup"><span data-stu-id="e45a6-108">A function that compares two elements `x` and `y` and returns if `x` is less than or equal to `y`.</span></span>



## <a name="output--tt---bool"></a><span data-ttu-id="e45a6-109">输出： ( t []，t [] ) ->[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="e45a6-109">Output : ('T[],'T[]) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e45a6-110">一个函数，它比较两个数组 `xs` ， `ys` 并 `xs` `ys` 在 lexographical 排序之前或等于时返回。</span><span class="sxs-lookup"><span data-stu-id="e45a6-110">A function that compares two arrays `xs` and `ys` and returns if `xs` occurs before or equal to `ys` in lexographical ordering.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e45a6-111">类型参数</span><span class="sxs-lookup"><span data-stu-id="e45a6-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e45a6-112">找</span><span class="sxs-lookup"><span data-stu-id="e45a6-112">'T</span></span>

<span data-ttu-id="e45a6-113">要比较的数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="e45a6-113">The type of the elements of the arrays being compared.</span></span>

## <a name="remarks"></a><span data-ttu-id="e45a6-114">注解</span><span class="sxs-lookup"><span data-stu-id="e45a6-114">Remarks</span></span>

<span data-ttu-id="e45a6-115">两个数组之间的 lexographic 比较 `xs` ， `ys` 由以下过程定义。</span><span class="sxs-lookup"><span data-stu-id="e45a6-115">The lexographic comparison between two arrays `xs` and `ys` is defined by the following procedure.</span></span> <span data-ttu-id="e45a6-116">假设 and 都为 true，则这两个元素 `x` 和 `y` 都是等效的 `elementComparison(x, y)` `elementComparison(y, x)` 。</span><span class="sxs-lookup"><span data-stu-id="e45a6-116">We say that two elements `x` and `y` are equivalent if `elementComparison(x, y)` and `elementComparison(y, x)` are both true.</span></span>

- <span data-ttu-id="e45a6-117">这两个数组都是逐个元素进行比较，直到第一对不等效的元素。</span><span class="sxs-lookup"><span data-stu-id="e45a6-117">Both arrays are compared element-by-element until the first pair of elements that are not equivalent.</span></span> <span data-ttu-id="e45a6-118">如果数组包含首先按照 lexographical 排序发生的元素，则该数组将 `elementComparison` 首先出现。</span><span class="sxs-lookup"><span data-stu-id="e45a6-118">The array containing the element that occurs first according to `elementComparison` is said to occur first in lexographical ordering.</span></span>
- <span data-ttu-id="e45a6-119">如果未找到任何 inequivalent 的元素，并且一个数组的长度超过另一个，则认为较短的数组将首先出现。</span><span class="sxs-lookup"><span data-stu-id="e45a6-119">If no inequivalent elements are found, and one array is longer than the other, the shorter array is said to occur first.</span></span>

## <a name="see-also"></a><span data-ttu-id="e45a6-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e45a6-120">See Also</span></span>

- [<span data-ttu-id="e45a6-121">已排序的</span><span class="sxs-lookup"><span data-stu-id="e45a6-121">Microsoft.Quantum.Arrays.Sorted</span></span>](xref:Microsoft.Quantum.Arrays.Sorted)