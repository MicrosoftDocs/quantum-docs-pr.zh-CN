---
uid: Microsoft.Quantum.Arrays.Windows
title: Windows 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Windows
qsharp.summary: Returns all consecutive subarrays of length `size`.
ms.openlocfilehash: adfea2b9a2f6c22446817538d29586284dba723e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842200"
---
# <a name="windows-function"></a><span data-ttu-id="1f4c9-102">Windows 函数</span><span class="sxs-lookup"><span data-stu-id="1f4c9-102">Windows function</span></span>

<span data-ttu-id="1f4c9-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="1f4c9-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="1f4c9-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1f4c9-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1f4c9-105">返回子的所有连续的 `size` 。</span><span class="sxs-lookup"><span data-stu-id="1f4c9-105">Returns all consecutive subarrays of length `size`.</span></span>

```qsharp
function Windows<'T> (size : Int, array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="1f4c9-106">说明</span><span class="sxs-lookup"><span data-stu-id="1f4c9-106">Description</span></span>

<span data-ttu-id="1f4c9-107">此函数 `n - size + 1` 按顺序返回所有长度的子 `size` ，其中 `n` 是的长度 `arr` 。</span><span class="sxs-lookup"><span data-stu-id="1f4c9-107">This function returns all `n - size + 1` subarrays of length `size` in order, where `n` is the length of `arr`.</span></span>
<span data-ttu-id="1f4c9-108">第一个子 `arr[0..size - 1], arr[1..size], arr[2..size + 1]` 一直为最后一个子数组 `arr[n - size..n - 1]` 。</span><span class="sxs-lookup"><span data-stu-id="1f4c9-108">The first subarrays are `arr[0..size - 1], arr[1..size], arr[2..size + 1]` until the last subarray `arr[n - size..n - 1]`.</span></span>

<span data-ttu-id="1f4c9-109">如果为 `size <= 0` 或 `size > n` ，则返回空数组。</span><span class="sxs-lookup"><span data-stu-id="1f4c9-109">If `size <= 0` or `size > n`, an empty array is returned.</span></span>

## <a name="input"></a><span data-ttu-id="1f4c9-110">输入</span><span class="sxs-lookup"><span data-stu-id="1f4c9-110">Input</span></span>

### <a name="size--int"></a><span data-ttu-id="1f4c9-111">大小： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="1f4c9-111">size : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="1f4c9-112">子的长度。</span><span class="sxs-lookup"><span data-stu-id="1f4c9-112">Length of the subarrays.</span></span>


### <a name="array--t"></a><span data-ttu-id="1f4c9-113">array： t []</span><span class="sxs-lookup"><span data-stu-id="1f4c9-113">array : 'T[]</span></span>

<span data-ttu-id="1f4c9-114">元素的数组。</span><span class="sxs-lookup"><span data-stu-id="1f4c9-114">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="1f4c9-115">输出： t [] []</span><span class="sxs-lookup"><span data-stu-id="1f4c9-115">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="1f4c9-116">类型参数</span><span class="sxs-lookup"><span data-stu-id="1f4c9-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1f4c9-117">找</span><span class="sxs-lookup"><span data-stu-id="1f4c9-117">'T</span></span>

<span data-ttu-id="1f4c9-118">元素的类型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="1f4c9-118">The type of `array` elements.</span></span>

## <a name="example"></a><span data-ttu-id="1f4c9-119">示例</span><span class="sxs-lookup"><span data-stu-id="1f4c9-119">Example</span></span>

```qsharp
// same as [[1, 2, 3], [2, 3, 4], [3, 4, 5]]
let windows = Windows(3, [1, 2, 3, 4, 5]);
```