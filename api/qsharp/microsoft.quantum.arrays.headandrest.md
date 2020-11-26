---
uid: Microsoft.Quantum.Arrays.HeadAndRest
title: HeadAndRest 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: HeadAndRest
qsharp.summary: Returns a tuple of first and all remaining elements of the array.
ms.openlocfilehash: 1144e00227df1cd7d96bc76b118b0b556adbaa96
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221073"
---
# <a name="headandrest-function"></a><span data-ttu-id="2286a-102">HeadAndRest 函数</span><span class="sxs-lookup"><span data-stu-id="2286a-102">HeadAndRest function</span></span>

<span data-ttu-id="2286a-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="2286a-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="2286a-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="2286a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="2286a-105">返回数组的第一个和所有剩余元素的元组。</span><span class="sxs-lookup"><span data-stu-id="2286a-105">Returns a tuple of first and all remaining elements of the array.</span></span>

```qsharp
function HeadAndRest<'A> (array : 'A[]) : ('A, 'A[])
```


## <a name="input"></a><span data-ttu-id="2286a-106">输入</span><span class="sxs-lookup"><span data-stu-id="2286a-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="2286a-107">array： ' A []</span><span class="sxs-lookup"><span data-stu-id="2286a-107">array : 'A[]</span></span>

<span data-ttu-id="2286a-108">包含至少一个元素的数组。</span><span class="sxs-lookup"><span data-stu-id="2286a-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="2286a-109">Output： ( ' A，' A [] ) </span><span class="sxs-lookup"><span data-stu-id="2286a-109">Output : ('A,'A[])</span></span>

<span data-ttu-id="2286a-110">数组的第一个和所有剩余元素的元组。</span><span class="sxs-lookup"><span data-stu-id="2286a-110">A tuple of first and all remaining elements of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="2286a-111">类型参数</span><span class="sxs-lookup"><span data-stu-id="2286a-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="2286a-112">' A</span><span class="sxs-lookup"><span data-stu-id="2286a-112">'A</span></span>

<span data-ttu-id="2286a-113">数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="2286a-113">The type of the array elements.</span></span>