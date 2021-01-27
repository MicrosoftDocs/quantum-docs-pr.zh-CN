---
uid: Microsoft.Quantum.Arrays.Where
title: Where 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Where
qsharp.summary: Given a predicate and an array, returns the indices of that array where the predicate is true.
ms.openlocfilehash: 4a938114689177f7a9ee182e6e5f36debe4edac7
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842217"
---
# <a name="where-function"></a><span data-ttu-id="82c35-102">Where 函数</span><span class="sxs-lookup"><span data-stu-id="82c35-102">Where function</span></span>

<span data-ttu-id="82c35-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="82c35-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="82c35-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="82c35-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="82c35-105">给定谓词和数组后，返回该数组的索引，其中谓词为 true。</span><span class="sxs-lookup"><span data-stu-id="82c35-105">Given a predicate and an array, returns the indices of that array where the predicate is true.</span></span>

```qsharp
function Where<'T> (predicate : ('T -> Bool), array : 'T[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="82c35-106">输入</span><span class="sxs-lookup"><span data-stu-id="82c35-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="82c35-107">谓词：不 >[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="82c35-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="82c35-108">从 `'T` 到用于筛选元素的布尔值的函数。</span><span class="sxs-lookup"><span data-stu-id="82c35-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="82c35-109">array： t []</span><span class="sxs-lookup"><span data-stu-id="82c35-109">array : 'T[]</span></span>

<span data-ttu-id="82c35-110">上的元素的数组 `'T` 。</span><span class="sxs-lookup"><span data-stu-id="82c35-110">An array of elements over `'T`.</span></span>



## <a name="output--int"></a><span data-ttu-id="82c35-111">输出： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="82c35-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="82c35-112">一个索引数组，其中 `predicate` 为 true。</span><span class="sxs-lookup"><span data-stu-id="82c35-112">An array of indices where `predicate` is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="82c35-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="82c35-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="82c35-114">找</span><span class="sxs-lookup"><span data-stu-id="82c35-114">'T</span></span>

<span data-ttu-id="82c35-115">元素的类型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="82c35-115">The type of `array` elements.</span></span>