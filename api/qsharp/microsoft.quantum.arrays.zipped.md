---
uid: Microsoft.Quantum.Arrays.Zipped
title: Zipped 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zipped
qsharp.summary: Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 5177ab0ade5a9ad7788e60c1028befb84b0191d4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845336"
---
# <a name="zipped-function"></a><span data-ttu-id="25288-102">Zipped 函数</span><span class="sxs-lookup"><span data-stu-id="25288-102">Zipped function</span></span>

<span data-ttu-id="25288-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="25288-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="25288-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="25288-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="25288-105">给定两个数组，返回一个新的对数组，以便每个对都包含来自每个原始数组的元素。</span><span class="sxs-lookup"><span data-stu-id="25288-105">Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.</span></span>

```qsharp
function Zipped<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a><span data-ttu-id="25288-106">输入</span><span class="sxs-lookup"><span data-stu-id="25288-106">Input</span></span>

### <a name="left--t"></a><span data-ttu-id="25288-107">left： t []</span><span class="sxs-lookup"><span data-stu-id="25288-107">left : 'T[]</span></span>

<span data-ttu-id="25288-108">一个数组，其中包含每个元组的第一个元素的值。</span><span class="sxs-lookup"><span data-stu-id="25288-108">An array containing values for the first element of each tuple.</span></span>


### <a name="right--u"></a><span data-ttu-id="25288-109">right： ' U []</span><span class="sxs-lookup"><span data-stu-id="25288-109">right : 'U[]</span></span>

<span data-ttu-id="25288-110">一个数组，其中包含每个元组的第二个元素的值。</span><span class="sxs-lookup"><span data-stu-id="25288-110">An array containing values for the second element of each tuple.</span></span>



## <a name="output--tu"></a><span data-ttu-id="25288-111">Output： ( ' U) []</span><span class="sxs-lookup"><span data-stu-id="25288-111">Output : ('T,'U)[]</span></span>

<span data-ttu-id="25288-112">一个数组，其中包含每个的形式对 `(left[idx], right[idx])` `idx` 。</span><span class="sxs-lookup"><span data-stu-id="25288-112">An array containing pairs of the form `(left[idx], right[idx])` for each `idx`.</span></span> <span data-ttu-id="25288-113">如果两个数组的长度不相等，则输出将与输入的较短内容相同。</span><span class="sxs-lookup"><span data-stu-id="25288-113">If the two arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="25288-114">类型参数</span><span class="sxs-lookup"><span data-stu-id="25288-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="25288-115">找</span><span class="sxs-lookup"><span data-stu-id="25288-115">'T</span></span>

<span data-ttu-id="25288-116">左侧数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="25288-116">The type of the left array elements.</span></span>
### <a name="u"></a><span data-ttu-id="25288-117">' U</span><span class="sxs-lookup"><span data-stu-id="25288-117">'U</span></span>

<span data-ttu-id="25288-118">右侧数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="25288-118">The type of the right array elements.</span></span>

## <a name="example"></a><span data-ttu-id="25288-119">示例</span><span class="sxs-lookup"><span data-stu-id="25288-119">Example</span></span>

```qsharp
let left = [1, 3, 71];
let right = [false, true];
let pairs = Zipped(left, right); // [(1, false), (3, true)]
```

## <a name="see-also"></a><span data-ttu-id="25288-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="25288-120">See Also</span></span>

- [<span data-ttu-id="25288-121">Microsoft.Quantum.Arrays.Zipped3</span><span class="sxs-lookup"><span data-stu-id="25288-121">Microsoft.Quantum.Arrays.Zipped3</span></span>](xref:Microsoft.Quantum.Arrays.Zipped3)
- [<span data-ttu-id="25288-122">Microsoft.Quantum.Arrays.Zipped4</span><span class="sxs-lookup"><span data-stu-id="25288-122">Microsoft.Quantum.Arrays.Zipped4</span></span>](xref:Microsoft.Quantum.Arrays.Zipped4)
- [<span data-ttu-id="25288-123">"."</span><span class="sxs-lookup"><span data-stu-id="25288-123">Microsoft.Quantum.Arrays.Unzipped</span></span>](xref:Microsoft.Quantum.Arrays.Unzipped)