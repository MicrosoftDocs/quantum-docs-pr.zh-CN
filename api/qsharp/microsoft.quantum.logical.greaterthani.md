---
uid: Microsoft.Quantum.Logical.GreaterThanI
title: GreaterThanI 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanI
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: ffd00d8086654a2d783a351fe254fb2ee35b9184
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695170"
---
# <a name="greaterthani-function"></a><span data-ttu-id="01e39-102">GreaterThanI 函数</span><span class="sxs-lookup"><span data-stu-id="01e39-102">GreaterThanI function</span></span>

<span data-ttu-id="01e39-103">命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="01e39-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="01e39-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="01e39-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="01e39-105">当且仅当一个数字大于另一个数字时，返回 true。</span><span class="sxs-lookup"><span data-stu-id="01e39-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="01e39-106">输入</span><span class="sxs-lookup"><span data-stu-id="01e39-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="01e39-107">a： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="01e39-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="01e39-108">要比较的第一个值。</span><span class="sxs-lookup"><span data-stu-id="01e39-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="01e39-109">b： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="01e39-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="01e39-110">要比较的第二个值。</span><span class="sxs-lookup"><span data-stu-id="01e39-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="01e39-111">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="01e39-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="01e39-112">`true` 当且仅当 `a` 严格大于时 `b` 。</span><span class="sxs-lookup"><span data-stu-id="01e39-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="01e39-113">注解</span><span class="sxs-lookup"><span data-stu-id="01e39-113">Remarks</span></span>

<span data-ttu-id="01e39-114">以下项是等效的：</span><span class="sxs-lookup"><span data-stu-id="01e39-114">The following are equivalent:</span></span>

```Q#
let cond = a > b;
let cond = GreaterThanI(a, b);
```