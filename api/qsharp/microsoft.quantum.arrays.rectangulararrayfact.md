---
uid: Microsoft.Quantum.Arrays.RectangularArrayFact
title: RectangularArrayFact 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: RectangularArrayFact
qsharp.summary: Represents a condition that a 2-dimensional array has a rectangular shape
ms.openlocfilehash: f0d3f4d6bfa9e86f1c7a91792c09e16fe86433a0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696464"
---
# <a name="rectangulararrayfact-function"></a><span data-ttu-id="15f96-102">RectangularArrayFact 函数</span><span class="sxs-lookup"><span data-stu-id="15f96-102">RectangularArrayFact function</span></span>

<span data-ttu-id="15f96-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="15f96-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="15f96-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="15f96-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="15f96-105">表示二维数组具有矩形形状的条件</span><span class="sxs-lookup"><span data-stu-id="15f96-105">Represents a condition that a 2-dimensional array has a rectangular shape</span></span>

```qsharp
function RectangularArrayFact<'T> (array : 'T[][], message : String) : Unit
```


## <a name="description"></a><span data-ttu-id="15f96-106">说明</span><span class="sxs-lookup"><span data-stu-id="15f96-106">Description</span></span>

<span data-ttu-id="15f96-107">此函数断言数组中的每一行都具有相同的长度。</span><span class="sxs-lookup"><span data-stu-id="15f96-107">This function asserts that each row in an array has the same length.</span></span>

## <a name="input"></a><span data-ttu-id="15f96-108">输入</span><span class="sxs-lookup"><span data-stu-id="15f96-108">Input</span></span>

### <a name="array--t"></a><span data-ttu-id="15f96-109">array： t [] []</span><span class="sxs-lookup"><span data-stu-id="15f96-109">array : 'T[][]</span></span>

<span data-ttu-id="15f96-110">二维元素数组</span><span class="sxs-lookup"><span data-stu-id="15f96-110">A 2-dimensional array of elements</span></span>


### <a name="message--string"></a><span data-ttu-id="15f96-111">消息： [字符串](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="15f96-111">message : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="15f96-112">如果数组不是矩形数组，则为要打印的消息</span><span class="sxs-lookup"><span data-stu-id="15f96-112">A message to be printed if the array is not a rectangular array</span></span>



## <a name="output--unit"></a><span data-ttu-id="15f96-113">输出： [单元](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="15f96-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="15f96-114">类型参数</span><span class="sxs-lookup"><span data-stu-id="15f96-114">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="15f96-115">找</span><span class="sxs-lookup"><span data-stu-id="15f96-115">'T</span></span>

<span data-ttu-id="15f96-116">的每个元素的类型 `array` 。</span><span class="sxs-lookup"><span data-stu-id="15f96-116">The type of each element of `array`.</span></span>

## <a name="see-also"></a><span data-ttu-id="15f96-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="15f96-117">See Also</span></span>

- [<span data-ttu-id="15f96-118">SquareArrayFact。</span><span class="sxs-lookup"><span data-stu-id="15f96-118">Microsoft.Quantum.Arrays.SquareArrayFact</span></span>](xref:Microsoft.Quantum.Arrays.SquareArrayFact)