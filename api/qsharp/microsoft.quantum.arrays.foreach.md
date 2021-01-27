---
uid: Microsoft.Quantum.Arrays.ForEach
title: ForEach 操作
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ForEach
qsharp.summary: Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.
ms.openlocfilehash: 90dd6f94408d37d2b32d82e772a482b0e69c523f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848584"
---
# <a name="foreach-operation"></a><span data-ttu-id="a381f-102">ForEach 操作</span><span class="sxs-lookup"><span data-stu-id="a381f-102">ForEach operation</span></span>

<span data-ttu-id="a381f-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a381f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a381f-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="a381f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="a381f-105">给定为数组元素定义的数组和操作，返回一个新数组，该数组由该操作下的原始数组的图像组成。</span><span class="sxs-lookup"><span data-stu-id="a381f-105">Given an array and an operation that is defined for the elements of the array, returns a new array that consists of the images of the original array under the operation.</span></span>

```qsharp
operation ForEach<'T, 'U> (action : ('T => 'U), array : 'T[]) : 'U[]
```


## <a name="input"></a><span data-ttu-id="a381f-106">输入</span><span class="sxs-lookup"><span data-stu-id="a381f-106">Input</span></span>

### <a name="action--t--u"></a><span data-ttu-id="a381f-107">操作：不 => ' U</span><span class="sxs-lookup"><span data-stu-id="a381f-107">action : 'T => 'U</span></span> 

<span data-ttu-id="a381f-108">从 `'T` 到的操作将 `'U` 应用于每个元素。</span><span class="sxs-lookup"><span data-stu-id="a381f-108">An operation from `'T` to `'U` that is applied to each element.</span></span>


### <a name="array--t"></a><span data-ttu-id="a381f-109">array： t []</span><span class="sxs-lookup"><span data-stu-id="a381f-109">array : 'T[]</span></span>

<span data-ttu-id="a381f-110">上的元素的数组 `'T` 。</span><span class="sxs-lookup"><span data-stu-id="a381f-110">An array of elements over `'T`.</span></span>



## <a name="output--u"></a><span data-ttu-id="a381f-111">输出： U []</span><span class="sxs-lookup"><span data-stu-id="a381f-111">Output : 'U[]</span></span>

<span data-ttu-id="a381f-112">`'U[]`由操作映射的元素的数组 `action` 。</span><span class="sxs-lookup"><span data-stu-id="a381f-112">An array `'U[]` of elements that are mapped by the `action` operation.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a381f-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="a381f-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="a381f-114">找</span><span class="sxs-lookup"><span data-stu-id="a381f-114">'T</span></span>

<span data-ttu-id="a381f-115">元素的类型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="a381f-115">The type of `array` elements.</span></span>
### <a name="u"></a><span data-ttu-id="a381f-116">' U</span><span class="sxs-lookup"><span data-stu-id="a381f-116">'U</span></span>

<span data-ttu-id="a381f-117">操作的结果类型 `action` 。</span><span class="sxs-lookup"><span data-stu-id="a381f-117">The result type of the `action` operation.</span></span>

## <a name="remarks"></a><span data-ttu-id="a381f-118">备注</span><span class="sxs-lookup"><span data-stu-id="a381f-118">Remarks</span></span>

<span data-ttu-id="a381f-119">操作是为泛型类型定义的，也就是说，只要有一个数组 `'T[]` 和一个操作， `action : 'T -> 'U` 我们就可以映射数组的元素，并生成一个类型为的新数组 `'U[]` 。</span><span class="sxs-lookup"><span data-stu-id="a381f-119">The operation is defined for generic types, i.e., whenever we have an array `'T[]` and an operation `action : 'T -> 'U` we can map the elements of the array and produce a new array of type `'U[]`.</span></span>