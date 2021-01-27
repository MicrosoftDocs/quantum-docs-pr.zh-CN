---
uid: Microsoft.Quantum.Arrays.MostAndTail
title: MostAndTail 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: MostAndTail
qsharp.summary: Returns a tuple of all but one and the last element of the array.
ms.openlocfilehash: fd5569f1b71ac2fdf2b5c08ba7dde172e3a6744e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845592"
---
# <a name="mostandtail-function"></a><span data-ttu-id="2b8c8-102">MostAndTail 函数</span><span class="sxs-lookup"><span data-stu-id="2b8c8-102">MostAndTail function</span></span>

<span data-ttu-id="2b8c8-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2b8c8-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2b8c8-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2b8c8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2b8c8-105">返回数组的所有元素，而不是数组的最后一个元素。</span><span class="sxs-lookup"><span data-stu-id="2b8c8-105">Returns a tuple of all but one and the last element of the array.</span></span>

```qsharp
function MostAndTail<'A> (array : 'A[]) : ('A[], 'A)
```


## <a name="input"></a><span data-ttu-id="2b8c8-106">输入</span><span class="sxs-lookup"><span data-stu-id="2b8c8-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="2b8c8-107">array： ' A []</span><span class="sxs-lookup"><span data-stu-id="2b8c8-107">array : 'A[]</span></span>

<span data-ttu-id="2b8c8-108">包含至少一个元素的数组。</span><span class="sxs-lookup"><span data-stu-id="2b8c8-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="2b8c8-109">输出： ( ' A []，' A) </span><span class="sxs-lookup"><span data-stu-id="2b8c8-109">Output : ('A[],'A)</span></span>

<span data-ttu-id="2b8c8-110">除数组的一个和最后一个元素之外的所有元素的元组。</span><span class="sxs-lookup"><span data-stu-id="2b8c8-110">A tuple of all but one and the last element of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2b8c8-111">类型参数</span><span class="sxs-lookup"><span data-stu-id="2b8c8-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="2b8c8-112">' A</span><span class="sxs-lookup"><span data-stu-id="2b8c8-112">'A</span></span>

<span data-ttu-id="2b8c8-113">数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="2b8c8-113">The type of the array elements.</span></span>