---
uid: Microsoft.Quantum.Arrays.Subarray
title: 子数组函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Subarray
qsharp.summary: Takes an array and a list of locations and produces a new array formed from the elements of the original array that match the given locations.
ms.openlocfilehash: be7b6ee1a396d67ebc311d8d97f4bd751a32d171
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696451"
---
# <a name="subarray-function"></a><span data-ttu-id="7e783-102">子数组函数</span><span class="sxs-lookup"><span data-stu-id="7e783-102">Subarray function</span></span>

<span data-ttu-id="7e783-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="7e783-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="7e783-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7e783-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7e783-105">采用一个数组和一个位置列表，并生成一个新数组，该数组由与给定位置匹配的原始数组的元素构成。</span><span class="sxs-lookup"><span data-stu-id="7e783-105">Takes an array and a list of locations and produces a new array formed from the elements of the original array that match the given locations.</span></span>

```qsharp
function Subarray<'T> (indices : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="7e783-106">输入</span><span class="sxs-lookup"><span data-stu-id="7e783-106">Input</span></span>

### <a name="indices--int"></a><span data-ttu-id="7e783-107">索引： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="7e783-107">indices : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="7e783-108">用于定义子数组的整数的列表。</span><span class="sxs-lookup"><span data-stu-id="7e783-108">A list of integers that is used to define the subarray.</span></span>


### <a name="array--t"></a><span data-ttu-id="7e783-109">array： t []</span><span class="sxs-lookup"><span data-stu-id="7e783-109">array : 'T[]</span></span>

<span data-ttu-id="7e783-110">上的元素的数组 `'T` 。</span><span class="sxs-lookup"><span data-stu-id="7e783-110">An array of elements over `'T`.</span></span>



## <a name="output--t"></a><span data-ttu-id="7e783-111">输出： t []</span><span class="sxs-lookup"><span data-stu-id="7e783-111">Output : 'T[]</span></span>

<span data-ttu-id="7e783-112">`out`元素的数组，这些元素的索引对应于子数组，因此为 `out[idx] == array[indices[idx]]` 。</span><span class="sxs-lookup"><span data-stu-id="7e783-112">An array `out` of elements whose indices correspond to the subarray, such that `out[idx] == array[indices[idx]]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="7e783-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="7e783-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7e783-114">找</span><span class="sxs-lookup"><span data-stu-id="7e783-114">'T</span></span>

<span data-ttu-id="7e783-115">元素的类型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="7e783-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="7e783-116">注解</span><span class="sxs-lookup"><span data-stu-id="7e783-116">Remarks</span></span>

<span data-ttu-id="7e783-117">函数是为泛型类型定义的，即，只要有一个数组 `'T[]` 和一个定义子数组的位置列表 `Int[]` 。</span><span class="sxs-lookup"><span data-stu-id="7e783-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a list of locations `Int[]` defining the subarray.</span></span>
<span data-ttu-id="7e783-118">子数组的构造是基于生成给定数组的新深层副本的，而不是维护引用。</span><span class="sxs-lookup"><span data-stu-id="7e783-118">The construction of the subarray is a based on generating a new, deep copy of the given array as opposed to maintaining references.</span></span>

<span data-ttu-id="7e783-119">如果为 `Length(indices) < Length(array)` ，则此函数将返回的子集 `array` 。</span><span class="sxs-lookup"><span data-stu-id="7e783-119">If `Length(indices) < Length(array)`, this function will return a subset of `array`.</span></span> <span data-ttu-id="7e783-120">另一方面，如果 `indices` 包含重复的元素，则 `array` 同样会重复执行的相应元素。</span><span class="sxs-lookup"><span data-stu-id="7e783-120">On the other hand, if `indices` contains repeated elements, the corresponding elements of `array` will likewise be repeated.</span></span>
<span data-ttu-id="7e783-121">如果 `indices` 和的 `array` 长度相同，则此函数将提供 `array` 。</span><span class="sxs-lookup"><span data-stu-id="7e783-121">If `indices` and `array` are the same length, this function provides permutations of `array`.</span></span>