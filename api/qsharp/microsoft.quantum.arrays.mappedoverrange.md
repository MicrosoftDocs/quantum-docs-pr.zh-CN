---
uid: Microsoft.Quantum.Arrays.MappedOverRange
title: MappedOverRange 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedOverRange
qsharp.summary: Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.
ms.openlocfilehash: 7093043e2a290e6132774b8fe154d3627a254f27
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845649"
---
# <a name="mappedoverrange-function"></a><span data-ttu-id="0be31-102">MappedOverRange 函数</span><span class="sxs-lookup"><span data-stu-id="0be31-102">MappedOverRange function</span></span>

<span data-ttu-id="0be31-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="0be31-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="0be31-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0be31-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0be31-105">给定一个范围和一个采用整数作为输入的函数时，将返回一个新数组，该数组由函数下的范围值的图像组成。</span><span class="sxs-lookup"><span data-stu-id="0be31-105">Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.</span></span>

```qsharp
function MappedOverRange<'T> (mapper : (Int -> 'T), range : Range) : 'T[]
```


## <a name="input"></a><span data-ttu-id="0be31-106">输入</span><span class="sxs-lookup"><span data-stu-id="0be31-106">Input</span></span>

### <a name="mapper--int---t"></a><span data-ttu-id="0be31-107">映射器： [Int](xref:microsoft.quantum.lang-ref.int) -></span><span class="sxs-lookup"><span data-stu-id="0be31-107">mapper : [Int](xref:microsoft.quantum.lang-ref.int) -> 'T</span></span>

<span data-ttu-id="0be31-108">用于 `Int` `'T` 映射范围值的的函数。</span><span class="sxs-lookup"><span data-stu-id="0be31-108">A function from `Int` to `'T` that is used to map range values.</span></span>


### <a name="range--range"></a><span data-ttu-id="0be31-109">范围： [范围](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="0be31-109">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="0be31-110">整数的范围。</span><span class="sxs-lookup"><span data-stu-id="0be31-110">A range of integers.</span></span>



## <a name="output--t"></a><span data-ttu-id="0be31-111">输出： t []</span><span class="sxs-lookup"><span data-stu-id="0be31-111">Output : 'T[]</span></span>

<span data-ttu-id="0be31-112">`'T[]`由函数映射的元素的数组 `mapper` 。</span><span class="sxs-lookup"><span data-stu-id="0be31-112">An array `'T[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="0be31-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="0be31-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0be31-114">找</span><span class="sxs-lookup"><span data-stu-id="0be31-114">'T</span></span>

<span data-ttu-id="0be31-115">函数的结果类型 `mapper` 。</span><span class="sxs-lookup"><span data-stu-id="0be31-115">The result type of the `mapper` function.</span></span>

## <a name="example"></a><span data-ttu-id="0be31-116">示例</span><span class="sxs-lookup"><span data-stu-id="0be31-116">Example</span></span>

<span data-ttu-id="0be31-117">此示例将1添加到偶数范围中：</span><span class="sxs-lookup"><span data-stu-id="0be31-117">This example adds 1 to a range of even numbers:</span></span>

```qsharp
let numbers = MappedOverRange(PlusI(1, _), 0..2..10);
// numbers = [1, 3, 5, 7, 9, 11]
```

## <a name="remarks"></a><span data-ttu-id="0be31-118">备注</span><span class="sxs-lookup"><span data-stu-id="0be31-118">Remarks</span></span>

<span data-ttu-id="0be31-119">函数是为泛型类型定义的，也就是说，只要有一个函数， `mapper: Int -> 'T` 我们就可以映射范围的值并生成类型为的数组 `'T[]` 。</span><span class="sxs-lookup"><span data-stu-id="0be31-119">The function is defined for generic types, i.e., whenever we have a function `mapper: Int -> 'T` we can map the values of the range and produce an array of type `'T[]`.</span></span>

## <a name="see-also"></a><span data-ttu-id="0be31-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0be31-120">See Also</span></span>

- [<span data-ttu-id="0be31-121">已映射的</span><span class="sxs-lookup"><span data-stu-id="0be31-121">Microsoft.Quantum.Arrays.Mapped</span></span>](xref:Microsoft.Quantum.Arrays.Mapped)