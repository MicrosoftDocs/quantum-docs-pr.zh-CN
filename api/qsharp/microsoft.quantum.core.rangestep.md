---
uid: Microsoft.Quantum.Core.RangeStep
title: RangeStep 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStep
qsharp.summary: Returns the integer that specifies how the next value of a range is calculated.
ms.openlocfilehash: f8e4c42330f2d6afdc1c0a9bdde36081ccab2f94
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695624"
---
# <a name="rangestep-function"></a><span data-ttu-id="a3fdc-102">RangeStep 函数</span><span class="sxs-lookup"><span data-stu-id="a3fdc-102">RangeStep function</span></span>

<span data-ttu-id="a3fdc-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="a3fdc-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="a3fdc-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a3fdc-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a3fdc-105">返回一个整数，该整数指定如何计算范围的下一个值。</span><span class="sxs-lookup"><span data-stu-id="a3fdc-105">Returns the integer that specifies how the next value of a range is calculated.</span></span>

```qsharp
function RangeStep (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="a3fdc-106">输入</span><span class="sxs-lookup"><span data-stu-id="a3fdc-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="a3fdc-107">范围： [范围](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="a3fdc-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="a3fdc-108">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a3fdc-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a3fdc-109">给定范围的已定义步长值。</span><span class="sxs-lookup"><span data-stu-id="a3fdc-109">The defined step value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="a3fdc-110">注解</span><span class="sxs-lookup"><span data-stu-id="a3fdc-110">Remarks</span></span>

<span data-ttu-id="a3fdc-111">范围表达式的第一个元素是 `start` ，其第二个元素是， `start+step` 第三个元素为 `start+step+step` ，依此类推，直到 `end` 传递。</span><span class="sxs-lookup"><span data-stu-id="a3fdc-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>