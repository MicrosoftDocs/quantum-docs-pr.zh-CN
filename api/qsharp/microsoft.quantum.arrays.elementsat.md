---
uid: Microsoft.Quantum.Arrays.ElementsAt
title: ElementsAt 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: ElementsAt
qsharp.summary: Returns the array's elements at a given range of indices.
ms.openlocfilehash: 83b5e97085234e8249869f858400cba265d13058
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221447"
---
# <a name="elementsat-function"></a><span data-ttu-id="c34e1-102">ElementsAt 函数</span><span class="sxs-lookup"><span data-stu-id="c34e1-102">ElementsAt function</span></span>

<span data-ttu-id="c34e1-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c34e1-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c34e1-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c34e1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c34e1-105">返回给定索引范围内的数组元素。</span><span class="sxs-lookup"><span data-stu-id="c34e1-105">Returns the array's elements at a given range of indices.</span></span>

```qsharp
function ElementsAt<'T> (range : Range, array : 'T[]) : 'T[]
```


## <a name="input"></a><span data-ttu-id="c34e1-106">输入</span><span class="sxs-lookup"><span data-stu-id="c34e1-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="c34e1-107">范围： [范围](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="c34e1-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="c34e1-108">数组索引范围</span><span class="sxs-lookup"><span data-stu-id="c34e1-108">Range of array indexes</span></span>


### <a name="array--t"></a><span data-ttu-id="c34e1-109">array： t []</span><span class="sxs-lookup"><span data-stu-id="c34e1-109">array : 'T[]</span></span>

<span data-ttu-id="c34e1-110">Array</span><span class="sxs-lookup"><span data-stu-id="c34e1-110">Array</span></span>



## <a name="output--t"></a><span data-ttu-id="c34e1-111">输出： t []</span><span class="sxs-lookup"><span data-stu-id="c34e1-111">Output : 'T[]</span></span>



## <a name="type-parameters"></a><span data-ttu-id="c34e1-112">类型参数</span><span class="sxs-lookup"><span data-stu-id="c34e1-112">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="c34e1-113">找</span><span class="sxs-lookup"><span data-stu-id="c34e1-113">'T</span></span>

<span data-ttu-id="c34e1-114">的每个元素的类型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="c34e1-114">The type of each element of `array`.</span></span>

## <a name="see-also"></a><span data-ttu-id="c34e1-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c34e1-115">See Also</span></span>

- [<span data-ttu-id="c34e1-116">.Value.elementat。</span><span class="sxs-lookup"><span data-stu-id="c34e1-116">Microsoft.Quantum.Arrays.ElementAt</span></span>](xref:Microsoft.Quantum.Arrays.ElementAt)
- [<span data-ttu-id="c34e1-117">LookupFunction。</span><span class="sxs-lookup"><span data-stu-id="c34e1-117">Microsoft.Quantum.Arrays.LookupFunction</span></span>](xref:Microsoft.Quantum.Arrays.LookupFunction)