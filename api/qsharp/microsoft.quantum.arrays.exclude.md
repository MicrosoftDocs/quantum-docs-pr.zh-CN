---
uid: Microsoft.Quantum.Arrays.Exclude
title: Exclude 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Exclude
qsharp.summary: Returns an array containing the elements of another array, excluding elements at a given list of indices.
ms.openlocfilehash: e1fa7e728d4846db90872055454a8182a77a518b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696524"
---
# <a name="exclude-function"></a><span data-ttu-id="8b872-102">Exclude 函数</span><span class="sxs-lookup"><span data-stu-id="8b872-102">Exclude function</span></span>

<span data-ttu-id="8b872-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="8b872-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="8b872-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8b872-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8b872-105">返回一个数组，其中包含另一个数组的元素，而不包括给定索引列表中的元素。</span><span class="sxs-lookup"><span data-stu-id="8b872-105">Returns an array containing the elements of another array, excluding elements at a given list of indices.</span></span>

```qsharp
function Exclude<'T> (remove : Int[], array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="8b872-106">输入</span><span class="sxs-lookup"><span data-stu-id="8b872-106">Input</span></span>

### <a name="remove--int"></a><span data-ttu-id="8b872-107">删除： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="8b872-107">remove : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="8b872-108">指示应从输出中排除哪些元素的索引数组。</span><span class="sxs-lookup"><span data-stu-id="8b872-108">An array of indices denoting which elements should be excluded from the output.</span></span>


### <a name="array--t"></a><span data-ttu-id="8b872-109">array： t []</span><span class="sxs-lookup"><span data-stu-id="8b872-109">array : 'T[]</span></span>

<span data-ttu-id="8b872-110">输出数组中的值采用的数组。</span><span class="sxs-lookup"><span data-stu-id="8b872-110">Array of which the values in the output array are taken.</span></span>



## <a name="output--t"></a><span data-ttu-id="8b872-111">输出： t []</span><span class="sxs-lookup"><span data-stu-id="8b872-111">Output : 'T[]</span></span>

<span data-ttu-id="8b872-112">一个数组， `output` 它 `output[0]` 是 `array` 其索引未出现在中的第一个元素 `remove` ，这 `output[1]` 是第二个这样的元素，依此类推。</span><span class="sxs-lookup"><span data-stu-id="8b872-112">An array `output` such that `output[0]` is the first element of `array` whose index does not appear in `remove`, such that `output[1]` is the second such element, and so forth.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="8b872-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="8b872-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="8b872-114">找</span><span class="sxs-lookup"><span data-stu-id="8b872-114">'T</span></span>

<span data-ttu-id="8b872-115">数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="8b872-115">The type of the array elements.</span></span>