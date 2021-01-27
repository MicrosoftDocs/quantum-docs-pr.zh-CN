---
uid: Microsoft.Quantum.Arrays.IsSorted
title: IsSorted 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IsSorted
qsharp.summary: Given an array, returns whether that array is sorted as defined by a given comparison function.
ms.openlocfilehash: a5916b5cbf36e1b6c421a81e04016a333e2b5be7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845738"
---
# <a name="issorted-function"></a><span data-ttu-id="1b4d5-102">IsSorted 函数</span><span class="sxs-lookup"><span data-stu-id="1b4d5-102">IsSorted function</span></span>

<span data-ttu-id="1b4d5-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="1b4d5-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="1b4d5-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="1b4d5-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="1b4d5-105">给定数组，返回数组是否按给定比较函数的定义进行排序。</span><span class="sxs-lookup"><span data-stu-id="1b4d5-105">Given an array, returns whether that array is sorted as defined by a given comparison function.</span></span>

```qsharp
function IsSorted<'T> (comparison : (('T, 'T) -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="1b4d5-106">输入</span><span class="sxs-lookup"><span data-stu-id="1b4d5-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="1b4d5-107">比较： ( 不) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="1b4d5-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="1b4d5-108">比较两个元素的函数，如果为，则将 `a` 其视为小于或等于 `b` `comparison(a, b)` `true` 。</span><span class="sxs-lookup"><span data-stu-id="1b4d5-108">A function that compares two elements such that `a` is considered to be less than or equal to `b` if `comparison(a, b)` is `true`.</span></span>


### <a name="array--t"></a><span data-ttu-id="1b4d5-109">array： t []</span><span class="sxs-lookup"><span data-stu-id="1b4d5-109">array : 'T[]</span></span>

<span data-ttu-id="1b4d5-110">要检查的数组。</span><span class="sxs-lookup"><span data-stu-id="1b4d5-110">The array to be checked.</span></span>



## <a name="output--bool"></a><span data-ttu-id="1b4d5-111">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="1b4d5-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="1b4d5-112">`true` 当且仅当对于每对元素 `a` 和 `b` 按顺序发生时 `array` ， `comparison(a, b)` 为 `true` 。</span><span class="sxs-lookup"><span data-stu-id="1b4d5-112">`true` if and only if for each pair of elements `a` and `b` of `array` occuring in that order, `comparison(a, b)` is `true`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="1b4d5-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="1b4d5-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="1b4d5-114">找</span><span class="sxs-lookup"><span data-stu-id="1b4d5-114">'T</span></span>

<span data-ttu-id="1b4d5-115">的每个元素的类型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="1b4d5-115">The type of each element of `array`.</span></span>

## <a name="remarks"></a><span data-ttu-id="1b4d5-116">备注</span><span class="sxs-lookup"><span data-stu-id="1b4d5-116">Remarks</span></span>

<span data-ttu-id="1b4d5-117">假定函数是 `comparison` 可传递的，因此，如果 `comparison(a, b)` 和，则 `comparison(b, c)` `comparison(a, c)` 假定为。</span><span class="sxs-lookup"><span data-stu-id="1b4d5-117">The function `comparison` is assumed to be transitive, such that if `comparison(a, b)` and `comparison(b, c)`, then `comparison(a, c)` is assumed.</span></span> <span data-ttu-id="1b4d5-118">如果此属性不存在，则此函数的输出可能不正确。</span><span class="sxs-lookup"><span data-stu-id="1b4d5-118">If this property does not hold, then the output of this function may be incorrect.</span></span>