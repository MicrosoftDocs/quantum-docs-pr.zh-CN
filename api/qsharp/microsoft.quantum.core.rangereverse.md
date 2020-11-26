---
uid: Microsoft.Quantum.Core.RangeReverse
title: RangeReverse 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: 7bd7c55abe0b56b9d30b4c6e91f7175101dd2948
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213831"
---
# <a name="rangereverse-function"></a><span data-ttu-id="4f2cd-102">RangeReverse 函数</span><span class="sxs-lookup"><span data-stu-id="4f2cd-102">RangeReverse function</span></span>

<span data-ttu-id="4f2cd-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="4f2cd-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="4f2cd-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="4f2cd-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="4f2cd-105">返回一个新范围，该范围是输入范围的反向。</span><span class="sxs-lookup"><span data-stu-id="4f2cd-105">Returns a new range which is the reverse of the input range.</span></span>

```qsharp
function RangeReverse (r : Range) : Range
```


## <a name="input"></a><span data-ttu-id="4f2cd-106">输入</span><span class="sxs-lookup"><span data-stu-id="4f2cd-106">Input</span></span>

### <a name="r--range"></a><span data-ttu-id="4f2cd-107">r： [范围](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="4f2cd-107">r : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="4f2cd-108">输入范围。</span><span class="sxs-lookup"><span data-stu-id="4f2cd-108">Input range.</span></span>



## <a name="output--range"></a><span data-ttu-id="4f2cd-109">输出： [范围](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="4f2cd-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="4f2cd-110">与给定范围相反的新范围。</span><span class="sxs-lookup"><span data-stu-id="4f2cd-110">A new range that is the reverse of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="4f2cd-111">备注</span><span class="sxs-lookup"><span data-stu-id="4f2cd-111">Remarks</span></span>

<span data-ttu-id="4f2cd-112">请注意，范围的反向不只是 `end` ... `-step` `start` ，因为范围的实际最后一个元素可能与相同 `end` 。</span><span class="sxs-lookup"><span data-stu-id="4f2cd-112">Note that the reverse of a range is not simply `end`..`-step`..`start`, because the actual last element of a range may not be the same as `end`.</span></span>