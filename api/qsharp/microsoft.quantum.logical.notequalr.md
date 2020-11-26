---
uid: Microsoft.Quantum.Logical.NotEqualR
title: NotEqualR 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualR
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 4ac6cf4b220fa42c8eb946d6fbcad4cdb191afcd
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197188"
---
# <a name="notequalr-function"></a><span data-ttu-id="7f1f0-102">NotEqualR 函数</span><span class="sxs-lookup"><span data-stu-id="7f1f0-102">NotEqualR function</span></span>

<span data-ttu-id="7f1f0-103">命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="7f1f0-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="7f1f0-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7f1f0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7f1f0-105">当且仅当两个输入不相等时，返回 true。</span><span class="sxs-lookup"><span data-stu-id="7f1f0-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="7f1f0-106">输入</span><span class="sxs-lookup"><span data-stu-id="7f1f0-106">Input</span></span>

### <a name="a--__invalidresult__"></a><span data-ttu-id="7f1f0-107">答：__无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="7f1f0-107">a : __invalid<Result>__</span></span>

<span data-ttu-id="7f1f0-108">要比较的第一个值。</span><span class="sxs-lookup"><span data-stu-id="7f1f0-108">The first value to be compared.</span></span>


### <a name="b--__invalidresult__"></a><span data-ttu-id="7f1f0-109">b：__无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="7f1f0-109">b : __invalid<Result>__</span></span>

<span data-ttu-id="7f1f0-110">要比较的第二个值。</span><span class="sxs-lookup"><span data-stu-id="7f1f0-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="7f1f0-111">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="7f1f0-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="7f1f0-112">`true` 当且仅当不 `a` 等于时 `b` 。</span><span class="sxs-lookup"><span data-stu-id="7f1f0-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="7f1f0-113">备注</span><span class="sxs-lookup"><span data-stu-id="7f1f0-113">Remarks</span></span>

<span data-ttu-id="7f1f0-114">以下项是等效的：</span><span class="sxs-lookup"><span data-stu-id="7f1f0-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualR(a, b);
```