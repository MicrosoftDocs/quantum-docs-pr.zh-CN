---
uid: Microsoft.Quantum.Core.RangeStart
title: RangeStart 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStart
qsharp.summary: Returns the defined start value of the given range.
ms.openlocfilehash: 3e4b0cebe34b4c98cb1d582a9cd11b46ff778517
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695625"
---
# <a name="rangestart-function"></a><span data-ttu-id="8678e-102">RangeStart 函数</span><span class="sxs-lookup"><span data-stu-id="8678e-102">RangeStart function</span></span>

<span data-ttu-id="8678e-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="8678e-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="8678e-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="8678e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="8678e-105">返回给定范围中定义的开始值。</span><span class="sxs-lookup"><span data-stu-id="8678e-105">Returns the defined start value of the given range.</span></span>

```qsharp
function RangeStart (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="8678e-106">输入</span><span class="sxs-lookup"><span data-stu-id="8678e-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="8678e-107">范围： [范围](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="8678e-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="8678e-108">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="8678e-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="8678e-109">给定范围的定义起始值。</span><span class="sxs-lookup"><span data-stu-id="8678e-109">The defined start value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="8678e-110">注解</span><span class="sxs-lookup"><span data-stu-id="8678e-110">Remarks</span></span>

<span data-ttu-id="8678e-111">范围表达式的第一个元素是 `start` ，其第二个元素是， `start+step` 第三个元素为 `start+step+step` ，依此类推，直到 `end` 传递。</span><span class="sxs-lookup"><span data-stu-id="8678e-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>

<span data-ttu-id="8678e-112">请注意，定义的范围的起始值与序列的第一个元素相同，除非该范围指定一个空序列 (例如 2.。</span><span class="sxs-lookup"><span data-stu-id="8678e-112">Note that the defined start value of a range is the same as the first element of the sequence, unless the range specifies an empty sequence (for example, 2 ..</span></span> <span data-ttu-id="8678e-113">1）。</span><span class="sxs-lookup"><span data-stu-id="8678e-113">1).</span></span>