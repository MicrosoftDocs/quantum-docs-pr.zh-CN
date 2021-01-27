---
uid: Microsoft.Quantum.Arrays.SquareArrayFact
title: SquareArrayFact 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SquareArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a square shape
ms.openlocfilehash: a154e5becba4dae762596a3fc1b268855520fa1b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850965"
---
# <a name="squarearrayfact-function"></a><span data-ttu-id="9579c-102">SquareArrayFact 函数</span><span class="sxs-lookup"><span data-stu-id="9579c-102">SquareArrayFact function</span></span>

<span data-ttu-id="9579c-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="9579c-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="9579c-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9579c-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9579c-105">表示二维数组具有正方形形状的条件</span><span class="sxs-lookup"><span data-stu-id="9579c-105">Represents a condition that a 2-dimensional array has a square shape</span></span>

```qsharp
function SquareArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a><span data-ttu-id="9579c-106">说明</span><span class="sxs-lookup"><span data-stu-id="9579c-106">Description</span></span>

<span data-ttu-id="9579c-107">此函数断言数组中的每行都有多个元素，因为数组中有行 (元素) 。</span><span class="sxs-lookup"><span data-stu-id="9579c-107">This function asserts that each row in an array has as many elements as there are rows (elements) in the array.</span></span>

## <a name="input"></a><span data-ttu-id="9579c-108">输入</span><span class="sxs-lookup"><span data-stu-id="9579c-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="9579c-109">array： t [] []</span><span class="sxs-lookup"><span data-stu-id="9579c-109">array : 'T[][]</span></span>

<span data-ttu-id="9579c-110">二维元素数组</span><span class="sxs-lookup"><span data-stu-id="9579c-110">A 2-dimensional array of elements</span></span>


### <a name="message--string"></a><span data-ttu-id="9579c-111">消息： [字符串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="9579c-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="9579c-112">如果数组不是正方形数组，则为要打印的消息</span><span class="sxs-lookup"><span data-stu-id="9579c-112">A message to be printed if the array is not a square array</span></span>



## <a name="output--unit"></a><span data-ttu-id="9579c-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="9579c-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="9579c-114">类型参数</span><span class="sxs-lookup"><span data-stu-id="9579c-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="9579c-115">找</span><span class="sxs-lookup"><span data-stu-id="9579c-115">'T</span></span>

<span data-ttu-id="9579c-116">的每个元素的类型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="9579c-116">The type of each element of `array`.</span></span>

## <a name="example"></a><span data-ttu-id="9579c-117">示例</span><span class="sxs-lookup"><span data-stu-id="9579c-117">Example</span></span>

```qsharp
SquareArrayFact([[1, 2], [3, 4]], "Array is not a square");       // okay
SquareArrayFact([[1, 2, 3], [4, 5, 6]], "Array is not a square"); // will fail
SquareArrayFact([[1, 2], [3, 4, 5]], "Array is not a square");    // will fail
```

## <a name="see-also"></a><span data-ttu-id="9579c-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9579c-118">See Also</span></span>

- [<span data-ttu-id="9579c-119">RectangularArrayFact。</span><span class="sxs-lookup"><span data-stu-id="9579c-119">Microsoft.Quantum.Arrays.RectangularArrayFact</span></span>](xref:Microsoft.Quantum.Arrays.RectangularArrayFact)