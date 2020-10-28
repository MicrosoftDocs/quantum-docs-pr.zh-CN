---
uid: Microsoft.Quantum.Logical.NotEqualI
title: NotEqualI 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualI
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 68e0e105a6b3742ec11e80ff92c39578a786aa85
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695148"
---
# <a name="notequali-function"></a><span data-ttu-id="6beac-102">NotEqualI 函数</span><span class="sxs-lookup"><span data-stu-id="6beac-102">NotEqualI function</span></span>

<span data-ttu-id="6beac-103">命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="6beac-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="6beac-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6beac-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6beac-105">当且仅当两个输入不相等时，返回 true。</span><span class="sxs-lookup"><span data-stu-id="6beac-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="6beac-106">输入</span><span class="sxs-lookup"><span data-stu-id="6beac-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="6beac-107">a： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6beac-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6beac-108">要比较的第一个值。</span><span class="sxs-lookup"><span data-stu-id="6beac-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="6beac-109">b： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6beac-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6beac-110">要比较的第二个值。</span><span class="sxs-lookup"><span data-stu-id="6beac-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="6beac-111">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="6beac-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6beac-112">`true` 当且仅当不 `a` 等于时 `b` 。</span><span class="sxs-lookup"><span data-stu-id="6beac-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="6beac-113">注解</span><span class="sxs-lookup"><span data-stu-id="6beac-113">Remarks</span></span>

<span data-ttu-id="6beac-114">以下项是等效的：</span><span class="sxs-lookup"><span data-stu-id="6beac-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualI(a, b);
```