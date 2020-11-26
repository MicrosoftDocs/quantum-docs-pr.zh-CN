---
uid: Microsoft.Quantum.Arrays.Zipped
title: Zipped 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped
qsharp.summary: Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 56ed97d573bf29dddb7cdb1c3f360218bf97889a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219747"
---
# <a name="zipped-function"></a><span data-ttu-id="5d80a-102">Zipped 函数</span><span class="sxs-lookup"><span data-stu-id="5d80a-102">Zipped function</span></span>

<span data-ttu-id="5d80a-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="5d80a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="5d80a-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5d80a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5d80a-105">给定两个数组，返回一个新的对数组，以便每个对都包含来自每个原始数组的元素。</span><span class="sxs-lookup"><span data-stu-id="5d80a-105">Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.</span></span>

```qsharp
function Zipped<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a><span data-ttu-id="5d80a-106">输入</span><span class="sxs-lookup"><span data-stu-id="5d80a-106">Input</span></span>

### <a name="left--t"></a><span data-ttu-id="5d80a-107">left： t []</span><span class="sxs-lookup"><span data-stu-id="5d80a-107">left : 'T[]</span></span>

<span data-ttu-id="5d80a-108">一个数组，其中包含每个元组的第一个元素的值。</span><span class="sxs-lookup"><span data-stu-id="5d80a-108">An array containing values for the first element of each tuple.</span></span>


### <a name="right--u"></a><span data-ttu-id="5d80a-109">right： ' U []</span><span class="sxs-lookup"><span data-stu-id="5d80a-109">right : 'U[]</span></span>

<span data-ttu-id="5d80a-110">一个数组，其中包含每个元组的第二个元素的值。</span><span class="sxs-lookup"><span data-stu-id="5d80a-110">An array containing values for the second element of each tuple.</span></span>



## <a name="output--tu"></a><span data-ttu-id="5d80a-111">Output： ( ' U) []</span><span class="sxs-lookup"><span data-stu-id="5d80a-111">Output : ('T,'U)[]</span></span>

<span data-ttu-id="5d80a-112">一个数组，其中包含每个的形式对 `(left[idx], right[idx])` `idx` 。</span><span class="sxs-lookup"><span data-stu-id="5d80a-112">An array containing pairs of the form `(left[idx], right[idx])` for each `idx`.</span></span> <span data-ttu-id="5d80a-113">如果两个数组的长度不相等，则输出将与输入的较短内容相同。</span><span class="sxs-lookup"><span data-stu-id="5d80a-113">If the two arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="5d80a-114">类型参数</span><span class="sxs-lookup"><span data-stu-id="5d80a-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="5d80a-115">找</span><span class="sxs-lookup"><span data-stu-id="5d80a-115">'T</span></span>

<span data-ttu-id="5d80a-116">左侧数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="5d80a-116">The type of the left array elements.</span></span>
### <a name="u"></a><span data-ttu-id="5d80a-117">' U</span><span class="sxs-lookup"><span data-stu-id="5d80a-117">'U</span></span>

<span data-ttu-id="5d80a-118">右侧数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="5d80a-118">The type of the right array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="5d80a-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5d80a-119">See Also</span></span>

- [<span data-ttu-id="5d80a-120">Microsoft.Quantum.Arrays.Zipped3</span><span class="sxs-lookup"><span data-stu-id="5d80a-120">Microsoft.Quantum.Arrays.Zipped3</span></span>](xref:Microsoft.Quantum.Arrays.Zipped3)
- [<span data-ttu-id="5d80a-121">Microsoft.Quantum.Arrays.Zipped4</span><span class="sxs-lookup"><span data-stu-id="5d80a-121">Microsoft.Quantum.Arrays.Zipped4</span></span>](xref:Microsoft.Quantum.Arrays.Zipped4)
- [<span data-ttu-id="5d80a-122">"."</span><span class="sxs-lookup"><span data-stu-id="5d80a-122">Microsoft.Quantum.Arrays.Unzipped</span></span>](xref:Microsoft.Quantum.Arrays.Unzipped)