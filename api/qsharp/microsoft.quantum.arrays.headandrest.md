---
uid: Microsoft.Quantum.Arrays.HeadAndRest
title: HeadAndRest 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: HeadAndRest
qsharp.summary: Returns a tuple of first and all remaining elements of the array.
ms.openlocfilehash: 9af4ba48a21d3cdf932b2f702051a70a6108db1b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696507"
---
# <a name="headandrest-function"></a><span data-ttu-id="c4312-102">HeadAndRest 函数</span><span class="sxs-lookup"><span data-stu-id="c4312-102">HeadAndRest function</span></span>

<span data-ttu-id="c4312-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="c4312-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="c4312-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c4312-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c4312-105">返回数组的第一个和所有剩余元素的元组。</span><span class="sxs-lookup"><span data-stu-id="c4312-105">Returns a tuple of first and all remaining elements of the array.</span></span>

```qsharp
function HeadAndRest<'A> (array : 'A[]) : ('A, 'A[])
```


## <a name="input"></a><span data-ttu-id="c4312-106">输入</span><span class="sxs-lookup"><span data-stu-id="c4312-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="c4312-107">array： ' A []</span><span class="sxs-lookup"><span data-stu-id="c4312-107">array : 'A[]</span></span>

<span data-ttu-id="c4312-108">包含至少一个元素的数组。</span><span class="sxs-lookup"><span data-stu-id="c4312-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="c4312-109">Output： ( ' A，' A [] ) </span><span class="sxs-lookup"><span data-stu-id="c4312-109">Output : ('A,'A[])</span></span>

<span data-ttu-id="c4312-110">数组的第一个和所有剩余元素的元组。</span><span class="sxs-lookup"><span data-stu-id="c4312-110">A tuple of first and all remaining elements of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="c4312-111">类型参数</span><span class="sxs-lookup"><span data-stu-id="c4312-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="c4312-112">' A</span><span class="sxs-lookup"><span data-stu-id="c4312-112">'A</span></span>

<span data-ttu-id="c4312-113">数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="c4312-113">The type of the array elements.</span></span>