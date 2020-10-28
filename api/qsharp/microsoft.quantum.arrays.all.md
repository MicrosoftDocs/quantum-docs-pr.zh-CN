---
uid: Microsoft.Quantum.Arrays.All
title: All 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: All
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.
ms.openlocfilehash: 345c3fb92babd4ae2e54803b6c3b79b3313ef417
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696557"
---
# <a name="all-function"></a><span data-ttu-id="5419a-102">All 函数</span><span class="sxs-lookup"><span data-stu-id="5419a-102">All function</span></span>

<span data-ttu-id="5419a-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="5419a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="5419a-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="5419a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="5419a-105">给定为数组元素定义的数组和谓词，并检查数组的所有元素是否都满足该谓词。</span><span class="sxs-lookup"><span data-stu-id="5419a-105">Given an array and a predicate that is defined for the elements of the array, and checks if all elements of the array satisfy the predicate.</span></span>

```qsharp
function All<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="5419a-106">输入</span><span class="sxs-lookup"><span data-stu-id="5419a-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="5419a-107">谓词：不 >[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="5419a-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5419a-108">用于 `'T` `Bool` 检查元素的的函数。</span><span class="sxs-lookup"><span data-stu-id="5419a-108">A function from `'T` to `Bool` that is used to check elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="5419a-109">array： t []</span><span class="sxs-lookup"><span data-stu-id="5419a-109">array : 'T[]</span></span>

<span data-ttu-id="5419a-110">上的元素的数组 `'T` 。</span><span class="sxs-lookup"><span data-stu-id="5419a-110">An array of elements over `'T`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="5419a-111">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="5419a-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5419a-112">`Bool`应用于所有元素的谓词的和函数的值。</span><span class="sxs-lookup"><span data-stu-id="5419a-112">A `Bool` value of the AND function of the predicate applied to all elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="5419a-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="5419a-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5419a-114">找</span><span class="sxs-lookup"><span data-stu-id="5419a-114">'T</span></span>

<span data-ttu-id="5419a-115">元素的类型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="5419a-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="5419a-116">注解</span><span class="sxs-lookup"><span data-stu-id="5419a-116">Remarks</span></span>

<span data-ttu-id="5419a-117">函数是为泛型类型定义的，也就是说，只要有一个数组 `'T[]` 和一个函数， `predicate: 'T -> Bool` 我们就可以生成一个 `Bool` 值，该值指示所有元素是否满足 `predicate` 。</span><span class="sxs-lookup"><span data-stu-id="5419a-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a function `predicate: 'T -> Bool` we can produce a `Bool` value that indicates if all elements satisfy `predicate`.</span></span>