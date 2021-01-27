---
uid: Microsoft.Quantum.Core.RangeEnd
title: RangeEnd 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeEnd
qsharp.summary: Returns the defined end value of the given range, which is not necessarily the last element in the sequence.
ms.openlocfilehash: 196fab0bd97a441a16976033dc0d660c54cdfd6a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98831362"
---
# <a name="rangeend-function"></a><span data-ttu-id="39412-102">RangeEnd 函数</span><span class="sxs-lookup"><span data-stu-id="39412-102">RangeEnd function</span></span>

<span data-ttu-id="39412-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="39412-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="39412-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="39412-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="39412-105">返回给定范围的定义结束值，该范围不一定是序列中的最后一个元素。</span><span class="sxs-lookup"><span data-stu-id="39412-105">Returns the defined end value of the given range, which is not necessarily the last element in the sequence.</span></span>

```qsharp
function RangeEnd (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="39412-106">输入</span><span class="sxs-lookup"><span data-stu-id="39412-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="39412-107">范围： [范围](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="39412-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="39412-108">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="39412-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="39412-109">给定范围的定义结束值。</span><span class="sxs-lookup"><span data-stu-id="39412-109">The defined end value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="39412-110">备注</span><span class="sxs-lookup"><span data-stu-id="39412-110">Remarks</span></span>

<span data-ttu-id="39412-111">范围表达式的第一个元素是 `start` ，其第二个元素是， `start+step` 第三个元素为 `start+step+step` ，依此类推，直到 `end` 传递。</span><span class="sxs-lookup"><span data-stu-id="39412-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>

<span data-ttu-id="39412-112">请注意，范围的定义结束值可以与范围指定的序列中的最后一个元素不同;例如，在0到1的范围内。</span><span class="sxs-lookup"><span data-stu-id="39412-112">Note that the defined end value of a range can differ from the last element in the sequence specified by the range; for example, in a range 0 ..</span></span> <span data-ttu-id="39412-113">2.。</span><span class="sxs-lookup"><span data-stu-id="39412-113">2 ..</span></span> <span data-ttu-id="39412-114">5最后一个元素为4，但结束值为5。</span><span class="sxs-lookup"><span data-stu-id="39412-114">5 the last element is 4 but the end value is 5.</span></span>