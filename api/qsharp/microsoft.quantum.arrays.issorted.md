---
uid: Microsoft.Quantum.Arrays.IsSorted
title: IsSorted 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsSorted
qsharp.summary: Given an array, returns whether that array is sorted as defined by a given comparison function.
ms.openlocfilehash: 330c1f789585f64cf255bc74f8a9c1ccf81b009e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696494"
---
# <a name="issorted-function"></a><span data-ttu-id="fe09f-102">IsSorted 函数</span><span class="sxs-lookup"><span data-stu-id="fe09f-102">IsSorted function</span></span>

<span data-ttu-id="fe09f-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="fe09f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="fe09f-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fe09f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fe09f-105">给定数组，返回数组是否按给定比较函数的定义进行排序。</span><span class="sxs-lookup"><span data-stu-id="fe09f-105">Given an array, returns whether that array is sorted as defined by a given comparison function.</span></span>

```qsharp
function IsSorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="fe09f-106">输入</span><span class="sxs-lookup"><span data-stu-id="fe09f-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="fe09f-107">比较： ( 不) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="fe09f-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="fe09f-108">比较两个元素的函数，如果为，则将 `a` 其视为小于或等于 `b` `comparison(a, b)` `true` 。</span><span class="sxs-lookup"><span data-stu-id="fe09f-108">A function that compares two elements such that `a` is considered to be less than or equal to `b` if `comparison(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="fe09f-109">array： t []</span><span class="sxs-lookup"><span data-stu-id="fe09f-109">array : 'T[]</span></span>

<span data-ttu-id="fe09f-110">要检查的数组。</span><span class="sxs-lookup"><span data-stu-id="fe09f-110">The array to be checked.</span></span>



## <a name="output--bool"></a><span data-ttu-id="fe09f-111">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="fe09f-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="fe09f-112">`true` 当且仅当对于每对元素 `a` 和 `b` 按顺序发生时 `array` ， `comparison(a, b)` 为 `true` 。</span><span class="sxs-lookup"><span data-stu-id="fe09f-112">`true` if and only if for each pair of elements `a` and `b` of `array` occuring in that order, `comparison(a, b)` is `true`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="fe09f-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="fe09f-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fe09f-114">找</span><span class="sxs-lookup"><span data-stu-id="fe09f-114">'T</span></span>

<span data-ttu-id="fe09f-115">的每个元素的类型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="fe09f-115">The type of each element of `array`.</span></span>

## <a name="remarks"></a><span data-ttu-id="fe09f-116">注解</span><span class="sxs-lookup"><span data-stu-id="fe09f-116">Remarks</span></span>

<span data-ttu-id="fe09f-117">假定函数是 `comparison` 可传递的，因此，如果 `comparison(a, b)` 和，则 `comparison(b, c)` `comparison(a, c)` 假定为。</span><span class="sxs-lookup"><span data-stu-id="fe09f-117">The function `comparison` is assumed to be transitive, such that if `comparison(a, b)` and `comparison(b, c)`, then `comparison(a, c)` is assumed.</span></span> <span data-ttu-id="fe09f-118">如果此属性不存在，则此函数的输出可能不正确。</span><span class="sxs-lookup"><span data-stu-id="fe09f-118">If this property does not hold, then the output of this function may be incorrect.</span></span>