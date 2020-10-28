---
uid: Microsoft.Quantum.Arrays.SquareArrayFact
title: SquareArrayFact 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SquareArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a square shape
ms.openlocfilehash: f7f0573db9098feebfd481624e11119c58fd9eed
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696453"
---
# <a name="squarearrayfact-function"></a><span data-ttu-id="fbaad-102">SquareArrayFact 函数</span><span class="sxs-lookup"><span data-stu-id="fbaad-102">SquareArrayFact function</span></span>

<span data-ttu-id="fbaad-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="fbaad-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="fbaad-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fbaad-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fbaad-105">表示二维数组具有正方形形状的条件</span><span class="sxs-lookup"><span data-stu-id="fbaad-105">Represents a condition that a 2-dimensional array has a square shape</span></span>

```qsharp
function SquareArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a><span data-ttu-id="fbaad-106">说明</span><span class="sxs-lookup"><span data-stu-id="fbaad-106">Description</span></span>

<span data-ttu-id="fbaad-107">此函数断言数组中的每行都有多个元素，因为数组中有行 (元素) 。</span><span class="sxs-lookup"><span data-stu-id="fbaad-107">This function asserts that each row in an array has as many elements as there are rows (elements) in the array.</span></span>

## <a name="input"></a><span data-ttu-id="fbaad-108">输入</span><span class="sxs-lookup"><span data-stu-id="fbaad-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="fbaad-109">array： t [] []</span><span class="sxs-lookup"><span data-stu-id="fbaad-109">array : 'T[][]</span></span>

<span data-ttu-id="fbaad-110">二维元素数组</span><span class="sxs-lookup"><span data-stu-id="fbaad-110">A 2-dimensional array of elements</span></span>


### <a name="message--string"></a><span data-ttu-id="fbaad-111">消息： [字符串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="fbaad-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="fbaad-112">如果数组不是正方形数组，则为要打印的消息</span><span class="sxs-lookup"><span data-stu-id="fbaad-112">A message to be printed if the array is not a square array</span></span>



## <a name="output--unit"></a><span data-ttu-id="fbaad-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fbaad-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="fbaad-114">类型参数</span><span class="sxs-lookup"><span data-stu-id="fbaad-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="fbaad-115">找</span><span class="sxs-lookup"><span data-stu-id="fbaad-115">'T</span></span>

<span data-ttu-id="fbaad-116">的每个元素的类型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="fbaad-116">The type of each element of `array`.</span></span>

## <a name="see-also"></a><span data-ttu-id="fbaad-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fbaad-117">See Also</span></span>

- [<span data-ttu-id="fbaad-118">RectangularArrayFact。</span><span class="sxs-lookup"><span data-stu-id="fbaad-118">Microsoft.Quantum.Arrays.RectangularArrayFact</span></span>](xref:Microsoft.Quantum.Arrays.RectangularArrayFact)