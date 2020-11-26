---
uid: Microsoft.Quantum.Arrays.MostAndTail
title: MostAndTail 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MostAndTail
qsharp.summary: Returns a tuple of all but one and the last element of the array.
ms.openlocfilehash: 392efb20e4aaba80a77664444bb415d8bc9b0930
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220563"
---
# <a name="mostandtail-function"></a><span data-ttu-id="9fd6d-102">MostAndTail 函数</span><span class="sxs-lookup"><span data-stu-id="9fd6d-102">MostAndTail function</span></span>

<span data-ttu-id="9fd6d-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="9fd6d-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="9fd6d-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9fd6d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9fd6d-105">返回数组的所有元素，而不是数组的最后一个元素。</span><span class="sxs-lookup"><span data-stu-id="9fd6d-105">Returns a tuple of all but one and the last element of the array.</span></span>

```qsharp
function MostAndTail<'A> (array : 'A[]) : ('A[], 'A)
```


## <a name="input"></a><span data-ttu-id="9fd6d-106">输入</span><span class="sxs-lookup"><span data-stu-id="9fd6d-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="9fd6d-107">array： ' A []</span><span class="sxs-lookup"><span data-stu-id="9fd6d-107">array : 'A[]</span></span>

<span data-ttu-id="9fd6d-108">包含至少一个元素的数组。</span><span class="sxs-lookup"><span data-stu-id="9fd6d-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="9fd6d-109">输出： ( ' A []，' A) </span><span class="sxs-lookup"><span data-stu-id="9fd6d-109">Output : ('A[],'A)</span></span>

<span data-ttu-id="9fd6d-110">除数组的一个和最后一个元素之外的所有元素的元组。</span><span class="sxs-lookup"><span data-stu-id="9fd6d-110">A tuple of all but one and the last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9fd6d-111">类型参数</span><span class="sxs-lookup"><span data-stu-id="9fd6d-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="9fd6d-112">' A</span><span class="sxs-lookup"><span data-stu-id="9fd6d-112">'A</span></span>

<span data-ttu-id="9fd6d-113">数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="9fd6d-113">The type of the array elements.</span></span>