---
uid: Microsoft.Quantum.Arrays.IndexRange
title: IndexRange 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 5afd4cc260ac3e384d2736bf7b43d941afd9ef73
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220937"
---
# <a name="indexrange-function"></a><span data-ttu-id="d0eaf-102">IndexRange 函数</span><span class="sxs-lookup"><span data-stu-id="d0eaf-102">IndexRange function</span></span>

<span data-ttu-id="d0eaf-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="d0eaf-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="d0eaf-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="d0eaf-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="d0eaf-105">给定一个数组，返回该数组的索引范围，该范围适用于在 for 循环中使用。</span><span class="sxs-lookup"><span data-stu-id="d0eaf-105">Given an array, returns a range over the indices of that array, suitable for use in a for loop.</span></span>

```qsharp
function IndexRange<'TElement> (array : 'TElement[]) : Range
```


## <a name="input"></a><span data-ttu-id="d0eaf-106">输入</span><span class="sxs-lookup"><span data-stu-id="d0eaf-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="d0eaf-107">array： ' TElement []</span><span class="sxs-lookup"><span data-stu-id="d0eaf-107">array : 'TElement[]</span></span>

<span data-ttu-id="d0eaf-108">应为其返回索引范围的数组。</span><span class="sxs-lookup"><span data-stu-id="d0eaf-108">An array for which a range of indices should be returned.</span></span>



## <a name="output--range"></a><span data-ttu-id="d0eaf-109">输出： [范围](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="d0eaf-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="d0eaf-110">数组的所有索引范围。</span><span class="sxs-lookup"><span data-stu-id="d0eaf-110">A range over all indices of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="d0eaf-111">类型参数</span><span class="sxs-lookup"><span data-stu-id="d0eaf-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="d0eaf-112">' TElement</span><span class="sxs-lookup"><span data-stu-id="d0eaf-112">'TElement</span></span>

<span data-ttu-id="d0eaf-113">数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="d0eaf-113">The type of elements of the array.</span></span>