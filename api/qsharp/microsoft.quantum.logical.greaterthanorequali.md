---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualI
title: GreaterThanOrEqualI 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualI
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: c1a513500c8a70bd7628976974387cba48162e80
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849186"
---
# <a name="greaterthanorequali-function"></a><span data-ttu-id="950f6-102">GreaterThanOrEqualI 函数</span><span class="sxs-lookup"><span data-stu-id="950f6-102">GreaterThanOrEqualI function</span></span>

<span data-ttu-id="950f6-103">命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="950f6-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="950f6-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="950f6-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="950f6-105">当且仅当一个数字大于或等于另一个数字时，返回 true。</span><span class="sxs-lookup"><span data-stu-id="950f6-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="950f6-106">输入</span><span class="sxs-lookup"><span data-stu-id="950f6-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="950f6-107">a： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="950f6-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="950f6-108">要比较的第一个值。</span><span class="sxs-lookup"><span data-stu-id="950f6-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="950f6-109">b： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="950f6-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="950f6-110">要比较的第二个值。</span><span class="sxs-lookup"><span data-stu-id="950f6-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="950f6-111">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="950f6-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="950f6-112">`true` 当且仅当 `a` 大于或等于时 `b` 。</span><span class="sxs-lookup"><span data-stu-id="950f6-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="950f6-113">备注</span><span class="sxs-lookup"><span data-stu-id="950f6-113">Remarks</span></span>

<span data-ttu-id="950f6-114">以下项是等效的：</span><span class="sxs-lookup"><span data-stu-id="950f6-114">The following are equivalent:</span></span>

```qsharp
let cond = a >= b;
let cond = GreaterThanOrEqualI(a, b);
```