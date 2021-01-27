---
uid: Microsoft.Quantum.Arrays.Enumerated
title: 枚举函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Enumerated
qsharp.summary: Given an array, returns a new array containing elements of the original array along with the indices of each element.
ms.openlocfilehash: adb13d8b25c9e4a6011ade119ffa3cb2783f60e2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848126"
---
# <a name="enumerated-function"></a><span data-ttu-id="fa2b1-102">枚举函数</span><span class="sxs-lookup"><span data-stu-id="fa2b1-102">Enumerated function</span></span>

<span data-ttu-id="fa2b1-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="fa2b1-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="fa2b1-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fa2b1-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fa2b1-105">给定一个数组，返回一个新数组，其中包含原始数组的元素以及每个元素的索引。</span><span class="sxs-lookup"><span data-stu-id="fa2b1-105">Given an array, returns a new array containing elements of the original array along with the indices of each element.</span></span>

```qsharp
function Enumerated<'TElement> (array : 'TElement[]) : (Int, 'TElement)[]
```


## <a name="input"></a><span data-ttu-id="fa2b1-106">输入</span><span class="sxs-lookup"><span data-stu-id="fa2b1-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="fa2b1-107">array： ' TElement []</span><span class="sxs-lookup"><span data-stu-id="fa2b1-107">array : 'TElement[]</span></span>

<span data-ttu-id="fa2b1-108">要枚举其元素的数组。</span><span class="sxs-lookup"><span data-stu-id="fa2b1-108">An array whose elements are to be enumerated.</span></span>



## <a name="output--inttelement"></a><span data-ttu-id="fa2b1-109">Output： ([Int](xref:microsoft.quantum.lang-ref.int)，' TElement) []</span><span class="sxs-lookup"><span data-stu-id="fa2b1-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),'TElement)[]</span></span>

<span data-ttu-id="fa2b1-110">一个新数组，其中包含原始数组的元素及其索引。</span><span class="sxs-lookup"><span data-stu-id="fa2b1-110">A new array containing elements of the original array along with their indices.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="fa2b1-111">类型参数</span><span class="sxs-lookup"><span data-stu-id="fa2b1-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="fa2b1-112">' TElement</span><span class="sxs-lookup"><span data-stu-id="fa2b1-112">'TElement</span></span>

<span data-ttu-id="fa2b1-113">数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="fa2b1-113">The type of elements of the array.</span></span>

## <a name="example"></a><span data-ttu-id="fa2b1-114">示例</span><span class="sxs-lookup"><span data-stu-id="fa2b1-114">Example</span></span>

<span data-ttu-id="fa2b1-115">以下 `for` 循环是等效的：</span><span class="sxs-lookup"><span data-stu-id="fa2b1-115">The following `for` loops are equivalent:</span></span>

```qsharp
for (idx in IndexRange(array)) {
    let element = array[idx];
    ...
}
for ((idx, element) in Enumerated(array)) { ... }
```