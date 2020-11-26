---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualD
title: GreaterThanOrEqualD 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualD
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: 0c9fa353b549d3c137beac3bcc3cfb0e742f6d07
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197800"
---
# <a name="greaterthanorequald-function"></a><span data-ttu-id="f3d41-102">GreaterThanOrEqualD 函数</span><span class="sxs-lookup"><span data-stu-id="f3d41-102">GreaterThanOrEqualD function</span></span>

<span data-ttu-id="f3d41-103">命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="f3d41-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="f3d41-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="f3d41-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="f3d41-105">当且仅当一个数字大于或等于另一个数字时，返回 true。</span><span class="sxs-lookup"><span data-stu-id="f3d41-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="f3d41-106">输入</span><span class="sxs-lookup"><span data-stu-id="f3d41-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="f3d41-107">答： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f3d41-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f3d41-108">要比较的第一个值。</span><span class="sxs-lookup"><span data-stu-id="f3d41-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="f3d41-109">b： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f3d41-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f3d41-110">要比较的第二个值。</span><span class="sxs-lookup"><span data-stu-id="f3d41-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="f3d41-111">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="f3d41-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f3d41-112">`true` 当且仅当 `a` 大于或等于时 `b` 。</span><span class="sxs-lookup"><span data-stu-id="f3d41-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="f3d41-113">备注</span><span class="sxs-lookup"><span data-stu-id="f3d41-113">Remarks</span></span>

<span data-ttu-id="f3d41-114">以下项是等效的：</span><span class="sxs-lookup"><span data-stu-id="f3d41-114">The following are equivalent:</span></span>

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualD(a, b);
```