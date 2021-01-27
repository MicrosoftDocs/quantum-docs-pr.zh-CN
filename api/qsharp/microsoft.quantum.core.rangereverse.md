---
uid: Microsoft.Quantum.Core.RangeReverse
title: RangeReverse 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: RangeReverse
qsharp.summary: Returns a new range which is the reverse of the input range.
ms.openlocfilehash: f3b94d3c6fa6350a2c337f8bc8d889d24d87a85b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853659"
---
# <a name="rangereverse-function"></a><span data-ttu-id="30b2e-102">RangeReverse 函数</span><span class="sxs-lookup"><span data-stu-id="30b2e-102">RangeReverse function</span></span>

<span data-ttu-id="30b2e-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="30b2e-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="30b2e-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="30b2e-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="30b2e-105">返回一个新范围，该范围是输入范围的反向。</span><span class="sxs-lookup"><span data-stu-id="30b2e-105">Returns a new range which is the reverse of the input range.</span></span>

```qsharp
function RangeReverse (r : Range) : Range
```


## <a name="input"></a><span data-ttu-id="30b2e-106">输入</span><span class="sxs-lookup"><span data-stu-id="30b2e-106">Input</span></span>

### <a name="r--range"></a><span data-ttu-id="30b2e-107">r： [范围](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="30b2e-107">r : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="30b2e-108">输入范围。</span><span class="sxs-lookup"><span data-stu-id="30b2e-108">Input range.</span></span>



## <a name="output--range"></a><span data-ttu-id="30b2e-109">输出： [范围](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="30b2e-109">Output : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="30b2e-110">与给定范围相反的新范围。</span><span class="sxs-lookup"><span data-stu-id="30b2e-110">A new range that is the reverse of the given range.</span></span>

## <a name="remarks"></a><span data-ttu-id="30b2e-111">备注</span><span class="sxs-lookup"><span data-stu-id="30b2e-111">Remarks</span></span>

<span data-ttu-id="30b2e-112">请注意，范围的反向不只是 `end` ... `-step` `start` ，因为范围的实际最后一个元素可能与相同 `end` 。</span><span class="sxs-lookup"><span data-stu-id="30b2e-112">Note that the reverse of a range is not simply `end`..`-step`..`start`, because the actual last element of a range may not be the same as `end`.</span></span>