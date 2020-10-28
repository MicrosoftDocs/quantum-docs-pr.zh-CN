---
uid: Microsoft.Quantum.Arrays.LookupFunction
title: LookupFunction 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: LookupFunction
qsharp.summary: Given an array, returns a function which returns elements of that array.
ms.openlocfilehash: c929054b96ee499db896cacf0e3ae4da6f6c4b98
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696489"
---
# <a name="lookupfunction-function"></a><span data-ttu-id="ac120-102">LookupFunction 函数</span><span class="sxs-lookup"><span data-stu-id="ac120-102">LookupFunction function</span></span>

<span data-ttu-id="ac120-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ac120-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ac120-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="ac120-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="ac120-105">给定一个数组，返回返回该数组的元素的函数。</span><span class="sxs-lookup"><span data-stu-id="ac120-105">Given an array, returns a function which returns elements of that array.</span></span>

```qsharp
function LookupFunction<'T> (array : 'T[]) : (Int -> 'T)
```


## <a name="input"></a><span data-ttu-id="ac120-106">输入</span><span class="sxs-lookup"><span data-stu-id="ac120-106">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="ac120-107">array： t []</span><span class="sxs-lookup"><span data-stu-id="ac120-107">array : 'T[]</span></span>

<span data-ttu-id="ac120-108">要表示为查找函数的数组。</span><span class="sxs-lookup"><span data-stu-id="ac120-108">The array to be represented as a lookup function.</span></span>



## <a name="output--int---t"></a><span data-ttu-id="ac120-109">输出： [Int](xref:microsoft.quantum.lang-ref.int) -></span><span class="sxs-lookup"><span data-stu-id="ac120-109">Output : [Int](xref:microsoft.quantum.lang-ref.int) -> 'T</span></span>

<span data-ttu-id="ac120-110">`f`这样的函数 `f(idx) == f[idx]` 。</span><span class="sxs-lookup"><span data-stu-id="ac120-110">A function `f` such that `f(idx) == f[idx]`.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ac120-111">类型参数</span><span class="sxs-lookup"><span data-stu-id="ac120-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ac120-112">找</span><span class="sxs-lookup"><span data-stu-id="ac120-112">'T</span></span>

<span data-ttu-id="ac120-113">表示为查找函数的数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="ac120-113">The type of the elements of the array being represented as a lookup function.</span></span>

## <a name="remarks"></a><span data-ttu-id="ac120-114">注解</span><span class="sxs-lookup"><span data-stu-id="ac120-114">Remarks</span></span>

<span data-ttu-id="ac120-115">此函数主要用于与将 `Int -> 'T` 函数作为其参数的函数和操作进行互操作。</span><span class="sxs-lookup"><span data-stu-id="ac120-115">This function is mainly useful for interoperating with functions and operations that take `Int -> 'T` functions as their arguments.</span></span> <span data-ttu-id="ac120-116">这种情况很常见，例如，在生成器表示库中，函数用于避免需要在内存中记录整个数组。</span><span class="sxs-lookup"><span data-stu-id="ac120-116">This is common, for instance, in the generator representation library, where functions are used to avoid the need to record an entire array in memory.</span></span>