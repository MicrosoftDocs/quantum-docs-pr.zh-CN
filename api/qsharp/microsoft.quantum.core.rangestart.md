---
uid: Microsoft.Quantum.Core.RangeStart
title: RangeStart 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStart
qsharp.summary: Returns the defined start value of the given range.
ms.openlocfilehash: 44683b204ecd469f5f5412a7ec06e98ec8a4f37e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96223997"
---
# <a name="rangestart-function"></a><span data-ttu-id="0be7b-102">RangeStart 函数</span><span class="sxs-lookup"><span data-stu-id="0be7b-102">RangeStart function</span></span>

<span data-ttu-id="0be7b-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="0be7b-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="0be7b-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="0be7b-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="0be7b-105">返回给定范围中定义的开始值。</span><span class="sxs-lookup"><span data-stu-id="0be7b-105">Returns the defined start value of the given range.</span></span>

```qsharp
function RangeStart (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="0be7b-106">输入</span><span class="sxs-lookup"><span data-stu-id="0be7b-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="0be7b-107">范围： [范围](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="0be7b-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="0be7b-108">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0be7b-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0be7b-109">给定范围的定义起始值。</span><span class="sxs-lookup"><span data-stu-id="0be7b-109">The defined start value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="0be7b-110">备注</span><span class="sxs-lookup"><span data-stu-id="0be7b-110">Remarks</span></span>

<span data-ttu-id="0be7b-111">范围表达式的第一个元素是 `start` ，其第二个元素是， `start+step` 第三个元素为 `start+step+step` ，依此类推，直到 `end` 传递。</span><span class="sxs-lookup"><span data-stu-id="0be7b-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>

<span data-ttu-id="0be7b-112">请注意，定义的范围的起始值与序列的第一个元素相同，除非该范围指定一个空序列 (例如 2.。</span><span class="sxs-lookup"><span data-stu-id="0be7b-112">Note that the defined start value of a range is the same as the first element of the sequence, unless the range specifies an empty sequence (for example, 2 ..</span></span> <span data-ttu-id="0be7b-113">1）。</span><span class="sxs-lookup"><span data-stu-id="0be7b-113">1).</span></span>