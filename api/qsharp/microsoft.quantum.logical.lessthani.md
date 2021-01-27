---
uid: Microsoft.Quantum.Logical.LessThanI
title: LessThanI 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanI
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 69c3d7c414967b830c15189c895a2b34f409c7b3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98815839"
---
# <a name="lessthani-function"></a><span data-ttu-id="b985a-102">LessThanI 函数</span><span class="sxs-lookup"><span data-stu-id="b985a-102">LessThanI function</span></span>

<span data-ttu-id="b985a-103">命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="b985a-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="b985a-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="b985a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="b985a-105">当且仅当一个数字小于另一个数字时，返回 true。</span><span class="sxs-lookup"><span data-stu-id="b985a-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="b985a-106">输入</span><span class="sxs-lookup"><span data-stu-id="b985a-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="b985a-107">a： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b985a-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b985a-108">要比较的第一个值。</span><span class="sxs-lookup"><span data-stu-id="b985a-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="b985a-109">b： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="b985a-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="b985a-110">要比较的第二个值。</span><span class="sxs-lookup"><span data-stu-id="b985a-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="b985a-111">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="b985a-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="b985a-112">`true` 当且仅当 `a` 严格小于时 `b` 。</span><span class="sxs-lookup"><span data-stu-id="b985a-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="b985a-113">备注</span><span class="sxs-lookup"><span data-stu-id="b985a-113">Remarks</span></span>

<span data-ttu-id="b985a-114">以下项是等效的：</span><span class="sxs-lookup"><span data-stu-id="b985a-114">The following are equivalent:</span></span>

```qsharp
let cond = a < b;
let cond = LessThanI(a, b);
```