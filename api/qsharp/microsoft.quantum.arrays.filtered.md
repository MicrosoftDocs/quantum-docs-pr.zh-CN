---
uid: Microsoft.Quantum.Arrays.Filtered
title: 筛选函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Filtered
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.
ms.openlocfilehash: 83336b7001ce1d8ab1f5340b194abdcf93588c31
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847161"
---
# <a name="filtered-function"></a><span data-ttu-id="fd74e-102">筛选函数</span><span class="sxs-lookup"><span data-stu-id="fd74e-102">Filtered function</span></span>

<span data-ttu-id="fd74e-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="fd74e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="fd74e-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fd74e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fd74e-105">给定为数组元素定义的数组和谓词后，将返回一个数组，其中包含满足谓词的元素。</span><span class="sxs-lookup"><span data-stu-id="fd74e-105">Given an array and a predicate that is defined for the elements of the array, returns an array that consists of those elements that satisfy the predicate.</span></span>

```qsharp
function Filtered<'T> (predicate : ('T -> Bool), array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="fd74e-106">输入</span><span class="sxs-lookup"><span data-stu-id="fd74e-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="fd74e-107">谓词：不 >[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="fd74e-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="fd74e-108">从 `'T` 到用于筛选元素的布尔值的函数。</span><span class="sxs-lookup"><span data-stu-id="fd74e-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="fd74e-109">array： t []</span><span class="sxs-lookup"><span data-stu-id="fd74e-109">array : 'T[]</span></span>

<span data-ttu-id="fd74e-110">上的元素的数组 `'T` 。</span><span class="sxs-lookup"><span data-stu-id="fd74e-110">An array of elements over `'T`.</span></span>



## <a name="output--t"></a><span data-ttu-id="fd74e-111">输出： t []</span><span class="sxs-lookup"><span data-stu-id="fd74e-111">Output : 'T[]</span></span>

<span data-ttu-id="fd74e-112">`'T[]`满足谓词的元素的数组。</span><span class="sxs-lookup"><span data-stu-id="fd74e-112">An array `'T[]` of elements that satisfy the predicate.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="fd74e-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="fd74e-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fd74e-114">找</span><span class="sxs-lookup"><span data-stu-id="fd74e-114">'T</span></span>

<span data-ttu-id="fd74e-115">元素的类型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="fd74e-115">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="fd74e-116">示例</span><span class="sxs-lookup"><span data-stu-id="fd74e-116">Example</span></span>

<span data-ttu-id="fd74e-117">下面的代码演示 "筛选的" 函数。</span><span class="sxs-lookup"><span data-stu-id="fd74e-117">The following code demonstrates the "Filtered" function.</span></span>
<span data-ttu-id="fd74e-118">使用函数定义谓词 @"microsoft.quantum.logical.greaterthani" ：</span><span class="sxs-lookup"><span data-stu-id="fd74e-118">A predicate is defined using the @"microsoft.quantum.logical.greaterthani" function:</span></span>

```qsharp
open Microsoft.Quantum.Arrays;
open Microsoft.Quantum.Logical;

function FilteredDemo() : Unit {
   let predicate = GreaterThanI(_, 5);
   let filteredArray = Filtered(predicate, [2, 5, 9, 1, 8]);
   Message($"{filteredArray}");
}
```

<span data-ttu-id="fd74e-119">此示例应有的结果是一个大于5的数字数组。</span><span class="sxs-lookup"><span data-stu-id="fd74e-119">The outcome one should expect from this example will be an array of numbers greater than 5.</span></span>

## <a name="remarks"></a><span data-ttu-id="fd74e-120">备注</span><span class="sxs-lookup"><span data-stu-id="fd74e-120">Remarks</span></span>

<span data-ttu-id="fd74e-121">函数是为泛型类型定义的，也就是说，只要有一个数组 `'T[]` 和一个谓词，就 `'T -> Bool` 可以筛选元素。</span><span class="sxs-lookup"><span data-stu-id="fd74e-121">The function is defined for generic types, i.e., whenever we have an array `'T[]` and a predicate `'T -> Bool` we can filter elements.</span></span>