---
uid: Microsoft.Quantum.Logical.NotNearlyEqualD
title: NotNearlyEqualD 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotNearlyEqualD
qsharp.summary: Returns true if and only if two inputs are not nearly equal (that is, are not within a tolerance of 1e-12).
ms.openlocfilehash: d9e4cc5b0cfba3989ae64e494d0daa52069718a4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699736"
---
# <a name="notnearlyequald-function"></a><span data-ttu-id="f4177-102">NotNearlyEqualD 函数</span><span class="sxs-lookup"><span data-stu-id="f4177-102">NotNearlyEqualD function</span></span>

<span data-ttu-id="f4177-103">命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="f4177-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="f4177-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f4177-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f4177-105">当且仅当两个输入不 (相等时（即，不在 1e-12) 的容差内），将返回 true。</span><span class="sxs-lookup"><span data-stu-id="f4177-105">Returns true if and only if two inputs are not nearly equal (that is, are not within a tolerance of 1e-12).</span></span>

```qsharp
function NotNearlyEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="f4177-106">输入</span><span class="sxs-lookup"><span data-stu-id="f4177-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="f4177-107">答： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f4177-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f4177-108">要比较的第一个值。</span><span class="sxs-lookup"><span data-stu-id="f4177-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="f4177-109">b： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="f4177-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="f4177-110">要比较的第二个值。</span><span class="sxs-lookup"><span data-stu-id="f4177-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="f4177-111">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="f4177-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="f4177-112">`true` 当且仅当 `a` 不与几乎相等时 `b` 。</span><span class="sxs-lookup"><span data-stu-id="f4177-112">`true` if and only if `a` is not nearly equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="f4177-113">注解</span><span class="sxs-lookup"><span data-stu-id="f4177-113">Remarks</span></span>

<span data-ttu-id="f4177-114">以下项是等效的：</span><span class="sxs-lookup"><span data-stu-id="f4177-114">The following are equivalent:</span></span>

```Q#
let cond = Microsoft.Quantum.Math.AbsD(a - b) >= 1e-12;
let cond = NotNearlyEqualD(a, b);
```