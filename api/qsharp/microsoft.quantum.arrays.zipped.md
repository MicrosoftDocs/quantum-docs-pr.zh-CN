---
uid: Microsoft.Quantum.Arrays.Zipped
title: Zipped 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped
qsharp.summary: Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 67170fa005675f0e5d788c9c3b350fb9a961a597
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696429"
---
# <a name="zipped-function"></a><span data-ttu-id="b9e51-102">Zipped 函数</span><span class="sxs-lookup"><span data-stu-id="b9e51-102">Zipped function</span></span>

<span data-ttu-id="b9e51-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="b9e51-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="b9e51-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="b9e51-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="b9e51-105">给定两个数组，返回一个新的对数组，以便每个对都包含来自每个原始数组的元素。</span><span class="sxs-lookup"><span data-stu-id="b9e51-105">Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.</span></span>

```qsharp
function Zipped<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a><span data-ttu-id="b9e51-106">输入</span><span class="sxs-lookup"><span data-stu-id="b9e51-106">Input</span></span>

### <a name="left--t"></a><span data-ttu-id="b9e51-107">left： t []</span><span class="sxs-lookup"><span data-stu-id="b9e51-107">left : 'T[]</span></span>

<span data-ttu-id="b9e51-108">一个数组，其中包含每个元组的第一个元素的值。</span><span class="sxs-lookup"><span data-stu-id="b9e51-108">An array containing values for the first element of each tuple.</span></span>


### <a name="right--u"></a><span data-ttu-id="b9e51-109">right： ' U []</span><span class="sxs-lookup"><span data-stu-id="b9e51-109">right : 'U[]</span></span>

<span data-ttu-id="b9e51-110">一个数组，其中包含每个元组的第二个元素的值。</span><span class="sxs-lookup"><span data-stu-id="b9e51-110">An array containing values for the second element of each tuple.</span></span>



## <a name="output--tu"></a><span data-ttu-id="b9e51-111">Output： ( ' U) []</span><span class="sxs-lookup"><span data-stu-id="b9e51-111">Output : ('T,'U)[]</span></span>

<span data-ttu-id="b9e51-112">一个数组，其中包含每个的形式对 `(left[idx], right[idx])` `idx` 。</span><span class="sxs-lookup"><span data-stu-id="b9e51-112">An array containing pairs of the form `(left[idx], right[idx])` for each `idx`.</span></span> <span data-ttu-id="b9e51-113">如果两个数组的长度不相等，则输出将与输入的较短内容相同。</span><span class="sxs-lookup"><span data-stu-id="b9e51-113">If the two arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="b9e51-114">类型参数</span><span class="sxs-lookup"><span data-stu-id="b9e51-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="b9e51-115">找</span><span class="sxs-lookup"><span data-stu-id="b9e51-115">'T</span></span>

<span data-ttu-id="b9e51-116">左侧数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="b9e51-116">The type of the left array elements.</span></span>
### <a name="u"></a><span data-ttu-id="b9e51-117">' U</span><span class="sxs-lookup"><span data-stu-id="b9e51-117">'U</span></span>

<span data-ttu-id="b9e51-118">右侧数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="b9e51-118">The type of the right array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="b9e51-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b9e51-119">See Also</span></span>

- [<span data-ttu-id="b9e51-120">Microsoft.Quantum.Arrays.Zipped3</span><span class="sxs-lookup"><span data-stu-id="b9e51-120">Microsoft.Quantum.Arrays.Zipped3</span></span>](xref:Microsoft.Quantum.Arrays.Zipped3)
- [<span data-ttu-id="b9e51-121">Microsoft.Quantum.Arrays.Zipped4</span><span class="sxs-lookup"><span data-stu-id="b9e51-121">Microsoft.Quantum.Arrays.Zipped4</span></span>](xref:Microsoft.Quantum.Arrays.Zipped4)
- [<span data-ttu-id="b9e51-122">"."</span><span class="sxs-lookup"><span data-stu-id="b9e51-122">Microsoft.Quantum.Arrays.Unzipped</span></span>](xref:Microsoft.Quantum.Arrays.Unzipped)