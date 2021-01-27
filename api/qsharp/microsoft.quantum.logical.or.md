---
uid: Microsoft.Quantum.Logical.Or
title: Or 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Or
qsharp.summary: Returns the Boolean disjunction of two values.
ms.openlocfilehash: 4a29b7684b28b904b43ccceb8e63280999690349
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848461"
---
# <a name="or-function"></a><span data-ttu-id="83c61-102">Or 函数</span><span class="sxs-lookup"><span data-stu-id="83c61-102">Or function</span></span>

<span data-ttu-id="83c61-103">命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="83c61-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="83c61-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="83c61-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="83c61-105">返回两个值的布尔析取。</span><span class="sxs-lookup"><span data-stu-id="83c61-105">Returns the Boolean disjunction of two values.</span></span>

```qsharp
function Or (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="83c61-106">输入</span><span class="sxs-lookup"><span data-stu-id="83c61-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="83c61-107">a： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="83c61-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="83c61-108">要考虑的第一个值。</span><span class="sxs-lookup"><span data-stu-id="83c61-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="83c61-109">b： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="83c61-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="83c61-110">要考虑的第二个值。</span><span class="sxs-lookup"><span data-stu-id="83c61-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="83c61-111">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="83c61-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="83c61-112">`true` 当且仅当 `a` 或 `b` 为时 `true` 。</span><span class="sxs-lookup"><span data-stu-id="83c61-112">`true` if and only if either `a` or `b` are `true`.</span></span>

## <a name="remarks"></a><span data-ttu-id="83c61-113">备注</span><span class="sxs-lookup"><span data-stu-id="83c61-113">Remarks</span></span>

<span data-ttu-id="83c61-114">与 `or` 运算符不同，此函数不会进行短路，因此，这两个输入都是完全计算的。</span><span class="sxs-lookup"><span data-stu-id="83c61-114">Unlike the `or` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="83c61-115">最多短路行为，如下所示：</span><span class="sxs-lookup"><span data-stu-id="83c61-115">Up to short-circuiting behavior, the following are equivalent:</span></span>

```qsharp
let x = a or b;
let x = Or(a, b);
```