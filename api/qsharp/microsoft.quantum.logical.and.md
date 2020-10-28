---
uid: Microsoft.Quantum.Logical.And
title: And 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: And
qsharp.summary: Returns the Boolean conjunction of two values.
ms.openlocfilehash: cc81f650216c4db219a79c4fe89a42447a4e95b8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92699760"
---
# <a name="and-function"></a><span data-ttu-id="0650b-102">And 函数</span><span class="sxs-lookup"><span data-stu-id="0650b-102">And function</span></span>

<span data-ttu-id="0650b-103">命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="0650b-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="0650b-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0650b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0650b-105">返回两个值的布尔值。</span><span class="sxs-lookup"><span data-stu-id="0650b-105">Returns the Boolean conjunction of two values.</span></span>

```qsharp
function And (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="0650b-106">输入</span><span class="sxs-lookup"><span data-stu-id="0650b-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="0650b-107">a： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="0650b-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="0650b-108">要考虑的第一个值。</span><span class="sxs-lookup"><span data-stu-id="0650b-108">The first value to be considered.</span></span>


### <a name="b--bool"></a><span data-ttu-id="0650b-109">b： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="0650b-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="0650b-110">要考虑的第二个值。</span><span class="sxs-lookup"><span data-stu-id="0650b-110">The second value to be considered.</span></span>



## <a name="output--bool"></a><span data-ttu-id="0650b-111">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="0650b-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="0650b-112">`true` 当且仅当 `a` 和 `b` 都是时 `true` 。</span><span class="sxs-lookup"><span data-stu-id="0650b-112">`true` if and only if `a` and `b` are both `true`.</span></span>

## <a name="remarks"></a><span data-ttu-id="0650b-113">注解</span><span class="sxs-lookup"><span data-stu-id="0650b-113">Remarks</span></span>

<span data-ttu-id="0650b-114">与 `and` 运算符不同，此函数不会进行短路，因此，这两个输入都是完全计算的。</span><span class="sxs-lookup"><span data-stu-id="0650b-114">Unlike the `and` operator, this function does not short-circuit, such that both inputs are fully evaluated.</span></span>

<span data-ttu-id="0650b-115">最多短路行为，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0650b-115">Up to short-circuiting behavior, the following are equivalent:</span></span>

```Q#
let x = a and b;
let x = And(a, b);
```