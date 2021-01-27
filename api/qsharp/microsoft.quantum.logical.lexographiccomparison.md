---
uid: Microsoft.Quantum.Logical.LexographicComparison
title: LexographicComparison 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LexographicComparison
qsharp.summary: Given a comparison function, returns a new function that lexographically compares two arrays.
ms.openlocfilehash: de8179ab6e835d08e7f41287f31a876b7ecc91c5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814389"
---
# <a name="lexographiccomparison-function"></a><span data-ttu-id="5cc08-102">LexographicComparison 函数</span><span class="sxs-lookup"><span data-stu-id="5cc08-102">LexographicComparison function</span></span>

<span data-ttu-id="5cc08-103">命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="5cc08-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="5cc08-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5cc08-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5cc08-105">给定比较函数，将返回 lexographically 比较两个数组的新函数。</span><span class="sxs-lookup"><span data-stu-id="5cc08-105">Given a comparison function, returns a new function that lexographically compares two arrays.</span></span>

```qsharp
function LexographicComparison<'T> (elementComparison : (('T, 'T) -> Bool)) : (('T[], 'T[]) -> Bool)
```


## <a name="input"></a><span data-ttu-id="5cc08-106">输入</span><span class="sxs-lookup"><span data-stu-id="5cc08-106">Input</span></span>

### <a name="elementcomparison--tt---bool"></a><span data-ttu-id="5cc08-107">elementComparison： ( t，不) ->[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="5cc08-107">elementComparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5cc08-108">一个函数，它比较两个元素 `x` ，并 `y` 在 `x` 小于或等于时返回 `y` 。</span><span class="sxs-lookup"><span data-stu-id="5cc08-108">A function that compares two elements `x` and `y` and returns if `x` is less than or equal to `y`.</span></span>



## <a name="output--tt---bool"></a><span data-ttu-id="5cc08-109">输出： ( t []，t [] ) ->[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="5cc08-109">Output : ('T[],'T[]) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5cc08-110">一个函数，它比较两个数组 `xs` ， `ys` 并 `xs` `ys` 在 lexographical 排序之前或等于时返回。</span><span class="sxs-lookup"><span data-stu-id="5cc08-110">A function that compares two arrays `xs` and `ys` and returns if `xs` occurs before or equal to `ys` in lexographical ordering.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="5cc08-111">类型参数</span><span class="sxs-lookup"><span data-stu-id="5cc08-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5cc08-112">找</span><span class="sxs-lookup"><span data-stu-id="5cc08-112">'T</span></span>

<span data-ttu-id="5cc08-113">要比较的数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="5cc08-113">The type of the elements of the arrays being compared.</span></span>

## <a name="remarks"></a><span data-ttu-id="5cc08-114">备注</span><span class="sxs-lookup"><span data-stu-id="5cc08-114">Remarks</span></span>

<span data-ttu-id="5cc08-115">两个数组之间的 lexographic 比较 `xs` ， `ys` 由以下过程定义。</span><span class="sxs-lookup"><span data-stu-id="5cc08-115">The lexographic comparison between two arrays `xs` and `ys` is defined by the following procedure.</span></span> <span data-ttu-id="5cc08-116">假设 and 都为 true，则这两个元素 `x` 和 `y` 都是等效的 `elementComparison(x, y)` `elementComparison(y, x)` 。</span><span class="sxs-lookup"><span data-stu-id="5cc08-116">We say that two elements `x` and `y` are equivalent if `elementComparison(x, y)` and `elementComparison(y, x)` are both true.</span></span>

- <span data-ttu-id="5cc08-117">这两个数组都是逐个元素进行比较，直到第一对不等效的元素。</span><span class="sxs-lookup"><span data-stu-id="5cc08-117">Both arrays are compared element-by-element until the first pair of elements that are not equivalent.</span></span> <span data-ttu-id="5cc08-118">如果数组包含首先按照 lexographical 排序发生的元素，则该数组将 `elementComparison` 首先出现。</span><span class="sxs-lookup"><span data-stu-id="5cc08-118">The array containing the element that occurs first according to `elementComparison` is said to occur first in lexographical ordering.</span></span>
- <span data-ttu-id="5cc08-119">如果未找到任何 inequivalent 的元素，并且一个数组的长度超过另一个，则认为较短的数组将首先出现。</span><span class="sxs-lookup"><span data-stu-id="5cc08-119">If no inequivalent elements are found, and one array is longer than the other, the shorter array is said to occur first.</span></span>

## <a name="see-also"></a><span data-ttu-id="5cc08-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5cc08-120">See Also</span></span>

- [<span data-ttu-id="5cc08-121">已排序的</span><span class="sxs-lookup"><span data-stu-id="5cc08-121">Microsoft.Quantum.Arrays.Sorted</span></span>](xref:Microsoft.Quantum.Arrays.Sorted)