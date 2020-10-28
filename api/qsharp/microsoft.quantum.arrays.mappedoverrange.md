---
uid: Microsoft.Quantum.Arrays.MappedOverRange
title: MappedOverRange 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedOverRange
qsharp.summary: Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.
ms.openlocfilehash: e527a3ca1fd7571836f4f79bb453581f53d1db2b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696484"
---
# <a name="mappedoverrange-function"></a><span data-ttu-id="87f5c-102">MappedOverRange 函数</span><span class="sxs-lookup"><span data-stu-id="87f5c-102">MappedOverRange function</span></span>

<span data-ttu-id="87f5c-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="87f5c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="87f5c-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="87f5c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="87f5c-105">给定一个范围和一个采用整数作为输入的函数时，将返回一个新数组，该数组由函数下的范围值的图像组成。</span><span class="sxs-lookup"><span data-stu-id="87f5c-105">Given a range and a function that takes an integer as input, returns a new array that consists of the images of the range values under the function.</span></span>

```qsharp
function MappedOverRange<'T> (mapper : (Int -> 'T), range : Range) : 'T[]
```


## <a name="input"></a><span data-ttu-id="87f5c-106">输入</span><span class="sxs-lookup"><span data-stu-id="87f5c-106">Input</span></span>

### <a name="mapper--int---t"></a><span data-ttu-id="87f5c-107">映射器： [Int](xref:microsoft.quantum.lang-ref.int) -></span><span class="sxs-lookup"><span data-stu-id="87f5c-107">mapper : [Int](xref:microsoft.quantum.lang-ref.int) -> 'T</span></span>

<span data-ttu-id="87f5c-108">用于 `Int` `'T` 映射范围值的的函数。</span><span class="sxs-lookup"><span data-stu-id="87f5c-108">A function from `Int` to `'T` that is used to map range values.</span></span>


### <a name="range--range"></a><span data-ttu-id="87f5c-109">范围： [范围](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="87f5c-109">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="87f5c-110">整数的范围。</span><span class="sxs-lookup"><span data-stu-id="87f5c-110">A range of integers.</span></span>



## <a name="output--t"></a><span data-ttu-id="87f5c-111">输出： t []</span><span class="sxs-lookup"><span data-stu-id="87f5c-111">Output : 'T[]</span></span>

<span data-ttu-id="87f5c-112">`'T[]`由函数映射的元素的数组 `mapper` 。</span><span class="sxs-lookup"><span data-stu-id="87f5c-112">An array `'T[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="87f5c-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="87f5c-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="87f5c-114">找</span><span class="sxs-lookup"><span data-stu-id="87f5c-114">'T</span></span>

<span data-ttu-id="87f5c-115">函数的结果类型 `mapper` 。</span><span class="sxs-lookup"><span data-stu-id="87f5c-115">The result type of the `mapper` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="87f5c-116">注解</span><span class="sxs-lookup"><span data-stu-id="87f5c-116">Remarks</span></span>

<span data-ttu-id="87f5c-117">函数是为泛型类型定义的，也就是说，只要有一个函数， `mapper: Int -> 'T` 我们就可以映射范围的值并生成类型为的数组 `'T[]` 。</span><span class="sxs-lookup"><span data-stu-id="87f5c-117">The function is defined for generic types, i.e., whenever we have a function `mapper: Int -> 'T` we can map the values of the range and produce an array of type `'T[]`.</span></span>

## <a name="see-also"></a><span data-ttu-id="87f5c-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="87f5c-118">See Also</span></span>

- [<span data-ttu-id="87f5c-119">已映射的</span><span class="sxs-lookup"><span data-stu-id="87f5c-119">Microsoft.Quantum.Arrays.Mapped</span></span>](xref:Microsoft.Quantum.Arrays.Mapped)