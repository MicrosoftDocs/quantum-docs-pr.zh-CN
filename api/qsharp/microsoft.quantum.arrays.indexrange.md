---
uid: Microsoft.Quantum.Arrays.IndexRange
title: IndexRange 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 7f9779acd4a781c50388217aa780710bd0b99ff3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696502"
---
# <a name="indexrange-function"></a><span data-ttu-id="a3add-102">IndexRange 函数</span><span class="sxs-lookup"><span data-stu-id="a3add-102">IndexRange function</span></span>

<span data-ttu-id="a3add-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="a3add-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="a3add-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a3add-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a3add-105">给定一个数组，返回该数组的索引范围，该范围适用于在 for 循环中使用。</span><span class="sxs-lookup"><span data-stu-id="a3add-105">Given an array, returns a range over the indices of that array, suitable for use in a for loop.</span></span>

```qsharp
function IndexRange<'TElement> (array : 'TElement[]) : Range
```


## <a name="input"></a><span data-ttu-id="a3add-106">输入</span><span class="sxs-lookup"><span data-stu-id="a3add-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="a3add-107">array： ' TElement []</span><span class="sxs-lookup"><span data-stu-id="a3add-107">array : 'TElement[]</span></span>

<span data-ttu-id="a3add-108">应为其返回索引范围的数组。</span><span class="sxs-lookup"><span data-stu-id="a3add-108">An array for which a range of indices should be returned.</span></span>



## <a name="output--range"></a><span data-ttu-id="a3add-109">输出： [范围](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="a3add-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="a3add-110">数组的所有索引范围。</span><span class="sxs-lookup"><span data-stu-id="a3add-110">A range over all indices of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="a3add-111">类型参数</span><span class="sxs-lookup"><span data-stu-id="a3add-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="a3add-112">' TElement</span><span class="sxs-lookup"><span data-stu-id="a3add-112">'TElement</span></span>

<span data-ttu-id="a3add-113">数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="a3add-113">The type of elements of the array.</span></span>