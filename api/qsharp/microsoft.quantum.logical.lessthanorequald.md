---
uid: Microsoft.Quantum.Logical.LessThanOrEqualD
title: LessThanOrEqualD 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualD
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 7b0e9da379bd67eb78a80e7a535a15dcb8ba85c7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695165"
---
# <a name="lessthanorequald-function"></a><span data-ttu-id="0896f-102">LessThanOrEqualD 函数</span><span class="sxs-lookup"><span data-stu-id="0896f-102">LessThanOrEqualD function</span></span>

<span data-ttu-id="0896f-103">命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="0896f-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="0896f-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0896f-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0896f-105">当且仅当一个数字小于或等于另一个数字时，返回 true。</span><span class="sxs-lookup"><span data-stu-id="0896f-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="0896f-106">输入</span><span class="sxs-lookup"><span data-stu-id="0896f-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="0896f-107">答： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0896f-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0896f-108">要比较的第一个值。</span><span class="sxs-lookup"><span data-stu-id="0896f-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="0896f-109">b： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="0896f-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="0896f-110">要比较的第二个值。</span><span class="sxs-lookup"><span data-stu-id="0896f-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="0896f-111">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="0896f-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="0896f-112">`true` 当且仅当 `a` 小于或等于时 `b` 。</span><span class="sxs-lookup"><span data-stu-id="0896f-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="0896f-113">注解</span><span class="sxs-lookup"><span data-stu-id="0896f-113">Remarks</span></span>

<span data-ttu-id="0896f-114">以下项是等效的：</span><span class="sxs-lookup"><span data-stu-id="0896f-114">The following are equivalent:</span></span>

```Q#
let cond = a <= b;
let cond = LessThanOrEqualD(a, b);
```