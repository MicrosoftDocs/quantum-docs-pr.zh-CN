---
uid: Microsoft.Quantum.Arrays.Zipped4
title: Zipped4 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped4
qsharp.summary: Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.
ms.openlocfilehash: d5ee10ac9776383e75bc16a5c003a8b1a65c5698
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219628"
---
# <a name="zipped4-function"></a><span data-ttu-id="4ab06-102">Zipped4 函数</span><span class="sxs-lookup"><span data-stu-id="4ab06-102">Zipped4 function</span></span>

<span data-ttu-id="4ab06-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="4ab06-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="4ab06-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="4ab06-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="4ab06-105">给定四个数组，返回一个4元组的新数组，使每个4元组包含每个原始数组中的一个元素。</span><span class="sxs-lookup"><span data-stu-id="4ab06-105">Given four arrays, returns a new array of 4-tuples such that each 4-tuple contains an element from each original array.</span></span>

```qsharp
function Zipped4<'T1, 'T2, 'T3, 'T4> (first : 'T1[], second : 'T2[], third : 'T3[], fourth : 'T4[]) : ('T1, 'T2, 'T3, 'T4)[]
```


## <a name="input"></a><span data-ttu-id="4ab06-106">输入</span><span class="sxs-lookup"><span data-stu-id="4ab06-106">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="4ab06-107">第一个：不是 1 []</span><span class="sxs-lookup"><span data-stu-id="4ab06-107">first : 'T1[]</span></span>

<span data-ttu-id="4ab06-108">一个数组，其中包含每个元组的第一个元素的值。</span><span class="sxs-lookup"><span data-stu-id="4ab06-108">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="4ab06-109">second：不 2 []</span><span class="sxs-lookup"><span data-stu-id="4ab06-109">second : 'T2[]</span></span>

<span data-ttu-id="4ab06-110">一个数组，其中包含每个元组的第二个元素的值。</span><span class="sxs-lookup"><span data-stu-id="4ab06-110">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="4ab06-111">第三个：不 3 []</span><span class="sxs-lookup"><span data-stu-id="4ab06-111">third : 'T3[]</span></span>

<span data-ttu-id="4ab06-112">一个数组，其中包含每个元组的第三个元素的值。</span><span class="sxs-lookup"><span data-stu-id="4ab06-112">An array containing values for the third element of each tuple.</span></span>


### <a name="fourth--t4"></a><span data-ttu-id="4ab06-113">第四个：不 4 []</span><span class="sxs-lookup"><span data-stu-id="4ab06-113">fourth : 'T4[]</span></span>

<span data-ttu-id="4ab06-114">一个数组，其中包含每个元组的第四个元素的值。</span><span class="sxs-lookup"><span data-stu-id="4ab06-114">An array containing values for the fourth element of each tuple.</span></span>



## <a name="output--t1t2t3t4"></a><span data-ttu-id="4ab06-115">输出： ( 不是1，不是2，不是3，不) []</span><span class="sxs-lookup"><span data-stu-id="4ab06-115">Output : ('T1,'T2,'T3,'T4)[]</span></span>

<span data-ttu-id="4ab06-116">一个数组，其中包含每个的窗体的4元组 `(first[idx], second[idx], third[idx], fourth[idx])` `idx` 。</span><span class="sxs-lookup"><span data-stu-id="4ab06-116">An array containing 4-tuples of the form `(first[idx], second[idx], third[idx], fourth[idx])` for each `idx`.</span></span> <span data-ttu-id="4ab06-117">如果四个数组的长度不相等，则输出将与输入的较短内容相同。</span><span class="sxs-lookup"><span data-stu-id="4ab06-117">If the four arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="4ab06-118">类型参数</span><span class="sxs-lookup"><span data-stu-id="4ab06-118">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="4ab06-119">T 1</span><span class="sxs-lookup"><span data-stu-id="4ab06-119">'T1</span></span>

<span data-ttu-id="4ab06-120">第一个数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="4ab06-120">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="4ab06-121">不是2</span><span class="sxs-lookup"><span data-stu-id="4ab06-121">'T2</span></span>

<span data-ttu-id="4ab06-122">第二个数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="4ab06-122">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="4ab06-123">不3</span><span class="sxs-lookup"><span data-stu-id="4ab06-123">'T3</span></span>

<span data-ttu-id="4ab06-124">第三个数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="4ab06-124">The type of the third array elements.</span></span>
### <a name="t4"></a><span data-ttu-id="4ab06-125">不4</span><span class="sxs-lookup"><span data-stu-id="4ab06-125">'T4</span></span>

<span data-ttu-id="4ab06-126">第四个数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="4ab06-126">The type of the fourth array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="4ab06-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4ab06-127">See Also</span></span>

- [<span data-ttu-id="4ab06-128">Microsoft.Quantum.Arrays.Zipped</span><span class="sxs-lookup"><span data-stu-id="4ab06-128">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)
- [<span data-ttu-id="4ab06-129">Microsoft.Quantum.Arrays.Zipped3</span><span class="sxs-lookup"><span data-stu-id="4ab06-129">Microsoft.Quantum.Arrays.Zipped3</span></span>](xref:Microsoft.Quantum.Arrays.Zipped3)