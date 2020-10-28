---
uid: Microsoft.Quantum.Arrays.Zip
title: Zip 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip
qsharp.summary: >-
  > [!WARNING]

  > Zip has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped> instead.


  Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.
ms.openlocfilehash: 32fea60fc36bfdbaa2ab2f3560f291bf4ce4fa51
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696432"
---
# <a name="zip-function"></a><span data-ttu-id="2f75e-102">Zip 函数</span><span class="sxs-lookup"><span data-stu-id="2f75e-102">Zip function</span></span>

<span data-ttu-id="2f75e-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2f75e-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2f75e-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2f75e-104">Package: [](https://nuget.org/packages/)</span></span>


> [!WARNING]
> <span data-ttu-id="2f75e-105">Zip 已弃用。</span><span class="sxs-lookup"><span data-stu-id="2f75e-105">Zip has been deprecated.</span></span> <span data-ttu-id="2f75e-106">请改用 <xref:Microsoft.Quantum.Arrays.Zipped>。</span><span class="sxs-lookup"><span data-stu-id="2f75e-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped> instead.</span></span>

<span data-ttu-id="2f75e-107">给定两个数组，返回一个新的对数组，以便每个对都包含来自每个原始数组的元素。</span><span class="sxs-lookup"><span data-stu-id="2f75e-107">Given two arrays, returns a new array of pairs such that each pair contains an element from each original array.</span></span>

```qsharp
function Zip<'T, 'U> (left : 'T[], right : 'U[]) : ('T, 'U)[]
```


## <a name="input"></a><span data-ttu-id="2f75e-108">输入</span><span class="sxs-lookup"><span data-stu-id="2f75e-108">Input</span></span>

### <a name="left--t"></a><span data-ttu-id="2f75e-109">left： t []</span><span class="sxs-lookup"><span data-stu-id="2f75e-109">left : 'T[]</span></span>

<span data-ttu-id="2f75e-110">一个数组，其中包含每个元组的第一个元素的值。</span><span class="sxs-lookup"><span data-stu-id="2f75e-110">An array containing values for the first element of each tuple.</span></span>


### <a name="right--u"></a><span data-ttu-id="2f75e-111">right： ' U []</span><span class="sxs-lookup"><span data-stu-id="2f75e-111">right : 'U[]</span></span>

<span data-ttu-id="2f75e-112">一个数组，其中包含每个元组的第二个元素的值。</span><span class="sxs-lookup"><span data-stu-id="2f75e-112">An array containing values for the second element of each tuple.</span></span>



## <a name="output--tu"></a><span data-ttu-id="2f75e-113">Output： ( ' U) []</span><span class="sxs-lookup"><span data-stu-id="2f75e-113">Output : ('T,'U)[]</span></span>

<span data-ttu-id="2f75e-114">一个数组，其中包含每个的形式对 `(left[idx], right[idx])` `idx` 。</span><span class="sxs-lookup"><span data-stu-id="2f75e-114">An array containing pairs of the form `(left[idx], right[idx])` for each `idx`.</span></span> <span data-ttu-id="2f75e-115">如果两个数组的长度不相等，则输出将与输入的较短内容相同。</span><span class="sxs-lookup"><span data-stu-id="2f75e-115">If the two arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2f75e-116">类型参数</span><span class="sxs-lookup"><span data-stu-id="2f75e-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="2f75e-117">找</span><span class="sxs-lookup"><span data-stu-id="2f75e-117">'T</span></span>

<span data-ttu-id="2f75e-118">左侧数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="2f75e-118">The type of the left array elements.</span></span>
### <a name="u"></a><span data-ttu-id="2f75e-119">' U</span><span class="sxs-lookup"><span data-stu-id="2f75e-119">'U</span></span>

<span data-ttu-id="2f75e-120">右侧数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="2f75e-120">The type of the right array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="2f75e-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2f75e-121">See Also</span></span>

- [<span data-ttu-id="2f75e-122">Microsoft.Quantum.Arrays.Zip3</span><span class="sxs-lookup"><span data-stu-id="2f75e-122">Microsoft.Quantum.Arrays.Zip3</span></span>](xref:Microsoft.Quantum.Arrays.Zip3)
- [<span data-ttu-id="2f75e-123">Microsoft.Quantum.Arrays.Zip4</span><span class="sxs-lookup"><span data-stu-id="2f75e-123">Microsoft.Quantum.Arrays.Zip4</span></span>](xref:Microsoft.Quantum.Arrays.Zip4)
- [<span data-ttu-id="2f75e-124">"."</span><span class="sxs-lookup"><span data-stu-id="2f75e-124">Microsoft.Quantum.Arrays.Unzipped</span></span>](xref:Microsoft.Quantum.Arrays.Unzipped)