---
uid: Microsoft.Quantum.Logical.NotNearlyEqualD
title: NotNearlyEqualD 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotNearlyEqualD
qsharp.summary: Returns true if and only if two inputs are not nearly equal (that is, are not within a tolerance of 1e-12).
ms.openlocfilehash: 6e4cf3ec009f55ecc6345453c080520a3af6a8ef
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848493"
---
# <a name="notnearlyequald-function"></a><span data-ttu-id="7890d-102">NotNearlyEqualD 函数</span><span class="sxs-lookup"><span data-stu-id="7890d-102">NotNearlyEqualD function</span></span>

<span data-ttu-id="7890d-103">命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="7890d-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="7890d-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7890d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7890d-105">当且仅当两个输入不 (相等时（即，不在 1e-12) 的容差内），将返回 true。</span><span class="sxs-lookup"><span data-stu-id="7890d-105">Returns true if and only if two inputs are not nearly equal (that is, are not within a tolerance of 1e-12).</span></span>

```qsharp
function NotNearlyEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="7890d-106">输入</span><span class="sxs-lookup"><span data-stu-id="7890d-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="7890d-107">答： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7890d-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7890d-108">要比较的第一个值。</span><span class="sxs-lookup"><span data-stu-id="7890d-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="7890d-109">b： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="7890d-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="7890d-110">要比较的第二个值。</span><span class="sxs-lookup"><span data-stu-id="7890d-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="7890d-111">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="7890d-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="7890d-112">`true` 当且仅当 `a` 不与几乎相等时 `b` 。</span><span class="sxs-lookup"><span data-stu-id="7890d-112">`true` if and only if `a` is not nearly equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="7890d-113">备注</span><span class="sxs-lookup"><span data-stu-id="7890d-113">Remarks</span></span>

<span data-ttu-id="7890d-114">以下项是等效的：</span><span class="sxs-lookup"><span data-stu-id="7890d-114">The following are equivalent:</span></span>

```qsharp
let cond = Microsoft.Quantum.Math.AbsD(a - b) >= 1e-12;
let cond = NotNearlyEqualD(a, b);
```