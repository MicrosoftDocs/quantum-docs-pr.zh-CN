---
uid: Microsoft.Quantum.Arrays.Windows
title: Windows 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Windows
qsharp.summary: Returns all consecutive subarrays of length `size`.
ms.openlocfilehash: 6071d1c3e5981855c57abd0e741b1de0201c30a3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696435"
---
# <a name="windows-function"></a><span data-ttu-id="65a23-102">Windows 函数</span><span class="sxs-lookup"><span data-stu-id="65a23-102">Windows function</span></span>

<span data-ttu-id="65a23-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="65a23-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="65a23-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="65a23-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="65a23-105">返回子的所有连续的 `size` 。</span><span class="sxs-lookup"><span data-stu-id="65a23-105">Returns all consecutive subarrays of length `size`.</span></span>

```qsharp
function Windows<'T> (size : Int, array : 'T[]) : 'T[][]
```


## <a name="description"></a><span data-ttu-id="65a23-106">说明</span><span class="sxs-lookup"><span data-stu-id="65a23-106">Description</span></span>

<span data-ttu-id="65a23-107">此函数 `n - size + 1` 按顺序返回所有长度的子 `size` ，其中 `n` 是的长度 `arr` 。</span><span class="sxs-lookup"><span data-stu-id="65a23-107">This function returns all `n - size + 1` subarrays of length `size` in order, where `n` is the length of `arr`.</span></span>
<span data-ttu-id="65a23-108">第一个子 `arr[0..size - 1], arr[1..size], arr[2..size + 1]` 一直为最后一个子数组 `arr[n - size..n - 1]` 。</span><span class="sxs-lookup"><span data-stu-id="65a23-108">The first subarrays are `arr[0..size - 1], arr[1..size], arr[2..size + 1]` until the last subarray `arr[n - size..n - 1]`.</span></span>

<span data-ttu-id="65a23-109">如果为 `size <= 0` 或 `size > n` ，则返回空数组。</span><span class="sxs-lookup"><span data-stu-id="65a23-109">If `size <= 0` or `size > n`, an empty array is returned.</span></span>

## <a name="input"></a><span data-ttu-id="65a23-110">输入</span><span class="sxs-lookup"><span data-stu-id="65a23-110">Input</span></span>

### <a name="size--int"></a><span data-ttu-id="65a23-111">大小： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="65a23-111">size : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="65a23-112">子的长度。</span><span class="sxs-lookup"><span data-stu-id="65a23-112">Length of the subarrays.</span></span>


### <a name="array--t"></a><span data-ttu-id="65a23-113">array： t []</span><span class="sxs-lookup"><span data-stu-id="65a23-113">array : 'T[]</span></span>

<span data-ttu-id="65a23-114">元素的数组。</span><span class="sxs-lookup"><span data-stu-id="65a23-114">An array of elements.</span></span>



## <a name="output--t"></a><span data-ttu-id="65a23-115">输出： t [] []</span><span class="sxs-lookup"><span data-stu-id="65a23-115">Output : 'T[][]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="65a23-116">类型参数</span><span class="sxs-lookup"><span data-stu-id="65a23-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="65a23-117">找</span><span class="sxs-lookup"><span data-stu-id="65a23-117">'T</span></span>

<span data-ttu-id="65a23-118">元素的类型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="65a23-118">The type of `array` elements.</span></span>