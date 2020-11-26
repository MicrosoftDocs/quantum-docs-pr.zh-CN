---
uid: Microsoft.Quantum.Arrays.Partitioned
title: 分区函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Partitioned
qsharp.summary: Splits an array into multiple parts.
ms.openlocfilehash: bce46262e3ef64a43e578098d81c5dd39225915e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220495"
---
# <a name="partitioned-function"></a><span data-ttu-id="91532-102">分区函数</span><span class="sxs-lookup"><span data-stu-id="91532-102">Partitioned function</span></span>

<span data-ttu-id="91532-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="91532-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="91532-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="91532-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="91532-105">将数组拆分为多个部分。</span><span class="sxs-lookup"><span data-stu-id="91532-105">Splits an array into multiple parts.</span></span>

```qsharp
function Partitioned<'T> (nElements : Int[], arr : 'T[]) : 'T[][]
```


## <a name="input"></a><span data-ttu-id="91532-106">输入</span><span class="sxs-lookup"><span data-stu-id="91532-106">Input</span></span>

### <a name="nelements--int"></a><span data-ttu-id="91532-107">nElements： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="91532-107">nElements : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="91532-108">数组的每个部分中的元素数</span><span class="sxs-lookup"><span data-stu-id="91532-108">Number of elements in each part of array</span></span>


### <a name="arr--t"></a><span data-ttu-id="91532-109">arr： t []</span><span class="sxs-lookup"><span data-stu-id="91532-109">arr : 'T[]</span></span>

<span data-ttu-id="91532-110">要拆分的输入数组。</span><span class="sxs-lookup"><span data-stu-id="91532-110">Input array to be split.</span></span>



## <a name="output--t"></a><span data-ttu-id="91532-111">输出： t [] []</span><span class="sxs-lookup"><span data-stu-id="91532-111">Output : 'T[][]</span></span>

<span data-ttu-id="91532-112">多个数组，其中第一个数组是第一个数组 `nElements[0]` `arr` ，第二个数组 `nElements[1]` 是 `arr` 等。最后一个数组将包含所有剩余元素。</span><span class="sxs-lookup"><span data-stu-id="91532-112">Multiple arrays where the first array is the first `nElements[0]` of `arr` and the second array are the next `nElements[1]` of `arr` etc. The last array will contain all remaining elements.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="91532-113">类型参数</span><span class="sxs-lookup"><span data-stu-id="91532-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="91532-114">找</span><span class="sxs-lookup"><span data-stu-id="91532-114">'T</span></span>

