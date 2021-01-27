---
uid: Microsoft.Quantum.Core.RangeStep
title: RangeStep 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeStep
qsharp.summary: Returns the integer that specifies how the next value of a range is calculated.
ms.openlocfilehash: 667b579337eec28d6b75de61668bd79de176883e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853595"
---
# <a name="rangestep-function"></a><span data-ttu-id="4f223-102">RangeStep 函数</span><span class="sxs-lookup"><span data-stu-id="4f223-102">RangeStep function</span></span>

<span data-ttu-id="4f223-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="4f223-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="4f223-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="4f223-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="4f223-105">返回一个整数，该整数指定如何计算范围的下一个值。</span><span class="sxs-lookup"><span data-stu-id="4f223-105">Returns the integer that specifies how the next value of a range is calculated.</span></span>

```qsharp
function RangeStep (range : Range) : Int
```


## <a name="input"></a><span data-ttu-id="4f223-106">输入</span><span class="sxs-lookup"><span data-stu-id="4f223-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="4f223-107">范围： [范围](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="4f223-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>





## <a name="output--int"></a><span data-ttu-id="4f223-108">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="4f223-108">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="4f223-109">给定范围的已定义步长值。</span><span class="sxs-lookup"><span data-stu-id="4f223-109">The defined step value of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="4f223-110">备注</span><span class="sxs-lookup"><span data-stu-id="4f223-110">Remarks</span></span>

<span data-ttu-id="4f223-111">范围表达式的第一个元素是 `start` ，其第二个元素是， `start+step` 第三个元素为 `start+step+step` ，依此类推，直到 `end` 传递。</span><span class="sxs-lookup"><span data-stu-id="4f223-111">A range expression's first element is `start`, its second element is `start+step`, third element is `start+step+step`, etc., until `end` is passed.</span></span>