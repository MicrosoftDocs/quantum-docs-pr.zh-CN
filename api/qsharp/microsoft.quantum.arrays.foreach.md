---
uid: Microsoft.Quantum.Arrays.ForEach
title: ForEach 操作
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ForEach
qsharp.summary: Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.
ms.openlocfilehash: ab6ac6eb913095f31ba166ac27f034f2e2875acf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696511"
---
# <a name="foreach-operation"></a><span data-ttu-id="fa8b3-102">ForEach 操作</span><span class="sxs-lookup"><span data-stu-id="fa8b3-102">ForEach operation</span></span>

<span data-ttu-id="fa8b3-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="fa8b3-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="fa8b3-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fa8b3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fa8b3-105">给定为数组元素定义的数组和操作，返回一个新数组，该数组由该操作下的原始数组的图像组成。</span><span class="sxs-lookup"><span data-stu-id="fa8b3-105">Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.</span></span>

```qsharp
operation ForEach<'T, 'U> (action : ('T => 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="fa8b3-106">输入</span><span class="sxs-lookup"><span data-stu-id="fa8b3-106">Input</span></span>

### <a name="action--t--u"></a><span data-ttu-id="fa8b3-107">操作：不 => ' U</span><span class="sxs-lookup"><span data-stu-id="fa8b3-107">action : 'T => 'U</span></span> 

<span data-ttu-id="fa8b3-108">从 `'T` 到的操作将 `'U` 应用于每个元素。</span><span class="sxs-lookup"><span data-stu-id="fa8b3-108">An operation from `'T` to `'U` that is applied to each element.</span></span>


### <a name="array--t"></a><span data-ttu-id="fa8b3-109">array： t []</span><span class="sxs-lookup"><span data-stu-id="fa8b3-109">array : 'T[]</span></span>

<span data-ttu-id="fa8b3-110">上的元素的数组 `'T` 。</span><span class="sxs-lookup"><span data-stu-id="fa8b3-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="fa8b3-111">输出： U []</span><span class="sxs-lookup"><span data-stu-id="fa8b3-111">Output : 'U[]</span></span>

<span data-ttu-id="fa8b3-112">`'U[]`由操作映射的元素的数组 `action` 。</span><span class="sxs-lookup"><span data-stu-id="fa8b3-112">An array `'U[]` of elements that are mapped by the `action` operation.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="fa8b3-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="fa8b3-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fa8b3-114">找</span><span class="sxs-lookup"><span data-stu-id="fa8b3-114">'T</span></span>

<span data-ttu-id="fa8b3-115">元素的类型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="fa8b3-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="fa8b3-116">' U</span><span class="sxs-lookup"><span data-stu-id="fa8b3-116">'U</span></span>

<span data-ttu-id="fa8b3-117">操作的结果类型 `action` 。</span><span class="sxs-lookup"><span data-stu-id="fa8b3-117">The result type of the `action` operation.</span></span>

## <a name="remarks"></a><span data-ttu-id="fa8b3-118">注解</span><span class="sxs-lookup"><span data-stu-id="fa8b3-118">Remarks</span></span>

<span data-ttu-id="fa8b3-119">操作是为泛型类型定义的，也就是说，只要有一个数组 `'T[]` 和一个操作， `action : 'T -> 'U` 我们就可以映射数组的元素，并生成一个类型为的新数组 `'U[]` 。</span><span class="sxs-lookup"><span data-stu-id="fa8b3-119">The operation is defined for generic types, i.e., whenever we have an array `'T[]` and an operation `action : 'T -> 'U` we can map the elements of the array and produce a new array of type `'U[]`.</span></span>