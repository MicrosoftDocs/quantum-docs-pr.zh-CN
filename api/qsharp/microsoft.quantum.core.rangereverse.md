---
uid: Microsoft.Quantum.Core.RangeReverse
title: RangeReverse 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: d4e612d2f175015b7193634aeec12f9df12df7d3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695634"
---
# <a name="rangereverse-function"></a><span data-ttu-id="87c15-102">RangeReverse 函数</span><span class="sxs-lookup"><span data-stu-id="87c15-102">RangeReverse function</span></span>

<span data-ttu-id="87c15-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="87c15-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="87c15-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="87c15-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="87c15-105">返回一个新范围，该范围是输入范围的反向。</span><span class="sxs-lookup"><span data-stu-id="87c15-105">Returns a new range which is the reverse of the input range.</span></span>

```qsharp
function RangeReverse (r : Range) : Range
```


## <a name="input"></a><span data-ttu-id="87c15-106">输入</span><span class="sxs-lookup"><span data-stu-id="87c15-106">Input</span></span>

### <a name="r--range"></a><span data-ttu-id="87c15-107">r： [范围](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="87c15-107">r : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="87c15-108">输入范围。</span><span class="sxs-lookup"><span data-stu-id="87c15-108">Input range.</span></span>



## <a name="output--range"></a><span data-ttu-id="87c15-109">输出： [范围](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="87c15-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="87c15-110">与给定范围相反的新范围。</span><span class="sxs-lookup"><span data-stu-id="87c15-110">A new range that is the reverse of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="87c15-111">注解</span><span class="sxs-lookup"><span data-stu-id="87c15-111">Remarks</span></span>

<span data-ttu-id="87c15-112">请注意，范围的反向不只是 `end` ... `-step` `start` ，因为范围的实际最后一个元素可能与相同 `end` 。</span><span class="sxs-lookup"><span data-stu-id="87c15-112">Note that the reverse of a range is not simply `end`..`-step`..`start`, because the actual last element of a range may not be the same as `end`.</span></span>