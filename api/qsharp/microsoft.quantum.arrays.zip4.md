---
uid: Microsoft.Quantum.Arrays.Zip4
title: Zip4 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip4
qsharp.summary: >-
  > [!WARNING]

  > Zip4 has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped4> instead.


  Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.
ms.openlocfilehash: d42b3b6db059163f6c766d4f133551be293c153d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696427"
---
# <a name="zip4-function"></a><span data-ttu-id="3cfad-102">Zip4 函数</span><span class="sxs-lookup"><span data-stu-id="3cfad-102">Zip4 function</span></span>

<span data-ttu-id="3cfad-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="3cfad-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="3cfad-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3cfad-104">Package: [](https://nuget.org/packages/)</span></span>


> [!WARNING]
> <span data-ttu-id="3cfad-105">Zip4 已被弃用。</span><span class="sxs-lookup"><span data-stu-id="3cfad-105">Zip4 has been deprecated.</span></span> <span data-ttu-id="3cfad-106">请改用 <xref:Microsoft.Quantum.Arrays.Zipped4>。</span><span class="sxs-lookup"><span data-stu-id="3cfad-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped4> instead.</span></span>

<span data-ttu-id="3cfad-107">给定四个数组，返回一个4元组的新数组，使每个4元组包含每个原始数组中的一个元素。</span><span class="sxs-lookup"><span data-stu-id="3cfad-107">Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.</span></span>

```qsharp
function Zip4<'T1, 'T2, 'T3, 'T4> (first : 'T1[], second : 'T2[], third : 'T3[], fourth : 'T4[]) : ('T1, 'T2, 'T3, 'T4)[]
```


## <a name="input"></a><span data-ttu-id="3cfad-108">输入</span><span class="sxs-lookup"><span data-stu-id="3cfad-108">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="3cfad-109">第一个：不是 1 []</span><span class="sxs-lookup"><span data-stu-id="3cfad-109">first : 'T1[]</span></span>

<span data-ttu-id="3cfad-110">一个数组，其中包含每个元组的第一个元素的值。</span><span class="sxs-lookup"><span data-stu-id="3cfad-110">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="3cfad-111">second：不 2 []</span><span class="sxs-lookup"><span data-stu-id="3cfad-111">second : 'T2[]</span></span>

<span data-ttu-id="3cfad-112">一个数组，其中包含每个元组的第二个元素的值。</span><span class="sxs-lookup"><span data-stu-id="3cfad-112">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="3cfad-113">第三个：不 3 []</span><span class="sxs-lookup"><span data-stu-id="3cfad-113">third : 'T3[]</span></span>

<span data-ttu-id="3cfad-114">一个数组，其中包含每个元组的第三个元素的值。</span><span class="sxs-lookup"><span data-stu-id="3cfad-114">An array containing values for the third element of each tuple.</span></span>


### <a name="fourth--t4"></a><span data-ttu-id="3cfad-115">第四个：不 4 []</span><span class="sxs-lookup"><span data-stu-id="3cfad-115">fourth : 'T4[]</span></span>

<span data-ttu-id="3cfad-116">一个数组，其中包含每个元组的第四个元素的值。</span><span class="sxs-lookup"><span data-stu-id="3cfad-116">An array containing values for the fourth element of each tuple.</span></span>



## <a name="output--t1t2t3t4"></a><span data-ttu-id="3cfad-117">输出： ( 不是1，不是2，不是3，不) []</span><span class="sxs-lookup"><span data-stu-id="3cfad-117">Output : ('T1,'T2,'T3,'T4)[]</span></span>

<span data-ttu-id="3cfad-118">一个数组，其中包含每个的窗体的4元组 `(first[idx], second[idx], third[idx], fourth[idx])` `idx` 。</span><span class="sxs-lookup"><span data-stu-id="3cfad-118">An array containing 4-tuples of the form `(first[idx], second[idx], third[idx], fourth[idx])` for each `idx`.</span></span> <span data-ttu-id="3cfad-119">如果四个数组的长度不相等，则输出将与输入的较短内容相同。</span><span class="sxs-lookup"><span data-stu-id="3cfad-119">If the four arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="3cfad-120">类型参数</span><span class="sxs-lookup"><span data-stu-id="3cfad-120">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="3cfad-121">T 1</span><span class="sxs-lookup"><span data-stu-id="3cfad-121">'T1</span></span>

<span data-ttu-id="3cfad-122">第一个数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="3cfad-122">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="3cfad-123">不是2</span><span class="sxs-lookup"><span data-stu-id="3cfad-123">'T2</span></span>

<span data-ttu-id="3cfad-124">第二个数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="3cfad-124">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="3cfad-125">不3</span><span class="sxs-lookup"><span data-stu-id="3cfad-125">'T3</span></span>

<span data-ttu-id="3cfad-126">第三个数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="3cfad-126">The type of the third array elements.</span></span>
### <a name="t4"></a><span data-ttu-id="3cfad-127">不4</span><span class="sxs-lookup"><span data-stu-id="3cfad-127">'T4</span></span>

<span data-ttu-id="3cfad-128">第四个数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="3cfad-128">The type of the fourth array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="3cfad-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3cfad-129">See Also</span></span>

- [<span data-ttu-id="3cfad-130">Microsoft.Quantum.Arrays.Zip</span><span class="sxs-lookup"><span data-stu-id="3cfad-130">Microsoft.Quantum.Arrays.Zip</span></span>](xref:Microsoft.Quantum.Arrays.Zip)
- [<span data-ttu-id="3cfad-131">Microsoft.Quantum.Arrays.Zip3</span><span class="sxs-lookup"><span data-stu-id="3cfad-131">Microsoft.Quantum.Arrays.Zip3</span></span>](xref:Microsoft.Quantum.Arrays.Zip3)