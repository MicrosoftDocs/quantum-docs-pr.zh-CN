---
uid: Microsoft.Quantum.Arrays.Interleaved
title: 交错函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 1ff5999cc19f47e3dcae601b960446923b613d90
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220954"
---
# <a name="interleaved-function"></a><span data-ttu-id="c5db8-102">交错函数</span><span class="sxs-lookup"><span data-stu-id="c5db8-102">Interleaved function</span></span>

<span data-ttu-id="c5db8-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c5db8-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c5db8-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c5db8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c5db8-105">交错的两个 (数组几乎) 相同大小。</span><span class="sxs-lookup"><span data-stu-id="c5db8-105">Interleaves two arrays of (almost) same size.</span></span>

```qsharp
function Interleaved<'T> (first : 'T[], second : 'T[]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="c5db8-106">描述</span><span class="sxs-lookup"><span data-stu-id="c5db8-106">Description</span></span>

<span data-ttu-id="c5db8-107">此函数返回两个数组的交错，从第一个数组的第一个元素开始，然后从第二个数组的第一个元素开始，依次类推。</span><span class="sxs-lookup"><span data-stu-id="c5db8-107">This function returns the interleaving of two arrays, starting with the first element from the first array, then the first element from the second array, and so on.</span></span>

<span data-ttu-id="c5db8-108">第一个数组的长度必须与第二个数组的长度相同，或可以有一个以上的元素。</span><span class="sxs-lookup"><span data-stu-id="c5db8-108">The first array must either be of the same length as the second one, or can have one more element.</span></span>

## <a name="input"></a><span data-ttu-id="c5db8-109">输入</span><span class="sxs-lookup"><span data-stu-id="c5db8-109">Input</span></span>

### <a name="first--t"></a><span data-ttu-id="c5db8-110">第一个： t []</span><span class="sxs-lookup"><span data-stu-id="c5db8-110">first : 'T[]</span></span>

<span data-ttu-id="c5db8-111">要交错的第一个数组。</span><span class="sxs-lookup"><span data-stu-id="c5db8-111">The first array to be interleaved.</span></span>


### <a name="second--t"></a><span data-ttu-id="c5db8-112">second： t []</span><span class="sxs-lookup"><span data-stu-id="c5db8-112">second : 'T[]</span></span>

<span data-ttu-id="c5db8-113">要交错的第二个数组。</span><span class="sxs-lookup"><span data-stu-id="c5db8-113">The second array to be interleaved.</span></span>



## <a name="output--t"></a><span data-ttu-id="c5db8-114">输出： t []</span><span class="sxs-lookup"><span data-stu-id="c5db8-114">Output : 'T[]</span></span>

<span data-ttu-id="c5db8-115">交错数组</span><span class="sxs-lookup"><span data-stu-id="c5db8-115">Interleaved array</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c5db8-116">类型参数</span><span class="sxs-lookup"><span data-stu-id="c5db8-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c5db8-117">找</span><span class="sxs-lookup"><span data-stu-id="c5db8-117">'T</span></span>

<span data-ttu-id="c5db8-118">和的每个元素的 `first` 类型 `second` 。</span><span class="sxs-lookup"><span data-stu-id="c5db8-118">The type of each element of `first` and `second`.</span></span>