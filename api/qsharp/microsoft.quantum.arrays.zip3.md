---
uid: Microsoft.Quantum.Arrays.Zip3
title: List.zip3 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip3
qsharp.summary: >-
  > [!WARNING]

  > Zip3 has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.


  Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.
ms.openlocfilehash: b41b0789cdf90db534ee7a50ff25eb3a931ec683
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845351"
---
# <a name="zip3-function"></a><span data-ttu-id="5413b-102">List.zip3 函数</span><span class="sxs-lookup"><span data-stu-id="5413b-102">Zip3 function</span></span>

<span data-ttu-id="5413b-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="5413b-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="5413b-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5413b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="5413b-105">List.zip3 已被弃用。</span><span class="sxs-lookup"><span data-stu-id="5413b-105">Zip3 has been deprecated.</span></span> <span data-ttu-id="5413b-106">请改用 <xref:Microsoft.Quantum.Arrays.Zipped3>。</span><span class="sxs-lookup"><span data-stu-id="5413b-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.</span></span>

<span data-ttu-id="5413b-107">给定三个数组，返回一个新数组，其中包含3个元组，以便每个第三个元组包含每个原始数组中的一个元素。</span><span class="sxs-lookup"><span data-stu-id="5413b-107">Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.</span></span>

```qsharp
function Zip3<'T1, 'T2, 'T3> (first : 'T1[], second : 'T2[], third : 'T3[]) : ('T1, 'T2, 'T3)[]
```


## <a name="input"></a><span data-ttu-id="5413b-108">输入</span><span class="sxs-lookup"><span data-stu-id="5413b-108">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="5413b-109">第一个：不是 1 []</span><span class="sxs-lookup"><span data-stu-id="5413b-109">first : 'T1[]</span></span>

<span data-ttu-id="5413b-110">一个数组，其中包含每个元组的第一个元素的值。</span><span class="sxs-lookup"><span data-stu-id="5413b-110">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="5413b-111">second：不 2 []</span><span class="sxs-lookup"><span data-stu-id="5413b-111">second : 'T2[]</span></span>

<span data-ttu-id="5413b-112">一个数组，其中包含每个元组的第二个元素的值。</span><span class="sxs-lookup"><span data-stu-id="5413b-112">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="5413b-113">第三个：不 3 []</span><span class="sxs-lookup"><span data-stu-id="5413b-113">third : 'T3[]</span></span>

<span data-ttu-id="5413b-114">一个数组，其中包含每个元组的第三个元素的值。</span><span class="sxs-lookup"><span data-stu-id="5413b-114">An array containing values for the third element of each tuple.</span></span>



## <a name="output--t1t2t3"></a><span data-ttu-id="5413b-115">输出： ( 不是1，不是2，不是 3) []</span><span class="sxs-lookup"><span data-stu-id="5413b-115">Output : ('T1,'T2,'T3)[]</span></span>

<span data-ttu-id="5413b-116">一个数组，其中包含每个的窗体的3元组 `(first[idx], second[idx], third[idx])` `idx` 。</span><span class="sxs-lookup"><span data-stu-id="5413b-116">An array containing 3-tuples of the form `(first[idx], second[idx], third[idx])` for each `idx`.</span></span> <span data-ttu-id="5413b-117">如果三个数组的长度不相等，则输出将与输入的较短内容相同。</span><span class="sxs-lookup"><span data-stu-id="5413b-117">If the three arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="5413b-118">类型参数</span><span class="sxs-lookup"><span data-stu-id="5413b-118">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="5413b-119">T 1</span><span class="sxs-lookup"><span data-stu-id="5413b-119">'T1</span></span>

<span data-ttu-id="5413b-120">第一个数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="5413b-120">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="5413b-121">不是2</span><span class="sxs-lookup"><span data-stu-id="5413b-121">'T2</span></span>

<span data-ttu-id="5413b-122">第二个数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="5413b-122">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="5413b-123">不3</span><span class="sxs-lookup"><span data-stu-id="5413b-123">'T3</span></span>

<span data-ttu-id="5413b-124">第三个数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="5413b-124">The type of the third array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="5413b-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5413b-125">See Also</span></span>

- [<span data-ttu-id="5413b-126">Microsoft.Quantum.Arrays.Zip</span><span class="sxs-lookup"><span data-stu-id="5413b-126">Microsoft.Quantum.Arrays.Zip</span></span>](xref:Microsoft.Quantum.Arrays.Zip)
- [<span data-ttu-id="5413b-127">Microsoft.Quantum.Arrays.Zip4</span><span class="sxs-lookup"><span data-stu-id="5413b-127">Microsoft.Quantum.Arrays.Zip4</span></span>](xref:Microsoft.Quantum.Arrays.Zip4)