---
uid: Microsoft.Quantum.Logical.EqualI
title: EqualI 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualI
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 6b805e76217e033cb0135cf85bd8f37a3eb8636a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695180"
---
# <a name="equali-function"></a><span data-ttu-id="6c994-102">EqualI 函数</span><span class="sxs-lookup"><span data-stu-id="6c994-102">EqualI function</span></span>

<span data-ttu-id="6c994-103">命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="6c994-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="6c994-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="6c994-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="6c994-105">当且仅当两个输入相等时，返回 true。</span><span class="sxs-lookup"><span data-stu-id="6c994-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualI (a : Int, b : Int) : Bool
```


## <a name="input"></a><span data-ttu-id="6c994-106">输入</span><span class="sxs-lookup"><span data-stu-id="6c994-106">Input</span></span>

### <a name="a--int"></a><span data-ttu-id="6c994-107">a： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6c994-107">a : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6c994-108">要比较的第一个值。</span><span class="sxs-lookup"><span data-stu-id="6c994-108">The first value to be compared.</span></span>


### <a name="b--int"></a><span data-ttu-id="6c994-109">b： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6c994-109">b : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6c994-110">要比较的第二个值。</span><span class="sxs-lookup"><span data-stu-id="6c994-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="6c994-111">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="6c994-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6c994-112">`true` 当且仅当 `a` 等于时 `b` 。</span><span class="sxs-lookup"><span data-stu-id="6c994-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="6c994-113">注解</span><span class="sxs-lookup"><span data-stu-id="6c994-113">Remarks</span></span>

<span data-ttu-id="6c994-114">以下项是等效的：</span><span class="sxs-lookup"><span data-stu-id="6c994-114">The following are equivalent:</span></span>

```Q#
let cond = a == b;
let cond = EqualI(a, b);
```