---
uid: Microsoft.Quantum.Arrays.Enumerated
title: 枚举函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: 94e8fdb7288bc43ed84d10a3292819b455a2be31
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96221413"
---
# <a name="enumerated-function"></a><span data-ttu-id="41ed3-102">枚举函数</span><span class="sxs-lookup"><span data-stu-id="41ed3-102">Enumerated function</span></span>

<span data-ttu-id="41ed3-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="41ed3-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="41ed3-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="41ed3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="41ed3-105">给定一个数组，返回一个新数组，其中包含原始数组的元素以及每个元素的索引。</span><span class="sxs-lookup"><span data-stu-id="41ed3-105">Given an array, returns a new array containing elements of the original array along with the indices of each element.</span></span>

```qsharp
function Enumerated<'TElement> (array : 'TElement[]) : (Int, 'TElement)[]
```


## <a name="input"></a><span data-ttu-id="41ed3-106">输入</span><span class="sxs-lookup"><span data-stu-id="41ed3-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="41ed3-107">array： ' TElement []</span><span class="sxs-lookup"><span data-stu-id="41ed3-107">array : 'TElement[]</span></span>

<span data-ttu-id="41ed3-108">要枚举其元素的数组。</span><span class="sxs-lookup"><span data-stu-id="41ed3-108">An array whose elements are to be enumerated.</span></span>



## <a name="output--inttelement"></a><span data-ttu-id="41ed3-109">Output： ([Int](xref:microsoft.quantum.lang-ref.int)，' TElement) []</span><span class="sxs-lookup"><span data-stu-id="41ed3-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),'TElement)[]</span></span>

<span data-ttu-id="41ed3-110">一个新数组，其中包含原始数组的元素及其索引。</span><span class="sxs-lookup"><span data-stu-id="41ed3-110">A new array containing elements of the original array along with their indices.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="41ed3-111">类型参数</span><span class="sxs-lookup"><span data-stu-id="41ed3-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="41ed3-112">' TElement</span><span class="sxs-lookup"><span data-stu-id="41ed3-112">'TElement</span></span>

<span data-ttu-id="41ed3-113">数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="41ed3-113">The type of elements of the array.</span></span>