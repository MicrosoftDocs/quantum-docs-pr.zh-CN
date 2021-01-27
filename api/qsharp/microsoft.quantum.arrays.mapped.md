---
uid: Microsoft.Quantum.Arrays.Mapped
title: 映射函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Mapped
qsharp.summary: Given an array and a function that is defined for the elements of the array, returns a new array that consists of the images of the original array under the function.
ms.openlocfilehash: 00ea0803faf6e8edfa748af63dd6c7e217b1de41
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845678"
---
# <a name="mapped-function"></a><span data-ttu-id="aa04c-102">映射函数</span><span class="sxs-lookup"><span data-stu-id="aa04c-102">Mapped function</span></span>

<span data-ttu-id="aa04c-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="aa04c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="aa04c-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="aa04c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="aa04c-105">给定数组和为数组元素定义的函数后，将返回一个新数组，该数组由函数下的原始数组的图像组成。</span><span class="sxs-lookup"><span data-stu-id="aa04c-105">Given an array and a function that is defined for the elements of the array, returns a new array that consists of the images of the original array under the function.</span></span>

```qsharp
function Mapped<'T, 'U> (mapper : ('T -> 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="aa04c-106">输入</span><span class="sxs-lookup"><span data-stu-id="aa04c-106">Input</span></span>

### <a name="mapper--t---u"></a><span data-ttu-id="aa04c-107">映射器：不 > "U</span><span class="sxs-lookup"><span data-stu-id="aa04c-107">mapper : 'T -> 'U</span></span>

<span data-ttu-id="aa04c-108">用于映射元素的的函数 `'T` `'U` 。</span><span class="sxs-lookup"><span data-stu-id="aa04c-108">A function from `'T` to `'U` that is used to map elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="aa04c-109">array： t []</span><span class="sxs-lookup"><span data-stu-id="aa04c-109">array : 'T[]</span></span>

<span data-ttu-id="aa04c-110">上的元素的数组 `'T` 。</span><span class="sxs-lookup"><span data-stu-id="aa04c-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="aa04c-111">输出： U []</span><span class="sxs-lookup"><span data-stu-id="aa04c-111">Output : 'U[]</span></span>

<span data-ttu-id="aa04c-112">`'U[]`由函数映射的元素的数组 `mapper` 。</span><span class="sxs-lookup"><span data-stu-id="aa04c-112">An array `'U[]` of elements that are mapped by the `mapper` function.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="aa04c-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="aa04c-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="aa04c-114">找</span><span class="sxs-lookup"><span data-stu-id="aa04c-114">'T</span></span>

<span data-ttu-id="aa04c-115">元素的类型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="aa04c-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="aa04c-116">' U</span><span class="sxs-lookup"><span data-stu-id="aa04c-116">'U</span></span>

<span data-ttu-id="aa04c-117">函数的结果类型 `mapper` 。</span><span class="sxs-lookup"><span data-stu-id="aa04c-117">The result type of the `mapper` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="aa04c-118">备注</span><span class="sxs-lookup"><span data-stu-id="aa04c-118">Remarks</span></span>

<span data-ttu-id="aa04c-119">函数是为泛型类型定义的，也就是说，只要有一个数组 `'T[]` 和一个函数， `mapper: 'T -> 'U` 我们就可以映射数组的元素，并生成一个类型为的新数组 `'U[]` 。</span><span class="sxs-lookup"><span data-stu-id="aa04c-119">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `mapper: 'T -> 'U` we can map the elements of the array and produce a new array of type `'U[]`.</span></span>