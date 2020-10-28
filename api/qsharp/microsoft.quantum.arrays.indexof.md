---
uid: Microsoft.Quantum.Arrays.IndexOf
title: IndexOf 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexOf
qsharp.summary: Returns the first index of the first element in an array that satisfies a given predicate. If no such element exists, returns -1.
ms.openlocfilehash: 7ff80f13f432a18f216b2dee4bd65b1e82034fa5
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696506"
---
# <a name="indexof-function"></a><span data-ttu-id="e9bdc-102">IndexOf 函数</span><span class="sxs-lookup"><span data-stu-id="e9bdc-102">IndexOf function</span></span>

<span data-ttu-id="e9bdc-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="e9bdc-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="e9bdc-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e9bdc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e9bdc-105">返回满足给定谓词的数组中第一个元素的第一个索引。</span><span class="sxs-lookup"><span data-stu-id="e9bdc-105">Returns the first index of the first element in an array that satisfies a given predicate.</span></span> <span data-ttu-id="e9bdc-106">如果此类元素不存在，则返回-1。</span><span class="sxs-lookup"><span data-stu-id="e9bdc-106">If no such element exists, returns -1.</span></span>

```qsharp
function IndexOf<'T> (predicate : ('T -> Bool), arr : 'T[]) : Int
```


## <a name="input"></a><span data-ttu-id="e9bdc-107">输入</span><span class="sxs-lookup"><span data-stu-id="e9bdc-107">Input</span></span>

### <a name="predicate--t---bool"></a><span data-ttu-id="e9bdc-108">谓词：不 >[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="e9bdc-108">predicate : 'T -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e9bdc-109">一个谓词函数，该函数对数组的元素进行操作。</span><span class="sxs-lookup"><span data-stu-id="e9bdc-109">A predicate function acting on elements of the array.</span></span>


### <a name="arr--t"></a><span data-ttu-id="e9bdc-110">arr： t []</span><span class="sxs-lookup"><span data-stu-id="e9bdc-110">arr : 'T[]</span></span>

<span data-ttu-id="e9bdc-111">要使用给定谓词搜索的数组。</span><span class="sxs-lookup"><span data-stu-id="e9bdc-111">An array to be searched using the given predicate.</span></span>



## <a name="output--int"></a><span data-ttu-id="e9bdc-112">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e9bdc-112">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e9bdc-113">最小索引 `idx` （例如 `predicate(arr[idx])` true），如果不存在此类元素，则为-1。</span><span class="sxs-lookup"><span data-stu-id="e9bdc-113">Either the smallest index `idx` such that `predicate(arr[idx])` is true, or -1 if no such element exists.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="e9bdc-114">类型参数</span><span class="sxs-lookup"><span data-stu-id="e9bdc-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="e9bdc-115">找</span><span class="sxs-lookup"><span data-stu-id="e9bdc-115">'T</span></span>

