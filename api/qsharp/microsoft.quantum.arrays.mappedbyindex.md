---
uid: Microsoft.Quantum.Arrays.MappedByIndex
title: MappedByIndex 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MappedByIndex
qsharp.summary: Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 584cabcb7b6059ae5d311f13f5f75bd1f87bdba5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845665"
---
# <a name="mappedbyindex-function"></a><span data-ttu-id="c2a85-102">MappedByIndex 函数</span><span class="sxs-lookup"><span data-stu-id="c2a85-102">MappedByIndex function</span></span>

<span data-ttu-id="c2a85-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c2a85-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c2a85-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c2a85-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c2a85-105">给定数组和为数组的索引元素定义的函数后，将返回一个新数组，该数组由函数下的原始数组的图像组成。</span><span class="sxs-lookup"><span data-stu-id="c2a85-105">Given an array and a function that is defined for the indexed elements of the array, returns a new array that consists of the images of the original array under the function.</span></span>

```qsharp
function MappedByIndex<'T, 'U> (mapper : ((Int, 'T) -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="c2a85-106">输入</span><span class="sxs-lookup"><span data-stu-id="c2a85-106">Input</span></span>

### <a name="mapper--intt---u"></a><span data-ttu-id="c2a85-107">映射器： ([Int](xref:microsoft.quantum.lang-ref.int)，不) -> "U</span><span class="sxs-lookup"><span data-stu-id="c2a85-107">mapper : ([Int](xref:microsoft.quantum.lang-ref.int),'T) -> 'U</span></span>

<span data-ttu-id="c2a85-108">用于 `(Int, 'T)` `'U` 映射元素及其索引的的函数。</span><span class="sxs-lookup"><span data-stu-id="c2a85-108">A function from `(Int, 'T)` to `'U` that is used to map elements and their indices.</span></span>


### <a name="array--t"></a><span data-ttu-id="c2a85-109">array： t []</span><span class="sxs-lookup"><span data-stu-id="c2a85-109">array : 'T[]</span></span>

<span data-ttu-id="c2a85-110">上的元素的数组 `'T` 。</span><span class="sxs-lookup"><span data-stu-id="c2a85-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="c2a85-111">输出： U []</span><span class="sxs-lookup"><span data-stu-id="c2a85-111">Output : 'U[]</span></span>

<span data-ttu-id="c2a85-112">`'U[]`由函数映射的元素的数组 `mapper` 。</span><span class="sxs-lookup"><span data-stu-id="c2a85-112">An array `'U[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c2a85-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="c2a85-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c2a85-114">找</span><span class="sxs-lookup"><span data-stu-id="c2a85-114">'T</span></span>

<span data-ttu-id="c2a85-115">元素的类型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="c2a85-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="c2a85-116">' U</span><span class="sxs-lookup"><span data-stu-id="c2a85-116">'U</span></span>

<span data-ttu-id="c2a85-117">函数的结果类型 `mapper` 。</span><span class="sxs-lookup"><span data-stu-id="c2a85-117">The result type of the `mapper` function.</span></span>

## <a name="example"></a><span data-ttu-id="c2a85-118">示例</span><span class="sxs-lookup"><span data-stu-id="c2a85-118">Example</span></span>

<span data-ttu-id="c2a85-119">以下两行是等效的：</span><span class="sxs-lookup"><span data-stu-id="c2a85-119">The following two lines are equivalent:</span></span>

```qsharp
let arr = MapIndex(f, [x0, x1, x2]);
```

<span data-ttu-id="c2a85-120">和</span><span class="sxs-lookup"><span data-stu-id="c2a85-120">and</span></span>

```qsharp
let arr = [f(0, x0), f(1, x1), f(2, x2)];
```

## <a name="see-also"></a><span data-ttu-id="c2a85-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c2a85-121">See Also</span></span>

- [<span data-ttu-id="c2a85-122">已映射的</span><span class="sxs-lookup"><span data-stu-id="c2a85-122">Microsoft.Quantum.Arrays.Mapped</span></span>](xref:Microsoft.Quantum.Arrays.Mapped)