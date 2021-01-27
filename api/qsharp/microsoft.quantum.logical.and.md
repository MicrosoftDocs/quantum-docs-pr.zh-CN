---
uid: Microsoft.Quantum.Logical.And
title: And 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: And
qsharp.summary: Returns the Boolean conjunction of two values.
ms.openlocfilehash: 6c405bdb4182cc7f32bd04952dec25a974c03445
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849230"
---
# <a name="and-function"></a><span data-ttu-id="30bbb-102">And 函数</span><span class="sxs-lookup"><span data-stu-id="30bbb-102">And function</span></span>

<span data-ttu-id="30bbb-103">命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="30bbb-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="30bbb-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="30bbb-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="30bbb-105">返回两个值的布尔值。</span><span class="sxs-lookup"><span data-stu-id="30bbb-105">Returns the Boolean conjunction of two values.</span></span>

```qsharp
function And (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="30bbb-106">输入</span><span class="sxs-lookup"><span data-stu-id="30bbb-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="30bbb-107">a： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="30bbb-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="30bbb-108">要考虑的第一个值。</span><span class="sxs-lookup"><span data-stu-id="30bbb-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="30bbb-109">b： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="30bbb-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="30bbb-110">要考虑的第二个值。</span><span class="sxs-lookup"><span data-stu-id="30bbb-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="30bbb-111">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="30bbb-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="30bbb-112">`true` 当且仅当 `a` 和 `b` 都是时 `true` 。</span><span class="sxs-lookup"><span data-stu-id="30bbb-112">`true` if and only if `a` and `b` are both `true`.</span></span>

## <a name="remarks"></a><span data-ttu-id="30bbb-113">备注</span><span class="sxs-lookup"><span data-stu-id="30bbb-113">Remarks</span></span>

<span data-ttu-id="30bbb-114">与 `and` 运算符不同，此函数不会进行短路，因此，这两个输入都是完全计算的。</span><span class="sxs-lookup"><span data-stu-id="30bbb-114">Unlike the `and` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="30bbb-115">最多短路行为，如下所示：</span><span class="sxs-lookup"><span data-stu-id="30bbb-115">Up to short-circuiting behavior, the following are equivalent:</span></span>

```qsharp
let x = a and b;
let x = And(a, b);
```