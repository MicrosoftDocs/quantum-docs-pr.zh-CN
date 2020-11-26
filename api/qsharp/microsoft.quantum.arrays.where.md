---
uid: Microsoft.Quantum.Arrays.Where
title: Where 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Where
qsharp.summary: Given a predicate and an array, returns the indices of that array where the predicate is true.
ms.openlocfilehash: 97598aa25d2d085aaab94f3d60ee64db9e2b89d6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219917"
---
# <a name="where-function"></a><span data-ttu-id="63d07-102">Where 函数</span><span class="sxs-lookup"><span data-stu-id="63d07-102">Where function</span></span>

<span data-ttu-id="63d07-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="63d07-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="63d07-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="63d07-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="63d07-105">给定谓词和数组后，返回该数组的索引，其中谓词为 true。</span><span class="sxs-lookup"><span data-stu-id="63d07-105">Given a predicate and an array, returns the indices of that array where the predicate is true.</span></span>

```qsharp
function Where<'T> (predicate : ('T -> Bool), array : 'T[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="63d07-106">输入</span><span class="sxs-lookup"><span data-stu-id="63d07-106">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="63d07-107">谓词：不 >[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="63d07-107">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="63d07-108">从 `'T` 到用于筛选元素的布尔值的函数。</span><span class="sxs-lookup"><span data-stu-id="63d07-108">A function from `'T` to Boolean that is used to filter elements.</span></span>


### <a name="array--t"></a><span data-ttu-id="63d07-109">array： t []</span><span class="sxs-lookup"><span data-stu-id="63d07-109">array : 'T[]</span></span>

<span data-ttu-id="63d07-110">上的元素的数组 `'T` 。</span><span class="sxs-lookup"><span data-stu-id="63d07-110">An array of elements over `'T`.</span></span>



## <a name="output--int"></a><span data-ttu-id="63d07-111">输出： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="63d07-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="63d07-112">一个索引数组，其中 `predicate` 为 true。</span><span class="sxs-lookup"><span data-stu-id="63d07-112">An array of indices where `predicate` is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="63d07-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="63d07-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="63d07-114">找</span><span class="sxs-lookup"><span data-stu-id="63d07-114">'T</span></span>

<span data-ttu-id="63d07-115">元素的类型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="63d07-115">The type of `array` elements.</span></span>