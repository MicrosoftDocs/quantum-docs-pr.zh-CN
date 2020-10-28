---
uid: Microsoft.Quantum.Arrays.EqualA
title: EqualA 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EqualA
qsharp.summary: Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.
ms.openlocfilehash: 24fd76aaeb66081d6d8f1eaa3056117f54b5a5e7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696525"
---
# <a name="equala-function"></a><span data-ttu-id="22d3d-102">EqualA 函数</span><span class="sxs-lookup"><span data-stu-id="22d3d-102">EqualA function</span></span>

<span data-ttu-id="22d3d-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="22d3d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="22d3d-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="22d3d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="22d3d-105">给定两个相同类型的数组和为数组元素对定义的谓词，检查数组是否相等。</span><span class="sxs-lookup"><span data-stu-id="22d3d-105">Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.</span></span>

```qsharp
function EqualA<'T> (equal : (('T, 'T) -> Bool), array1 : 'T[], array2 : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="22d3d-106">输入</span><span class="sxs-lookup"><span data-stu-id="22d3d-106">Input</span></span>

### <a name="equal--tt---bool"></a><span data-ttu-id="22d3d-107">等于： ( 不，不) ->[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="22d3d-107">equal : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="22d3d-108">元组中的一个函数， `('T, 'T)` `Bool` 用于检查两个数组元素是否相等。</span><span class="sxs-lookup"><span data-stu-id="22d3d-108">A function from tuple `('T, 'T)` to `Bool` that is used to check whether two elements of arrays are equal.</span></span>


### <a name="array1--t"></a><span data-ttu-id="22d3d-109">array1： t []</span><span class="sxs-lookup"><span data-stu-id="22d3d-109">array1 : 'T[]</span></span>

<span data-ttu-id="22d3d-110">要比较的第一个数组。</span><span class="sxs-lookup"><span data-stu-id="22d3d-110">The first array to be compared.</span></span>


### <a name="array2--t"></a><span data-ttu-id="22d3d-111">array2： t []</span><span class="sxs-lookup"><span data-stu-id="22d3d-111">array2 : 'T[]</span></span>

<span data-ttu-id="22d3d-112">要比较的第二个数组。</span><span class="sxs-lookup"><span data-stu-id="22d3d-112">The second array to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="22d3d-113">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="22d3d-113">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="22d3d-114">`true`当且仅当和相等时，值为 `array1` `array2` 。</span><span class="sxs-lookup"><span data-stu-id="22d3d-114">The value `true` if and only if `array1` and `array2` are equal.</span></span>
<span data-ttu-id="22d3d-115">也就是说，如果两个数组具有相同的长度，并且所有元素都与定义的相等 `equal` 。</span><span class="sxs-lookup"><span data-stu-id="22d3d-115">That is, if both arrays have the same length, and all elements are equal as defined by `equal`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="22d3d-116">类型参数</span><span class="sxs-lookup"><span data-stu-id="22d3d-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="22d3d-117">找</span><span class="sxs-lookup"><span data-stu-id="22d3d-117">'T</span></span>

<span data-ttu-id="22d3d-118">每个数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="22d3d-118">The type of each array's elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="22d3d-119">注解</span><span class="sxs-lookup"><span data-stu-id="22d3d-119">Remarks</span></span>

<span data-ttu-id="22d3d-120">此函数是为泛型类型定义的;也就是说，每当有两个数组 `'T[]` 和一个函数时 `equal: ('T, 'T) -> Bool` ，此函数将返回一个 `Bool` 值，该值指示数组是否相等。</span><span class="sxs-lookup"><span data-stu-id="22d3d-120">This function is defined for generic types; i.e., whenever we have two arrays `'T[]` and a function `equal: ('T, 'T) -> Bool`, this function returns a `Bool` value that indicates whether the arrays are equal.</span></span>
<span data-ttu-id="22d3d-121">对于两个要视为相等的数组，它们必须具有相等的长度，并且数组中同一位置的元素必须相等。</span><span class="sxs-lookup"><span data-stu-id="22d3d-121">For two arrays to be considered equal, they have to have equal length and the elements in the same positions in the arrays have to be equal.</span></span>