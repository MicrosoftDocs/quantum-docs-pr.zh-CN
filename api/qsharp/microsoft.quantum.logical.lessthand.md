---
uid: Microsoft.Quantum.Logical.LessThanD
title: LessThanD 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanD
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 8cd274d5e299df2f556006baf7457d54aebcd071
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700572"
---
# <a name="lessthand-function"></a><span data-ttu-id="64cc8-102">LessThanD 函数</span><span class="sxs-lookup"><span data-stu-id="64cc8-102">LessThanD function</span></span>

<span data-ttu-id="64cc8-103">命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="64cc8-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="64cc8-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="64cc8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="64cc8-105">当且仅当一个数字小于另一个数字时，返回 true。</span><span class="sxs-lookup"><span data-stu-id="64cc8-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="64cc8-106">输入</span><span class="sxs-lookup"><span data-stu-id="64cc8-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="64cc8-107">答： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="64cc8-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="64cc8-108">要比较的第一个值。</span><span class="sxs-lookup"><span data-stu-id="64cc8-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="64cc8-109">b： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="64cc8-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="64cc8-110">要比较的第二个值。</span><span class="sxs-lookup"><span data-stu-id="64cc8-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="64cc8-111">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="64cc8-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="64cc8-112">`true` 当且仅当 `a` 严格小于时 `b` 。</span><span class="sxs-lookup"><span data-stu-id="64cc8-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="64cc8-113">注解</span><span class="sxs-lookup"><span data-stu-id="64cc8-113">Remarks</span></span>

<span data-ttu-id="64cc8-114">以下项是等效的：</span><span class="sxs-lookup"><span data-stu-id="64cc8-114">The following are equivalent:</span></span>

```Q#
let cond = a < b;
let cond = LessThanD(a, b);
```