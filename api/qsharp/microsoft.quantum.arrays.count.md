---
uid: Microsoft.Quantum.Arrays.Count
title: Count 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Count
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: 48b75cc6d6584f899223a0803f31fd174836f303
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221549"
---
# <a name="count-function"></a><span data-ttu-id="ecad5-102">Count 函数</span><span class="sxs-lookup"><span data-stu-id="ecad5-102">Count function</span></span>

<span data-ttu-id="ecad5-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ecad5-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ecad5-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ecad5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ecad5-105">给定为数组元素定义的数组和谓词后，将返回一个数组，该数组由满足该谓词的元素组成。</span><span class="sxs-lookup"><span data-stu-id="ecad5-105">Given an array and a predicate that is defined for the elements of the array, returns the number of elements an array that consists of those elements that satisfy the predicate.</span></span>

```qsharp
function Count<'T> (predicate : ('T -> Bool), array : 'T[]) : Int
```


## <a name="input"></a><span data-ttu-id="ecad5-106">输入</span><span class="sxs-lookup"><span data-stu-id="ecad5-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="ecad5-107">谓词：不 >[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="ecad5-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ecad5-108">从 `'T` 到用于筛选元素的布尔值的函数。</span><span class="sxs-lookup"><span data-stu-id="ecad5-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="ecad5-109">array： t []</span><span class="sxs-lookup"><span data-stu-id="ecad5-109">array : 'T[]</span></span>

<span data-ttu-id="ecad5-110">上的元素的数组 `'T` 。</span><span class="sxs-lookup"><span data-stu-id="ecad5-110">An array of elements over `'T`.</span></span>



## <a name="output--int"></a><span data-ttu-id="ecad5-111">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ecad5-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ecad5-112">中满足谓词的元素的数目 `array` 。</span><span class="sxs-lookup"><span data-stu-id="ecad5-112">The number of elements in `array` that satisfy the predicate.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ecad5-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="ecad5-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ecad5-114">找</span><span class="sxs-lookup"><span data-stu-id="ecad5-114">'T</span></span>

<span data-ttu-id="ecad5-115">元素的类型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="ecad5-115">The type of `array` elements.</span></span>

## <a name="remarks"></a><span data-ttu-id="ecad5-116">备注</span><span class="sxs-lookup"><span data-stu-id="ecad5-116">Remarks</span></span>

<span data-ttu-id="ecad5-117">函数是为泛型类型定义的，也就是说，只要有一个数组 `'T[]` 和一个谓词，就 `'T -> Bool` 可以筛选元素。</span><span class="sxs-lookup"><span data-stu-id="ecad5-117">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a predicate `'T -> Bool` we can filter elements.</span></span>