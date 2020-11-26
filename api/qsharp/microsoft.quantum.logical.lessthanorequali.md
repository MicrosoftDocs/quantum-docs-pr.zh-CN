---
uid: Microsoft.Quantum.Logical.LessThanOrEqualI
title: LessThanOrEqualI 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualI
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: b2974c9bc84d0b4366767f47682ab542f85063e2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197560"
---
# <a name="lessthanorequali-function"></a><span data-ttu-id="5c667-102">LessThanOrEqualI 函数</span><span class="sxs-lookup"><span data-stu-id="5c667-102">LessThanOrEqualI function</span></span>

<span data-ttu-id="5c667-103">命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="5c667-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="5c667-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5c667-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5c667-105">当且仅当一个数字小于或等于另一个数字时，返回 true。</span><span class="sxs-lookup"><span data-stu-id="5c667-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="5c667-106">输入</span><span class="sxs-lookup"><span data-stu-id="5c667-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="5c667-107">a： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5c667-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5c667-108">要比较的第一个值。</span><span class="sxs-lookup"><span data-stu-id="5c667-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="5c667-109">b： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="5c667-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="5c667-110">要比较的第二个值。</span><span class="sxs-lookup"><span data-stu-id="5c667-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="5c667-111">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="5c667-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5c667-112">`true` 当且仅当 `a` 小于或等于时 `b` 。</span><span class="sxs-lookup"><span data-stu-id="5c667-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="5c667-113">备注</span><span class="sxs-lookup"><span data-stu-id="5c667-113">Remarks</span></span>

<span data-ttu-id="5c667-114">以下项是等效的：</span><span class="sxs-lookup"><span data-stu-id="5c667-114">The following are equivalent:</span></span>

```Q#
let cond = a <= b;
let cond = LessThanOrEqualI(a, b);
```