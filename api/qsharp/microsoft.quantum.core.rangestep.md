---
uid: Microsoft.Quantum.Core.RangeStep
title: RangeStep 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStep
qsharp.summary: Returns the integer that specifies how the next value of a range is calculated.
ms.openlocfilehash: 39c8581fe795a1b76d2a6e81c238a271287c2c38
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213797"
---
# <a name="rangestep-function"></a><span data-ttu-id="74e55-102">RangeStep 函数</span><span class="sxs-lookup"><span data-stu-id="74e55-102">RangeStep function</span></span>

<span data-ttu-id="74e55-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="74e55-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="74e55-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="74e55-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="74e55-105">返回一个整数，该整数指定如何计算范围的下一个值。</span><span class="sxs-lookup"><span data-stu-id="74e55-105">Returns the integer that specifies how the next value of a range is calculated.</span></span>

```qsharp
function RangeStep (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="74e55-106">输入</span><span class="sxs-lookup"><span data-stu-id="74e55-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="74e55-107">范围： [范围](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="74e55-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="74e55-108">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="74e55-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="74e55-109">给定范围的已定义步长值。</span><span class="sxs-lookup"><span data-stu-id="74e55-109">The defined step value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="74e55-110">备注</span><span class="sxs-lookup"><span data-stu-id="74e55-110">Remarks</span></span>

<span data-ttu-id="74e55-111">范围表达式的第一个元素是 `start` ，其第二个元素是， `start+step` 第三个元素为 `start+step+step` ，依此类推，直到 `end` 传递。</span><span class="sxs-lookup"><span data-stu-id="74e55-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>