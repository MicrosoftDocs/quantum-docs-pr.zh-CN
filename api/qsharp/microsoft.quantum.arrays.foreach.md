---
uid: Microsoft.Quantum.Arrays.ForEach
title: ForEach 操作
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ForEach
qsharp.summary: Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.
ms.openlocfilehash: b362d28e77c8dea2b3daeed4a4d605e1dd42e487
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221141"
---
# <a name="foreach-operation"></a><span data-ttu-id="d1eda-102">ForEach 操作</span><span class="sxs-lookup"><span data-stu-id="d1eda-102">ForEach operation</span></span>

<span data-ttu-id="d1eda-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d1eda-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d1eda-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d1eda-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d1eda-105">给定为数组元素定义的数组和操作，返回一个新数组，该数组由该操作下的原始数组的图像组成。</span><span class="sxs-lookup"><span data-stu-id="d1eda-105">Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.</span></span>

```qsharp
operation ForEach<'T, 'U> (action : ('T => 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="d1eda-106">输入</span><span class="sxs-lookup"><span data-stu-id="d1eda-106">Input</span></span>

### <a name="action--t--u"></a><span data-ttu-id="d1eda-107">操作：不 => ' U</span><span class="sxs-lookup"><span data-stu-id="d1eda-107">action : 'T => 'U</span></span> 

<span data-ttu-id="d1eda-108">从 `'T` 到的操作将 `'U` 应用于每个元素。</span><span class="sxs-lookup"><span data-stu-id="d1eda-108">An operation from `'T` to `'U` that is applied to each element.</span></span>


### <a name="array--t"></a><span data-ttu-id="d1eda-109">array： t []</span><span class="sxs-lookup"><span data-stu-id="d1eda-109">array : 'T[]</span></span>

<span data-ttu-id="d1eda-110">上的元素的数组 `'T` 。</span><span class="sxs-lookup"><span data-stu-id="d1eda-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="d1eda-111">输出： U []</span><span class="sxs-lookup"><span data-stu-id="d1eda-111">Output : 'U[]</span></span>

<span data-ttu-id="d1eda-112">`'U[]`由操作映射的元素的数组 `action` 。</span><span class="sxs-lookup"><span data-stu-id="d1eda-112">An array `'U[]` of elements that are mapped by the `action` operation.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d1eda-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="d1eda-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d1eda-114">找</span><span class="sxs-lookup"><span data-stu-id="d1eda-114">'T</span></span>

<span data-ttu-id="d1eda-115">元素的类型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="d1eda-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="d1eda-116">' U</span><span class="sxs-lookup"><span data-stu-id="d1eda-116">'U</span></span>

<span data-ttu-id="d1eda-117">操作的结果类型 `action` 。</span><span class="sxs-lookup"><span data-stu-id="d1eda-117">The result type of the `action` operation.</span></span>

## <a name="remarks"></a><span data-ttu-id="d1eda-118">备注</span><span class="sxs-lookup"><span data-stu-id="d1eda-118">Remarks</span></span>

<span data-ttu-id="d1eda-119">操作是为泛型类型定义的，也就是说，只要有一个数组 `'T[]` 和一个操作， `action : 'T -> 'U` 我们就可以映射数组的元素，并生成一个类型为的新数组 `'U[]` 。</span><span class="sxs-lookup"><span data-stu-id="d1eda-119">The operation is defined for generic types, i.e., whenever we have an array `'T[]` and an operation `action : 'T -> 'U` we can map the elements of the array and produce a new array of type `'U[]`.</span></span>