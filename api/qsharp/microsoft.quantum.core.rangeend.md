---
uid: Microsoft.Quantum.Core.RangeEnd
title: RangeEnd 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeEnd
qsharp.summary: Returns the defined end value of the given range, which is not necessarily the last element in the sequence.
ms.openlocfilehash: 4dbcf517c4dc17775040444c77deb0e449082390
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695636"
---
# <a name="rangeend-function"></a><span data-ttu-id="bde2e-102">RangeEnd 函数</span><span class="sxs-lookup"><span data-stu-id="bde2e-102">RangeEnd function</span></span>

<span data-ttu-id="bde2e-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="bde2e-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="bde2e-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bde2e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bde2e-105">返回给定范围的定义结束值，该范围不一定是序列中的最后一个元素。</span><span class="sxs-lookup"><span data-stu-id="bde2e-105">Returns the defined end value of the given range, which is not necessarily the last element in the sequence.</span></span>

```qsharp
function RangeEnd (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="bde2e-106">输入</span><span class="sxs-lookup"><span data-stu-id="bde2e-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="bde2e-107">范围： [范围](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="bde2e-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="bde2e-108">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="bde2e-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="bde2e-109">给定范围的定义结束值。</span><span class="sxs-lookup"><span data-stu-id="bde2e-109">The defined end value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="bde2e-110">注解</span><span class="sxs-lookup"><span data-stu-id="bde2e-110">Remarks</span></span>

<span data-ttu-id="bde2e-111">范围表达式的第一个元素是 `start` ，其第二个元素是， `start+step` 第三个元素为 `start+step+step` ，依此类推，直到 `end` 传递。</span><span class="sxs-lookup"><span data-stu-id="bde2e-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>

<span data-ttu-id="bde2e-112">请注意，范围的定义结束值可以与范围指定的序列中的最后一个元素不同;例如，在0到1的范围内。</span><span class="sxs-lookup"><span data-stu-id="bde2e-112">Note that the defined end value of a range can differ from the last element in the sequence specified by the range; for example, in a range 0 ..</span></span> <span data-ttu-id="bde2e-113">2.。</span><span class="sxs-lookup"><span data-stu-id="bde2e-113">2 ..</span></span> <span data-ttu-id="bde2e-114">5最后一个元素为4，但结束值为5。</span><span class="sxs-lookup"><span data-stu-id="bde2e-114">5 the last element is 4 but the end value is 5.</span></span>