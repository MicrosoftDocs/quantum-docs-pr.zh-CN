---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualL
title: GreaterThanOrEqualL 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualL
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: 5536c009d6e78eac9ab2320b42aec7d2d82946eb
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197749"
---
# <a name="greaterthanorequall-function"></a><span data-ttu-id="e7b6b-102">GreaterThanOrEqualL 函数</span><span class="sxs-lookup"><span data-stu-id="e7b6b-102">GreaterThanOrEqualL function</span></span>

<span data-ttu-id="e7b6b-103">命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="e7b6b-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="e7b6b-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e7b6b-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e7b6b-105">当且仅当一个数字大于或等于另一个数字时，返回 true。</span><span class="sxs-lookup"><span data-stu-id="e7b6b-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="e7b6b-106">输入</span><span class="sxs-lookup"><span data-stu-id="e7b6b-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="e7b6b-107">a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="e7b6b-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="e7b6b-108">要比较的第一个值。</span><span class="sxs-lookup"><span data-stu-id="e7b6b-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="e7b6b-109">b： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="e7b6b-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="e7b6b-110">要比较的第二个值。</span><span class="sxs-lookup"><span data-stu-id="e7b6b-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="e7b6b-111">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="e7b6b-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="e7b6b-112">`true` 当且仅当 `a` 大于或等于时 `b` 。</span><span class="sxs-lookup"><span data-stu-id="e7b6b-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="e7b6b-113">备注</span><span class="sxs-lookup"><span data-stu-id="e7b6b-113">Remarks</span></span>

<span data-ttu-id="e7b6b-114">以下项是等效的：</span><span class="sxs-lookup"><span data-stu-id="e7b6b-114">The following are equivalent:</span></span>

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualL(a, b);
```