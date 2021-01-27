---
uid: Microsoft.Quantum.Arrays.Interleaved
title: 交错函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Interleaved
qsharp.summary: Interleaves two arrays of (almost) same size.
ms.openlocfilehash: 3605c0d0bc43cdb1097d025861c3ec2424763c86
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848113"
---
# <a name="interleaved-function"></a><span data-ttu-id="0b794-102">交错函数</span><span class="sxs-lookup"><span data-stu-id="0b794-102">Interleaved function</span></span>

<span data-ttu-id="0b794-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="0b794-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="0b794-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0b794-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0b794-105">交错的两个 (数组几乎) 相同大小。</span><span class="sxs-lookup"><span data-stu-id="0b794-105">Interleaves two arrays of (almost) same size.</span></span>

```qsharp
function Interleaved<'T> (first : 'T[], second : 'T[]) : 'T[]
```


## <a name="description"></a><span data-ttu-id="0b794-106">说明</span><span class="sxs-lookup"><span data-stu-id="0b794-106">Description</span></span>

<span data-ttu-id="0b794-107">此函数返回两个数组的交错，从第一个数组的第一个元素开始，然后从第二个数组的第一个元素开始，依次类推。</span><span class="sxs-lookup"><span data-stu-id="0b794-107">This function returns the interleaving of two arrays, starting with the first element from the first array, then the first element from the second array, and so on.</span></span>

<span data-ttu-id="0b794-108">第一个数组的长度必须与第二个数组的长度相同，或可以有一个以上的元素。</span><span class="sxs-lookup"><span data-stu-id="0b794-108">The first array must either be of the same length as the second one, or can have one more element.</span></span>

## <a name="input"></a><span data-ttu-id="0b794-109">输入</span><span class="sxs-lookup"><span data-stu-id="0b794-109">Input</span></span>

### <a name="first--t"></a><span data-ttu-id="0b794-110">第一个： t []</span><span class="sxs-lookup"><span data-stu-id="0b794-110">first : 'T[]</span></span>

<span data-ttu-id="0b794-111">要交错的第一个数组。</span><span class="sxs-lookup"><span data-stu-id="0b794-111">The first array to be interleaved.</span></span>


### <a name="second--t"></a><span data-ttu-id="0b794-112">second： t []</span><span class="sxs-lookup"><span data-stu-id="0b794-112">second : 'T[]</span></span>

<span data-ttu-id="0b794-113">要交错的第二个数组。</span><span class="sxs-lookup"><span data-stu-id="0b794-113">The second array to be interleaved.</span></span>



## <a name="output--t"></a><span data-ttu-id="0b794-114">输出： t []</span><span class="sxs-lookup"><span data-stu-id="0b794-114">Output : 'T[]</span></span>

<span data-ttu-id="0b794-115">交错数组</span><span class="sxs-lookup"><span data-stu-id="0b794-115">Interleaved array</span></span>

## <a name="type-parameters"></a><span data-ttu-id="0b794-116">类型参数</span><span class="sxs-lookup"><span data-stu-id="0b794-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="0b794-117">找</span><span class="sxs-lookup"><span data-stu-id="0b794-117">'T</span></span>

<span data-ttu-id="0b794-118">和的每个元素的 `first` 类型 `second` 。</span><span class="sxs-lookup"><span data-stu-id="0b794-118">The type of each element of `first` and `second`.</span></span>

## <a name="example"></a><span data-ttu-id="0b794-119">示例</span><span class="sxs-lookup"><span data-stu-id="0b794-119">Example</span></span>

```qsharp
// same as int1 = [1, -1, 2, -2, 3, -3]
let int1 = Interleaved([1, 2, 3], [-1, -2, -3])

// same as int2 = [false, true, false, true, false]
let int2 = Interleaved(ConstantArray(3, false), ConstantArray(2, true));
```