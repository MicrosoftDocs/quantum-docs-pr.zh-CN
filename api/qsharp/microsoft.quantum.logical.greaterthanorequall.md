---
uid: Microsoft.Quantum.Logical.GreaterThanOrEqualL
title: GreaterThanOrEqualL 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanOrEqualL
qsharp.summary: Returns true if and only if a number is greater than or equal to another number.
ms.openlocfilehash: a59a9eca2941a44a70ec5a379b146ac459390bd4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700329"
---
# <a name="greaterthanorequall-function"></a><span data-ttu-id="93022-102">GreaterThanOrEqualL 函数</span><span class="sxs-lookup"><span data-stu-id="93022-102">GreaterThanOrEqualL function</span></span>

<span data-ttu-id="93022-103">命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="93022-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="93022-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="93022-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="93022-105">当且仅当一个数字大于或等于另一个数字时，返回 true。</span><span class="sxs-lookup"><span data-stu-id="93022-105">Returns true if and only if a number is greater than or equal to another number.</span></span>

```qsharp
function GreaterThanOrEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="93022-106">输入</span><span class="sxs-lookup"><span data-stu-id="93022-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="93022-107">a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="93022-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="93022-108">要比较的第一个值。</span><span class="sxs-lookup"><span data-stu-id="93022-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="93022-109">b： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="93022-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="93022-110">要比较的第二个值。</span><span class="sxs-lookup"><span data-stu-id="93022-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="93022-111">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="93022-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="93022-112">`true` 当且仅当 `a` 大于或等于时 `b` 。</span><span class="sxs-lookup"><span data-stu-id="93022-112">`true` if and only if `a` is greater than or is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="93022-113">注解</span><span class="sxs-lookup"><span data-stu-id="93022-113">Remarks</span></span>

<span data-ttu-id="93022-114">以下项是等效的：</span><span class="sxs-lookup"><span data-stu-id="93022-114">The following are equivalent:</span></span>

```Q#
let cond = a >= b;
let cond = GreaterThanOrEqualL(a, b);
```