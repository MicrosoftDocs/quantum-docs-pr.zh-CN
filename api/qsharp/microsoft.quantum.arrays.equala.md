---
uid: Microsoft.Quantum.Arrays.EqualA
title: EqualA 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: EqualA
qsharp.summary: Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.
ms.openlocfilehash: fe22e208f67d2c289b0b2d99f19ff26fc5abc3d8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848686"
---
# <a name="equala-function"></a><span data-ttu-id="23997-102">EqualA 函数</span><span class="sxs-lookup"><span data-stu-id="23997-102">EqualA function</span></span>

<span data-ttu-id="23997-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="23997-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="23997-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="23997-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="23997-105">给定两个相同类型的数组和为数组元素对定义的谓词，检查数组是否相等。</span><span class="sxs-lookup"><span data-stu-id="23997-105">Given two arrays of the same type and a predicate that is defined for pairs of elements of the arrays, checks whether the arrays are equal.</span></span>

```qsharp
function EqualA<'T> (equal : (('T, 'T) -> Bool), array1 : 'T[], array2 : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="23997-106">输入</span><span class="sxs-lookup"><span data-stu-id="23997-106">Input</span></span>

### <a name="equal--tt---bool"></a><span data-ttu-id="23997-107">等于： ( 不，不) ->[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="23997-107">equal : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="23997-108">元组中的一个函数， `('T, 'T)` `Bool` 用于检查两个数组元素是否相等。</span><span class="sxs-lookup"><span data-stu-id="23997-108">A function from tuple `('T, 'T)` to `Bool` that is used to check whether two elements of arrays are equal.</span></span>


### <a name="array1--t"></a><span data-ttu-id="23997-109">array1： t []</span><span class="sxs-lookup"><span data-stu-id="23997-109">array1 : 'T[]</span></span>

<span data-ttu-id="23997-110">要比较的第一个数组。</span><span class="sxs-lookup"><span data-stu-id="23997-110">The first array to be compared.</span></span>


### <a name="array2--t"></a><span data-ttu-id="23997-111">array2： t []</span><span class="sxs-lookup"><span data-stu-id="23997-111">array2 : 'T[]</span></span>

<span data-ttu-id="23997-112">要比较的第二个数组。</span><span class="sxs-lookup"><span data-stu-id="23997-112">The second array to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="23997-113">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="23997-113">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="23997-114">`true`当且仅当和相等时，值为 `array1` `array2` 。</span><span class="sxs-lookup"><span data-stu-id="23997-114">The value `true` if and only if `array1` and `array2` are equal.</span></span>
<span data-ttu-id="23997-115">也就是说，如果两个数组具有相同的长度，并且所有元素都与定义的相等 `equal` 。</span><span class="sxs-lookup"><span data-stu-id="23997-115">That is, if both arrays have the same length, and all elements are equal as defined by `equal`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="23997-116">类型参数</span><span class="sxs-lookup"><span data-stu-id="23997-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="23997-117">找</span><span class="sxs-lookup"><span data-stu-id="23997-117">'T</span></span>

<span data-ttu-id="23997-118">每个数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="23997-118">The type of each array's elements.</span></span>

## <a name="example"></a><span data-ttu-id="23997-119">示例</span><span class="sxs-lookup"><span data-stu-id="23997-119">Example</span></span>

<span data-ttu-id="23997-120">下面的代码检查不同的数组对是否相等：</span><span class="sxs-lookup"><span data-stu-id="23997-120">The following code checks whether different pairs of arrays are equal:</span></span>

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function EqualADemo() : Unit {
    let equalArrays = EqualA(EqualI, [2, 3, 4], [2, 3, 4]);
    let differentLength = EqualA(EqualD, [2.0, 3.0, 4.0], [2.0, 3.0]);
    let differentElements = EqualA(EqualR, [One, Zero], [One, One]);
    Message($"Equal arrays are {equalArrays ? "equal" | "not equal"}");
    Message($"Arrays of different length are {differentLength ? "equal" | "not equal"}");
    Message($"Arrays of the same length with different elements are {differentElements ? "equal" | "not equal"}");
}
```

## <a name="remarks"></a><span data-ttu-id="23997-121">备注</span><span class="sxs-lookup"><span data-stu-id="23997-121">Remarks</span></span>

<span data-ttu-id="23997-122">此函数是为泛型类型定义的;也就是说，每当有两个数组 `'T[]` 和一个函数时 `equal: ('T, 'T) -> Bool` ，此函数将返回一个 `Bool` 值，该值指示数组是否相等。</span><span class="sxs-lookup"><span data-stu-id="23997-122">This function is defined for generic types; i.e., whenever we have two arrays `'T[]` and a function `equal: ('T, 'T) -> Bool`, this function returns a `Bool` value that indicates whether the arrays are equal.</span></span>
<span data-ttu-id="23997-123">对于两个要视为相等的数组，它们必须具有相等的长度，并且数组中同一位置的元素必须相等。</span><span class="sxs-lookup"><span data-stu-id="23997-123">For two arrays to be considered equal, they have to have equal length and the elements in the same positions in the arrays have to be equal.</span></span>