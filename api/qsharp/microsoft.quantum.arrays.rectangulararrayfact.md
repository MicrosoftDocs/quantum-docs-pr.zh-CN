---
uid: Microsoft.Quantum.Arrays.RectangularArrayFact
title: RectangularArrayFact 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: RectangularArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a rectangular shape
ms.openlocfilehash: b8ef7d52f7f815ca3e21ded1236e775a381646cb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220410"
---
# <a name="rectangulararrayfact-function"></a><span data-ttu-id="16851-102">RectangularArrayFact 函数</span><span class="sxs-lookup"><span data-stu-id="16851-102">RectangularArrayFact function</span></span>

<span data-ttu-id="16851-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="16851-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="16851-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="16851-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="16851-105">表示二维数组具有矩形形状的条件</span><span class="sxs-lookup"><span data-stu-id="16851-105">Represents a condition that a 2-dimensional array has a rectangular shape</span></span>

```qsharp
function RectangularArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a><span data-ttu-id="16851-106">描述</span><span class="sxs-lookup"><span data-stu-id="16851-106">Description</span></span>

<span data-ttu-id="16851-107">此函数断言数组中的每一行都具有相同的长度。</span><span class="sxs-lookup"><span data-stu-id="16851-107">This function asserts that each row in an array has the same length.</span></span>

## <a name="input"></a><span data-ttu-id="16851-108">输入</span><span class="sxs-lookup"><span data-stu-id="16851-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="16851-109">array： t [] []</span><span class="sxs-lookup"><span data-stu-id="16851-109">array : 'T[][]</span></span>

<span data-ttu-id="16851-110">二维元素数组</span><span class="sxs-lookup"><span data-stu-id="16851-110">A 2-dimensional array of elements</span></span>


### <a name="message--string"></a><span data-ttu-id="16851-111">消息： [字符串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="16851-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="16851-112">如果数组不是矩形数组，则为要打印的消息</span><span class="sxs-lookup"><span data-stu-id="16851-112">A message to be printed if the array is not a rectangular array</span></span>



## <a name="output--unit"></a><span data-ttu-id="16851-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="16851-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="16851-114">类型参数</span><span class="sxs-lookup"><span data-stu-id="16851-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="16851-115">找</span><span class="sxs-lookup"><span data-stu-id="16851-115">'T</span></span>

<span data-ttu-id="16851-116">的每个元素的类型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="16851-116">The type of each element of `array`.</span></span>

## <a name="see-also"></a><span data-ttu-id="16851-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="16851-117">See Also</span></span>

- [<span data-ttu-id="16851-118">SquareArrayFact。</span><span class="sxs-lookup"><span data-stu-id="16851-118">Microsoft.Quantum.Arrays.SquareArrayFact</span></span>](xref:Microsoft.Quantum.Arrays.SquareArrayFact)