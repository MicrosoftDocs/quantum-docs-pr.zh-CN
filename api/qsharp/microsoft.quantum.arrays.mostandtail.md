---
uid: Microsoft.Quantum.Arrays.MostAndTail
title: MostAndTail 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MostAndTail
qsharp.summary: Returns a tuple of all but one and the last element of the array.
ms.openlocfilehash: 8786250cf2f78ce2e9ff8baddc856d0bc07cb9a0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696476"
---
# <a name="mostandtail-function"></a><span data-ttu-id="65608-102">MostAndTail 函数</span><span class="sxs-lookup"><span data-stu-id="65608-102">MostAndTail function</span></span>

<span data-ttu-id="65608-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="65608-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="65608-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="65608-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="65608-105">返回数组的所有元素，而不是数组的最后一个元素。</span><span class="sxs-lookup"><span data-stu-id="65608-105">Returns a tuple of all but one and the last element of the array.</span></span>

```qsharp
function MostAndTail<'A> (array : 'A[]) : ('A[], 'A)
```


## <a name="input"></a><span data-ttu-id="65608-106">输入</span><span class="sxs-lookup"><span data-stu-id="65608-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="65608-107">array： ' A []</span><span class="sxs-lookup"><span data-stu-id="65608-107">array : 'A[]</span></span>

<span data-ttu-id="65608-108">包含至少一个元素的数组。</span><span class="sxs-lookup"><span data-stu-id="65608-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="65608-109">输出： ( ' A []，' A) </span><span class="sxs-lookup"><span data-stu-id="65608-109">Output : ('A[],'A)</span></span>

<span data-ttu-id="65608-110">除数组的一个和最后一个元素之外的所有元素的元组。</span><span class="sxs-lookup"><span data-stu-id="65608-110">A tuple of all but one and the last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="65608-111">类型参数</span><span class="sxs-lookup"><span data-stu-id="65608-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="65608-112">' A</span><span class="sxs-lookup"><span data-stu-id="65608-112">'A</span></span>

<span data-ttu-id="65608-113">数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="65608-113">The type of the array elements.</span></span>