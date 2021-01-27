---
uid: Microsoft.Quantum.Arrays.Zip
title: Zip 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip
qsharp.summary: >-
  > [!WARNING]

  > Zip has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped> instead.


  Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 8ed658003f749efd31b8d841cecbb0a23a471af5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850904"
---
# <a name="zip-function"></a><span data-ttu-id="31d42-102">Zip 函数</span><span class="sxs-lookup"><span data-stu-id="31d42-102">Zip function</span></span>

<span data-ttu-id="31d42-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="31d42-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="31d42-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="31d42-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="31d42-105">Zip 已弃用。</span><span class="sxs-lookup"><span data-stu-id="31d42-105">Zip has been deprecated.</span></span> <span data-ttu-id="31d42-106">请改用 <xref:Microsoft.Quantum.Arrays.Zipped>。</span><span class="sxs-lookup"><span data-stu-id="31d42-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped> instead.</span></span>

<span data-ttu-id="31d42-107">给定两个数组，返回一个新的对数组，以便每个对都包含来自每个原始数组的元素。</span><span class="sxs-lookup"><span data-stu-id="31d42-107">Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.</span></span>

```qsharp
function Zip<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a><span data-ttu-id="31d42-108">输入</span><span class="sxs-lookup"><span data-stu-id="31d42-108">Input</span></span>

### <a name="left--t"></a><span data-ttu-id="31d42-109">left： t []</span><span class="sxs-lookup"><span data-stu-id="31d42-109">left : 'T[]</span></span>

<span data-ttu-id="31d42-110">一个数组，其中包含每个元组的第一个元素的值。</span><span class="sxs-lookup"><span data-stu-id="31d42-110">An array containing values for the first element of each tuple.</span></span>


### <a name="right--u"></a><span data-ttu-id="31d42-111">right： ' U []</span><span class="sxs-lookup"><span data-stu-id="31d42-111">right : 'U[]</span></span>

<span data-ttu-id="31d42-112">一个数组，其中包含每个元组的第二个元素的值。</span><span class="sxs-lookup"><span data-stu-id="31d42-112">An array containing values for the second element of each tuple.</span></span>



## <a name="output--tu"></a><span data-ttu-id="31d42-113">Output： ( ' U) []</span><span class="sxs-lookup"><span data-stu-id="31d42-113">Output : ('T,'U)[]</span></span>

<span data-ttu-id="31d42-114">一个数组，其中包含每个的形式对 `(left[idx], right[idx])` `idx` 。</span><span class="sxs-lookup"><span data-stu-id="31d42-114">An array containing pairs of the form `(left[idx], right[idx])` for each `idx`.</span></span> <span data-ttu-id="31d42-115">如果两个数组的长度不相等，则输出将与输入的较短内容相同。</span><span class="sxs-lookup"><span data-stu-id="31d42-115">If the two arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="31d42-116">类型参数</span><span class="sxs-lookup"><span data-stu-id="31d42-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="31d42-117">找</span><span class="sxs-lookup"><span data-stu-id="31d42-117">'T</span></span>

<span data-ttu-id="31d42-118">左侧数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="31d42-118">The type of the left array elements.</span></span>
### <a name="u"></a><span data-ttu-id="31d42-119">' U</span><span class="sxs-lookup"><span data-stu-id="31d42-119">'U</span></span>

<span data-ttu-id="31d42-120">右侧数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="31d42-120">The type of the right array elements.</span></span>

## <a name="example"></a><span data-ttu-id="31d42-121">示例</span><span class="sxs-lookup"><span data-stu-id="31d42-121">Example</span></span>

```qsharp
let left = [1, 3, 71];
let right = [false, true];
let pairs = Zip(left, right); // [(1, false), (3, true)]
```

## <a name="see-also"></a><span data-ttu-id="31d42-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="31d42-122">See Also</span></span>

- [<span data-ttu-id="31d42-123">Microsoft.Quantum.Arrays.Zip3</span><span class="sxs-lookup"><span data-stu-id="31d42-123">Microsoft.Quantum.Arrays.Zip3</span></span>](xref:Microsoft.Quantum.Arrays.Zip3)
- [<span data-ttu-id="31d42-124">Microsoft.Quantum.Arrays.Zip4</span><span class="sxs-lookup"><span data-stu-id="31d42-124">Microsoft.Quantum.Arrays.Zip4</span></span>](xref:Microsoft.Quantum.Arrays.Zip4)
- [<span data-ttu-id="31d42-125">"."</span><span class="sxs-lookup"><span data-stu-id="31d42-125">Microsoft.Quantum.Arrays.Unzipped</span></span>](xref:Microsoft.Quantum.Arrays.Unzipped)