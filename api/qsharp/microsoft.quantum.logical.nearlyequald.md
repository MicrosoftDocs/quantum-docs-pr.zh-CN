---
uid: Microsoft.Quantum.Logical.NearlyEqualD
title: NearlyEqualD 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NearlyEqualD
qsharp.summary: Returns true if and only if two inputs are nearly equal (that is, within a tolerance of 1e-12).
ms.openlocfilehash: 332f9ea1753b539eba7b931d5b948b2a238d1abf
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695154"
---
# <a name="nearlyequald-function"></a><span data-ttu-id="59a8e-102">NearlyEqualD 函数</span><span class="sxs-lookup"><span data-stu-id="59a8e-102">NearlyEqualD function</span></span>

<span data-ttu-id="59a8e-103">命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="59a8e-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="59a8e-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="59a8e-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="59a8e-105">当且仅当两个输入几乎相等 (即在 1e-12) 的容错范围内时，返回 true。</span><span class="sxs-lookup"><span data-stu-id="59a8e-105">Returns true if and only if two inputs are nearly equal (that is, within a tolerance of 1e-12).</span></span>

```qsharp
function NearlyEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="59a8e-106">输入</span><span class="sxs-lookup"><span data-stu-id="59a8e-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="59a8e-107">答： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="59a8e-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="59a8e-108">要比较的第一个值。</span><span class="sxs-lookup"><span data-stu-id="59a8e-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="59a8e-109">b： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="59a8e-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="59a8e-110">要比较的第二个值。</span><span class="sxs-lookup"><span data-stu-id="59a8e-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="59a8e-111">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="59a8e-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="59a8e-112">`true` 当且仅当 `a` 约等于时 `b` 。</span><span class="sxs-lookup"><span data-stu-id="59a8e-112">`true` if and only if `a` is nearly equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="59a8e-113">注解</span><span class="sxs-lookup"><span data-stu-id="59a8e-113">Remarks</span></span>

<span data-ttu-id="59a8e-114">以下项是等效的：</span><span class="sxs-lookup"><span data-stu-id="59a8e-114">The following are equivalent:</span></span>

```Q#
let cond = Microsoft.Quantum.Math.AbsD(a - b) < 1e-12;
let cond = NearlyEqualD(a, b);
```