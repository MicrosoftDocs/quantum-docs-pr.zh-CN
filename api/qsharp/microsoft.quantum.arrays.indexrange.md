---
uid: Microsoft.Quantum.Arrays.IndexRange
title: IndexRange 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: IndexRange
qsharp.summary: Given an array, returns a range over the indices of that array, suitable for use in a for loop.
ms.openlocfilehash: 043b56a1ac3cbe5cd59cdd45d3725f301d81a6ee
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845782"
---
# <a name="indexrange-function"></a><span data-ttu-id="9bd61-102">IndexRange 函数</span><span class="sxs-lookup"><span data-stu-id="9bd61-102">IndexRange function</span></span>

<span data-ttu-id="9bd61-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="9bd61-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="9bd61-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="9bd61-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="9bd61-105">给定一个数组，返回该数组的索引范围，该范围适用于在 for 循环中使用。</span><span class="sxs-lookup"><span data-stu-id="9bd61-105">Given an array, returns a range over the indices of that array, suitable for use in a for loop.</span></span>

```qsharp
function IndexRange<'TElement> (array : 'TElement[]) : Range
```


## <a name="input"></a><span data-ttu-id="9bd61-106">输入</span><span class="sxs-lookup"><span data-stu-id="9bd61-106">Input</span></span>

### <a name="array--telement"></a><span data-ttu-id="9bd61-107">array： ' TElement []</span><span class="sxs-lookup"><span data-stu-id="9bd61-107">array : 'TElement[]</span></span>

<span data-ttu-id="9bd61-108">应为其返回索引范围的数组。</span><span class="sxs-lookup"><span data-stu-id="9bd61-108">An array for which a range of indices should be returned.</span></span>



## <a name="output--range"></a><span data-ttu-id="9bd61-109">输出： [范围](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="9bd61-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="9bd61-110">数组的所有索引范围。</span><span class="sxs-lookup"><span data-stu-id="9bd61-110">A range over all indices of the array.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="9bd61-111">类型参数</span><span class="sxs-lookup"><span data-stu-id="9bd61-111">Type Parameters</span></span>

### <a name="telement"></a><span data-ttu-id="9bd61-112">' TElement</span><span class="sxs-lookup"><span data-stu-id="9bd61-112">'TElement</span></span>

<span data-ttu-id="9bd61-113">数组元素的类型。</span><span class="sxs-lookup"><span data-stu-id="9bd61-113">The type of elements of the array.</span></span>

## <a name="example"></a><span data-ttu-id="9bd61-114">示例</span><span class="sxs-lookup"><span data-stu-id="9bd61-114">Example</span></span>

<span data-ttu-id="9bd61-115">以下 `for` 循环是等效的：</span><span class="sxs-lookup"><span data-stu-id="9bd61-115">The following `for` loops are equivalent:</span></span>

```qsharp
for (idx in IndexRange(array)) { ... }
for (idx in IndexRange(array)) { ... }
```