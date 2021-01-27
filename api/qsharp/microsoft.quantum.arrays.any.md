---
uid: Microsoft.Quantum.Arrays.Any
title: 任何函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Any
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.
ms.openlocfilehash: a05f9531168bf2b32977665d38cc00f3c8e64879
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846284"
---
# <a name="any-function"></a><span data-ttu-id="d9eb1-102">任何函数</span><span class="sxs-lookup"><span data-stu-id="d9eb1-102">Any function</span></span>

<span data-ttu-id="d9eb1-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d9eb1-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d9eb1-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d9eb1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d9eb1-105">给定为数组元素定义的数组和谓词，检查数组中是否至少有一个元素满足该谓词。</span><span class="sxs-lookup"><span data-stu-id="d9eb1-105">Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.</span></span>

```qsharp
function Any<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="d9eb1-106">输入</span><span class="sxs-lookup"><span data-stu-id="d9eb1-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="d9eb1-107">谓词：不 >[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="d9eb1-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d9eb1-108">用于 `'T` `Bool` 检查元素的的函数。</span><span class="sxs-lookup"><span data-stu-id="d9eb1-108">A function from `'T` to `Bool` that is used to check elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="d9eb1-109">array： t []</span><span class="sxs-lookup"><span data-stu-id="d9eb1-109">array : 'T[]</span></span>

<span data-ttu-id="d9eb1-110">上的元素的数组 `'T` 。</span><span class="sxs-lookup"><span data-stu-id="d9eb1-110">An array of elements over `'T`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="d9eb1-111">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="d9eb1-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d9eb1-112">`Bool`应用于所有元素的谓词或函数的值。</span><span class="sxs-lookup"><span data-stu-id="d9eb1-112">A `Bool` value of the OR function of the predicate applied to all elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d9eb1-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="d9eb1-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="d9eb1-114">找</span><span class="sxs-lookup"><span data-stu-id="d9eb1-114">'T</span></span>

<span data-ttu-id="d9eb1-115">元素的类型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="d9eb1-115">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="d9eb1-116">示例</span><span class="sxs-lookup"><span data-stu-id="d9eb1-116">Example</span></span>

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function IsThreePresent() : Bool {
    let arrayOfInts = [1, 2, 3, 4, 5];
    let is3Present = IsNumberPresentInArray(3, arrayOfInts);
    return is3Present;
}

function IsNumberPresentInArray(n : Int, array : Int[]) : Bool {
    return Any(EqualI(_, n), array);
}
```

## <a name="remarks"></a><span data-ttu-id="d9eb1-117">备注</span><span class="sxs-lookup"><span data-stu-id="d9eb1-117">Remarks</span></span>

<span data-ttu-id="d9eb1-118">函数是为泛型类型定义的，也就是说，只要有一个数组 `'T[]` 和一个函数， `predicate: 'T -> Bool` 我们就可以生成一个 `Bool` 值，该值指示某个元素是否满足 `predicate` 。</span><span class="sxs-lookup"><span data-stu-id="d9eb1-118">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `predicate: 'T -> Bool` we can produce a `Bool` value that indicates if some element satisfies `predicate`.</span></span>