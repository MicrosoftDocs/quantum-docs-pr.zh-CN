---
uid: Microsoft.Quantum.Arrays.Exclude
title: Exclude 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Exclude
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: 4ea0d754fce4fc7e3e4e42e55b56720cb3f95ca6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221345"
---
# <a name="exclude-function"></a><span data-ttu-id="6d1c6-102">Exclude 函数</span><span class="sxs-lookup"><span data-stu-id="6d1c6-102">Exclude function</span></span>

<span data-ttu-id="6d1c6-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="6d1c6-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="6d1c6-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6d1c6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6d1c6-105">返回一个数组，其中包含另一个数组的元素，而不包括给定索引列表中的元素。</span><span class="sxs-lookup"><span data-stu-id="6d1c6-105">Returns an array containing the elements of another array, excluding elements at a given list of indices.</span></span>

```qsharp
function Exclude<'T> (remove : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="6d1c6-106">输入</span><span class="sxs-lookup"><span data-stu-id="6d1c6-106">Input</span></span>

### <a name="remove--int"></a><span data-ttu-id="6d1c6-107">删除： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="6d1c6-107">remove : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="6d1c6-108">指示应从输出中排除哪些元素的索引数组。</span><span class="sxs-lookup"><span data-stu-id="6d1c6-108">An array of indices denoting which elements should be excluded from the output.</span></span>


### <a name="array--t"></a><span data-ttu-id="6d1c6-109">array： t []</span><span class="sxs-lookup"><span data-stu-id="6d1c6-109">array : 'T[]</span></span>

<span data-ttu-id="6d1c6-110">输出数组中的值采用的数组。</span><span class="sxs-lookup"><span data-stu-id="6d1c6-110">Array of which the values in the output array are taken.</span></span>



## <a name="output--t"></a><span data-ttu-id="6d1c6-111">输出： t []</span><span class="sxs-lookup"><span data-stu-id="6d1c6-111">Output : 'T[]</span></span>

<span data-ttu-id="6d1c6-112">一个数组， `output` 它 `output[0]` 是 `array` 其索引未出现在中的第一个元素 `remove` ，这 `output[1]` 是第二个这样的元素，依此类推。</span><span class="sxs-lookup"><span data-stu-id="6d1c6-112">An array `output` such that `output[0]` is the first element of `array` whose index does not appear in `remove`, such that `output[1]` is the second such element, and so forth.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="6d1c6-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="6d1c6-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="6d1c6-114">找</span><span class="sxs-lookup"><span data-stu-id="6d1c6-114">'T</span></span>

<span data-ttu-id="6d1c6-115">数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="6d1c6-115">The type of the array elements.</span></span>