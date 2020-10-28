---
uid: Microsoft.Quantum.Arrays.MappedByIndex
title: MappedByIndex 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedByIndex
qsharp.summary: Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 07ca523248c363f2229551a14e77803dc4f4f82e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696486"
---
# <a name="mappedbyindex-function"></a><span data-ttu-id="c8012-102">MappedByIndex 函数</span><span class="sxs-lookup"><span data-stu-id="c8012-102">MappedByIndex function</span></span>

<span data-ttu-id="c8012-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c8012-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c8012-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c8012-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c8012-105">给定数组和为数组的索引元素定义的函数后，将返回一个新数组，该数组由函数下的原始数组的图像组成。</span><span class="sxs-lookup"><span data-stu-id="c8012-105">Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.</span></span>

```qsharp
function MappedByIndex<'T, 'U> (mapper : ((Int, 'T) -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="c8012-106">输入</span><span class="sxs-lookup"><span data-stu-id="c8012-106">Input</span></span>

### <a name="mapper--intt---u"></a><span data-ttu-id="c8012-107">映射器： ([Int](xref:microsoft.quantum.lang-ref.int)，不) -> "U</span><span class="sxs-lookup"><span data-stu-id="c8012-107">mapper : ([Int](xref:microsoft.quantum.lang-ref.int),'T) -> 'U</span></span>

<span data-ttu-id="c8012-108">用于 `(Int, 'T)` `'U` 映射元素及其索引的的函数。</span><span class="sxs-lookup"><span data-stu-id="c8012-108">A function from `(Int, 'T)` to `'U` that is used to map elements and their indices.</span></span>


### <a name="array--t"></a><span data-ttu-id="c8012-109">array： t []</span><span class="sxs-lookup"><span data-stu-id="c8012-109">array : 'T[]</span></span>

<span data-ttu-id="c8012-110">上的元素的数组 `'T` 。</span><span class="sxs-lookup"><span data-stu-id="c8012-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="c8012-111">输出： U []</span><span class="sxs-lookup"><span data-stu-id="c8012-111">Output : 'U[]</span></span>

<span data-ttu-id="c8012-112">`'U[]`由函数映射的元素的数组 `mapper` 。</span><span class="sxs-lookup"><span data-stu-id="c8012-112">An array `'U[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c8012-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="c8012-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c8012-114">找</span><span class="sxs-lookup"><span data-stu-id="c8012-114">'T</span></span>

<span data-ttu-id="c8012-115">元素的类型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="c8012-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="c8012-116">' U</span><span class="sxs-lookup"><span data-stu-id="c8012-116">'U</span></span>

<span data-ttu-id="c8012-117">函数的结果类型 `mapper` 。</span><span class="sxs-lookup"><span data-stu-id="c8012-117">The result type of the `mapper` function.</span></span>

## <a name="see-also"></a><span data-ttu-id="c8012-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c8012-118">See Also</span></span>

- [<span data-ttu-id="c8012-119">已映射的</span><span class="sxs-lookup"><span data-stu-id="c8012-119">Microsoft.Quantum.Arrays.Mapped</span></span>](xref:Microsoft.Quantum.Arrays.Mapped)