---
uid: Microsoft.Quantum.Logical.GreaterThanD
title: GreaterThanD 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanD
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: c23d85cf513bb6d37e67260eeeb3b81b42e6771a
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96198021"
---
# <a name="greaterthand-function"></a><span data-ttu-id="c57c3-102">GreaterThanD 函数</span><span class="sxs-lookup"><span data-stu-id="c57c3-102">GreaterThanD function</span></span>

<span data-ttu-id="c57c3-103">命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="c57c3-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="c57c3-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="c57c3-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="c57c3-105">当且仅当一个数字大于另一个数字时，返回 true。</span><span class="sxs-lookup"><span data-stu-id="c57c3-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="c57c3-106">输入</span><span class="sxs-lookup"><span data-stu-id="c57c3-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="c57c3-107">答： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c57c3-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c57c3-108">要比较的第一个值。</span><span class="sxs-lookup"><span data-stu-id="c57c3-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="c57c3-109">b： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c57c3-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c57c3-110">要比较的第二个值。</span><span class="sxs-lookup"><span data-stu-id="c57c3-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="c57c3-111">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="c57c3-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="c57c3-112">`true` 当且仅当 `a` 严格大于时 `b` 。</span><span class="sxs-lookup"><span data-stu-id="c57c3-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="c57c3-113">备注</span><span class="sxs-lookup"><span data-stu-id="c57c3-113">Remarks</span></span>

<span data-ttu-id="c57c3-114">以下项是等效的：</span><span class="sxs-lookup"><span data-stu-id="c57c3-114">The following are equivalent:</span></span>

```Q#
let cond = a > b;
let cond = GreaterThanD(a, b);
```