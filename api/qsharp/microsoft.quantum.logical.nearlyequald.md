---
uid: Microsoft.Quantum.Logical.NearlyEqualD
title: NearlyEqualD 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NearlyEqualD
qsharp.summary: Returns true if and only if two inputs are nearly equal (that is, within a tolerance of 1e-12).
ms.openlocfilehash: 246fad15c691a53fcc5be10f2c713672e0b54e6b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197460"
---
# <a name="nearlyequald-function"></a><span data-ttu-id="268c7-102">NearlyEqualD 函数</span><span class="sxs-lookup"><span data-stu-id="268c7-102">NearlyEqualD function</span></span>

<span data-ttu-id="268c7-103">命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="268c7-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="268c7-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="268c7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="268c7-105">当且仅当两个输入几乎相等 (即在 1e-12) 的容错范围内时，返回 true。</span><span class="sxs-lookup"><span data-stu-id="268c7-105">Returns true if and only if two inputs are nearly equal (that is, within a tolerance of 1e-12).</span></span>

```qsharp
function NearlyEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="268c7-106">输入</span><span class="sxs-lookup"><span data-stu-id="268c7-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="268c7-107">答： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="268c7-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="268c7-108">要比较的第一个值。</span><span class="sxs-lookup"><span data-stu-id="268c7-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="268c7-109">b： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="268c7-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="268c7-110">要比较的第二个值。</span><span class="sxs-lookup"><span data-stu-id="268c7-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="268c7-111">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="268c7-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="268c7-112">`true` 当且仅当 `a` 约等于时 `b` 。</span><span class="sxs-lookup"><span data-stu-id="268c7-112">`true` if and only if `a` is nearly equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="268c7-113">备注</span><span class="sxs-lookup"><span data-stu-id="268c7-113">Remarks</span></span>

<span data-ttu-id="268c7-114">以下项是等效的：</span><span class="sxs-lookup"><span data-stu-id="268c7-114">The following are equivalent:</span></span>

```Q#
let cond = Microsoft.Quantum.Math.AbsD(a - b) < 1e-12;
let cond = NearlyEqualD(a, b);
```