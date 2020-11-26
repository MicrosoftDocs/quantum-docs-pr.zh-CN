---
uid: Microsoft.Quantum.Logical.LessThanI
title: LessThanI 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanI
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 5d5b17c8481ccf58b8e4fc4bb958e0adbf6d8f00
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197766"
---
# <a name="lessthani-function"></a><span data-ttu-id="80a87-102">LessThanI 函数</span><span class="sxs-lookup"><span data-stu-id="80a87-102">LessThanI function</span></span>

<span data-ttu-id="80a87-103">命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="80a87-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="80a87-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="80a87-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="80a87-105">当且仅当一个数字小于另一个数字时，返回 true。</span><span class="sxs-lookup"><span data-stu-id="80a87-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="80a87-106">输入</span><span class="sxs-lookup"><span data-stu-id="80a87-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="80a87-107">a： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="80a87-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="80a87-108">要比较的第一个值。</span><span class="sxs-lookup"><span data-stu-id="80a87-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="80a87-109">b： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="80a87-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="80a87-110">要比较的第二个值。</span><span class="sxs-lookup"><span data-stu-id="80a87-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="80a87-111">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="80a87-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="80a87-112">`true` 当且仅当 `a` 严格小于时 `b` 。</span><span class="sxs-lookup"><span data-stu-id="80a87-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="80a87-113">备注</span><span class="sxs-lookup"><span data-stu-id="80a87-113">Remarks</span></span>

<span data-ttu-id="80a87-114">以下项是等效的：</span><span class="sxs-lookup"><span data-stu-id="80a87-114">The following are equivalent:</span></span>

```Q#
let cond = a < b;
let cond = LessThanI(a, b);
```