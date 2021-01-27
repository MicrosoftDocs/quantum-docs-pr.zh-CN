---
uid: Microsoft.Quantum.Arrays.Zipped3
title: Zipped3 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped3
qsharp.summary: Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.
ms.openlocfilehash: 6a4ffaeff8e6248a708ab9f8f9a6ff0c2e9e08d1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842175"
---
# <a name="zipped3-function"></a><span data-ttu-id="f9b61-102">Zipped3 函数</span><span class="sxs-lookup"><span data-stu-id="f9b61-102">Zipped3 function</span></span>

<span data-ttu-id="f9b61-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="f9b61-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="f9b61-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f9b61-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f9b61-105">给定三个数组，返回一个新数组，其中包含3个元组，以便每个第三个元组包含每个原始数组中的一个元素。</span><span class="sxs-lookup"><span data-stu-id="f9b61-105">Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.</span></span>

```qsharp
function Zipped3<'T1, 'T2, 'T3> (first : 'T1[], second : 'T2[], third : 'T3[]) : ('T1, 'T2, 'T3)[]
```


## <a name="input"></a><span data-ttu-id="f9b61-106">输入</span><span class="sxs-lookup"><span data-stu-id="f9b61-106">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="f9b61-107">第一个：不是 1 []</span><span class="sxs-lookup"><span data-stu-id="f9b61-107">first : 'T1[]</span></span>

<span data-ttu-id="f9b61-108">一个数组，其中包含每个元组的第一个元素的值。</span><span class="sxs-lookup"><span data-stu-id="f9b61-108">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="f9b61-109">second：不 2 []</span><span class="sxs-lookup"><span data-stu-id="f9b61-109">second : 'T2[]</span></span>

<span data-ttu-id="f9b61-110">一个数组，其中包含每个元组的第二个元素的值。</span><span class="sxs-lookup"><span data-stu-id="f9b61-110">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="f9b61-111">第三个：不 3 []</span><span class="sxs-lookup"><span data-stu-id="f9b61-111">third : 'T3[]</span></span>

<span data-ttu-id="f9b61-112">一个数组，其中包含每个元组的第三个元素的值。</span><span class="sxs-lookup"><span data-stu-id="f9b61-112">An array containing values for the third element of each tuple.</span></span>



## <a name="output--t1t2t3"></a><span data-ttu-id="f9b61-113">输出： ( 不是1，不是2，不是 3) []</span><span class="sxs-lookup"><span data-stu-id="f9b61-113">Output : ('T1,'T2,'T3)[]</span></span>

<span data-ttu-id="f9b61-114">一个数组，其中包含每个的窗体的3元组 `(first[idx], second[idx], third[idx])` `idx` 。</span><span class="sxs-lookup"><span data-stu-id="f9b61-114">An array containing 3-tuples of the form `(first[idx], second[idx], third[idx])` for each `idx`.</span></span> <span data-ttu-id="f9b61-115">如果三个数组的长度不相等，则输出将与输入的较短内容相同。</span><span class="sxs-lookup"><span data-stu-id="f9b61-115">If the three arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="f9b61-116">类型参数</span><span class="sxs-lookup"><span data-stu-id="f9b61-116">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="f9b61-117">T 1</span><span class="sxs-lookup"><span data-stu-id="f9b61-117">'T1</span></span>

<span data-ttu-id="f9b61-118">第一个数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="f9b61-118">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="f9b61-119">不是2</span><span class="sxs-lookup"><span data-stu-id="f9b61-119">'T2</span></span>

<span data-ttu-id="f9b61-120">第二个数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="f9b61-120">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="f9b61-121">不3</span><span class="sxs-lookup"><span data-stu-id="f9b61-121">'T3</span></span>

<span data-ttu-id="f9b61-122">第三个数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="f9b61-122">The type of the third array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="f9b61-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f9b61-123">See Also</span></span>

- [<span data-ttu-id="f9b61-124">Microsoft.Quantum.Arrays.Zipped</span><span class="sxs-lookup"><span data-stu-id="f9b61-124">Microsoft.Quantum.Arrays.Zipped</span></span>](xref:Microsoft.Quantum.Arrays.Zipped)
- [<span data-ttu-id="f9b61-125">Microsoft.Quantum.Arrays.Zipped4</span><span class="sxs-lookup"><span data-stu-id="f9b61-125">Microsoft.Quantum.Arrays.Zipped4</span></span>](xref:Microsoft.Quantum.Arrays.Zipped4)