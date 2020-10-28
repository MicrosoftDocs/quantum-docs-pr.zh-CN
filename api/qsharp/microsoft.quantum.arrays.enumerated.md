---
uid: Microsoft.Quantum.Arrays.Enumerated
title: 枚举函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: 0a591025a4eef79e08b47527c0bdb556f5645334
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696528"
---
# <a name="enumerated-function"></a><span data-ttu-id="77bc3-102">枚举函数</span><span class="sxs-lookup"><span data-stu-id="77bc3-102">Enumerated function</span></span>

<span data-ttu-id="77bc3-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="77bc3-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="77bc3-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="77bc3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="77bc3-105">给定一个数组，返回一个新数组，其中包含原始数组的元素以及每个元素的索引。</span><span class="sxs-lookup"><span data-stu-id="77bc3-105">Given an array, returns a new array containing elements of the original array along with the indices of each element.</span></span>

```qsharp
function Enumerated<'TElement> (array : 'TElement[]) : (Int, 'TElement)[]
```


## <a name="input"></a><span data-ttu-id="77bc3-106">输入</span><span class="sxs-lookup"><span data-stu-id="77bc3-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="77bc3-107">array： ' TElement []</span><span class="sxs-lookup"><span data-stu-id="77bc3-107">array : 'TElement[]</span></span>

<span data-ttu-id="77bc3-108">要枚举其元素的数组。</span><span class="sxs-lookup"><span data-stu-id="77bc3-108">An array whose elements are to be enumerated.</span></span>



## <a name="output--inttelement"></a><span data-ttu-id="77bc3-109">Output： ([Int](xref:microsoft.quantum.lang-ref.int)，' TElement) []</span><span class="sxs-lookup"><span data-stu-id="77bc3-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),'TElement)[]</span></span>

<span data-ttu-id="77bc3-110">一个新数组，其中包含原始数组的元素及其索引。</span><span class="sxs-lookup"><span data-stu-id="77bc3-110">A new array containing elements of the original array along with their indices.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="77bc3-111">类型参数</span><span class="sxs-lookup"><span data-stu-id="77bc3-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="77bc3-112">' TElement</span><span class="sxs-lookup"><span data-stu-id="77bc3-112">'TElement</span></span>

<span data-ttu-id="77bc3-113">数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="77bc3-113">The type of elements of the array.</span></span>