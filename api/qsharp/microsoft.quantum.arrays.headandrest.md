---
uid: Microsoft.Quantum.Arrays.HeadAndRest
title: HeadAndRest 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: HeadAndRest
qsharp.summary: Returns a tuple of first and all remaining elements of the array.
ms.openlocfilehash: c082e0a917343c18e5f511f065b2e78f1e217ecc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848549"
---
# <a name="headandrest-function"></a><span data-ttu-id="28deb-102">HeadAndRest 函数</span><span class="sxs-lookup"><span data-stu-id="28deb-102">HeadAndRest function</span></span>

<span data-ttu-id="28deb-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="28deb-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="28deb-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="28deb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="28deb-105">返回数组的第一个和所有剩余元素的元组。</span><span class="sxs-lookup"><span data-stu-id="28deb-105">Returns a tuple of first and all remaining elements of the array.</span></span>

```qsharp
function HeadAndRest<'A> (array : 'A[]) : ('A, 'A[])
```


## <a name="input"></a><span data-ttu-id="28deb-106">输入</span><span class="sxs-lookup"><span data-stu-id="28deb-106">Input</span></span>

### <a name="array--a"></a><span data-ttu-id="28deb-107">array： ' A []</span><span class="sxs-lookup"><span data-stu-id="28deb-107">array : 'A[]</span></span>

<span data-ttu-id="28deb-108">包含至少一个元素的数组。</span><span class="sxs-lookup"><span data-stu-id="28deb-108">An array with at least one element.</span></span>



## <a name="output--aa"></a><span data-ttu-id="28deb-109">Output： ( ' A，' A [] ) </span><span class="sxs-lookup"><span data-stu-id="28deb-109">Output : ('A,'A[])</span></span>

<span data-ttu-id="28deb-110">数组的第一个和所有剩余元素的元组。</span><span class="sxs-lookup"><span data-stu-id="28deb-110">A tuple of first and all remaining elements of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="28deb-111">类型参数</span><span class="sxs-lookup"><span data-stu-id="28deb-111">Type Parameters</span></span>

### <a name="a"></a><span data-ttu-id="28deb-112">' A</span><span class="sxs-lookup"><span data-stu-id="28deb-112">'A</span></span>

<span data-ttu-id="28deb-113">数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="28deb-113">The type of the array elements.</span></span>