---
uid: Microsoft.Quantum.Arrays.IndexOf
title: IndexOf 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: d63b204334611f8f2c3860f9ee1d756f637780e2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221005"
---
# <a name="indexof-function"></a><span data-ttu-id="541bd-102">IndexOf 函数</span><span class="sxs-lookup"><span data-stu-id="541bd-102">IndexOf function</span></span>

<span data-ttu-id="541bd-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="541bd-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="541bd-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="541bd-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="541bd-105">返回满足给定谓词的数组中第一个元素的第一个索引。</span><span class="sxs-lookup"><span data-stu-id="541bd-105">Returns the first index of the first element in an array that satisfies a given predicate.</span></span> <span data-ttu-id="541bd-106">如果此类元素不存在，则返回-1。</span><span class="sxs-lookup"><span data-stu-id="541bd-106">If no such element exists, returns -1.</span></span>

```qsharp
function IndexOf<'T> (predicate : ('T -> Bool), arr : 'T[]) : Int
```


## <a name="input"></a><span data-ttu-id="541bd-107">输入</span><span class="sxs-lookup"><span data-stu-id="541bd-107">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="541bd-108">谓词：不 >[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="541bd-108">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="541bd-109">一个谓词函数，该函数对数组的元素进行操作。</span><span class="sxs-lookup"><span data-stu-id="541bd-109">A predicate function acting on elements of the array.</span></span>


### <a name="arr--t"></a><span data-ttu-id="541bd-110">arr： t []</span><span class="sxs-lookup"><span data-stu-id="541bd-110">arr : 'T[]</span></span>

<span data-ttu-id="541bd-111">要使用给定谓词搜索的数组。</span><span class="sxs-lookup"><span data-stu-id="541bd-111">An array to be searched using the given predicate.</span></span>



## <a name="output--int"></a><span data-ttu-id="541bd-112">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="541bd-112">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="541bd-113">最小索引 `idx` （例如 `predicate(arr[idx])` true），如果不存在此类元素，则为-1。</span><span class="sxs-lookup"><span data-stu-id="541bd-113">Either the smallest index `idx` such that `predicate(arr[idx])` is true, or -1 if no such element exists.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="541bd-114">类型参数</span><span class="sxs-lookup"><span data-stu-id="541bd-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="541bd-115">找</span><span class="sxs-lookup"><span data-stu-id="541bd-115">'T</span></span>

