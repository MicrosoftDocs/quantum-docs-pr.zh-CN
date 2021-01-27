---
uid: Microsoft.Quantum.Arrays.IndexOf
title: IndexOf 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: 64db55e831078a7130a3ced6a30bfbd2299c392d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848522"
---
# <a name="indexof-function"></a><span data-ttu-id="ba04f-102">IndexOf 函数</span><span class="sxs-lookup"><span data-stu-id="ba04f-102">IndexOf function</span></span>

<span data-ttu-id="ba04f-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="ba04f-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="ba04f-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ba04f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ba04f-105">返回满足给定谓词的数组中第一个元素的第一个索引。</span><span class="sxs-lookup"><span data-stu-id="ba04f-105">Returns the first index of the first element in an array that satisfies a given predicate.</span></span> <span data-ttu-id="ba04f-106">如果此类元素不存在，则返回-1。</span><span class="sxs-lookup"><span data-stu-id="ba04f-106">If no such element exists, returns -1.</span></span>

```qsharp
function IndexOf<'T> (predicate : ('T -> Bool), arr : 'T[]) : Int
```


## <a name="input"></a><span data-ttu-id="ba04f-107">输入</span><span class="sxs-lookup"><span data-stu-id="ba04f-107">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="ba04f-108">谓词：不 >[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="ba04f-108">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="ba04f-109">一个谓词函数，该函数对数组的元素进行操作。</span><span class="sxs-lookup"><span data-stu-id="ba04f-109">A predicate function acting on elements of the array.</span></span>


### <a name="arr--t"></a><span data-ttu-id="ba04f-110">arr： t []</span><span class="sxs-lookup"><span data-stu-id="ba04f-110">arr : 'T[]</span></span>

<span data-ttu-id="ba04f-111">要使用给定谓词搜索的数组。</span><span class="sxs-lookup"><span data-stu-id="ba04f-111">An array to be searched using the given predicate.</span></span>



## <a name="output--int"></a><span data-ttu-id="ba04f-112">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ba04f-112">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ba04f-113">最小索引 `idx` （例如 `predicate(arr[idx])` true），如果不存在此类元素，则为-1。</span><span class="sxs-lookup"><span data-stu-id="ba04f-113">Either the smallest index `idx` such that `predicate(arr[idx])` is true, or -1 if no such element exists.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="ba04f-114">类型参数</span><span class="sxs-lookup"><span data-stu-id="ba04f-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="ba04f-115">找</span><span class="sxs-lookup"><span data-stu-id="ba04f-115">'T</span></span>



## <a name="example"></a><span data-ttu-id="ba04f-116">示例</span><span class="sxs-lookup"><span data-stu-id="ba04f-116">Example</span></span>

<span data-ttu-id="ba04f-117">假设 `IsEven : Int -> Bool` 是一个函数，该函数在 `true` 且仅当其输入为偶数时返回。</span><span class="sxs-lookup"><span data-stu-id="ba04f-117">Suppose that `IsEven : Int -> Bool` is a function that returns `true` if and only if its input is even.</span></span> <span data-ttu-id="ba04f-118">然后，可将其与一起用于 `IndexOf` 查找数组中的第一个偶数元素：</span><span class="sxs-lookup"><span data-stu-id="ba04f-118">Then, this can be used with `IndexOf` to find the first even element in an array:</span></span>

```qsharp
let items = [1, 3, 17, 2, 21];
let idx = IndexOf(IsEven, items); // returns 3
```