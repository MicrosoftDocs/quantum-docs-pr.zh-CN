---
uid: Microsoft.Quantum.Logical.NotEqualR
title: NotEqualR 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualR
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: 06615c7ffb6aafc296077990dfca0ce25e1e00fa
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695143"
---
# <a name="notequalr-function"></a><span data-ttu-id="3e3f5-102">NotEqualR 函数</span><span class="sxs-lookup"><span data-stu-id="3e3f5-102">NotEqualR function</span></span>

<span data-ttu-id="3e3f5-103">命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="3e3f5-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="3e3f5-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="3e3f5-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="3e3f5-105">当且仅当两个输入不相等时，返回 true。</span><span class="sxs-lookup"><span data-stu-id="3e3f5-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="3e3f5-106">输入</span><span class="sxs-lookup"><span data-stu-id="3e3f5-106">Input</span></span>

### <a name="a--__invalidresult__"></a><span data-ttu-id="3e3f5-107">答： __无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="3e3f5-107">a : __invalid<Result>__</span></span>

<span data-ttu-id="3e3f5-108">要比较的第一个值。</span><span class="sxs-lookup"><span data-stu-id="3e3f5-108">The first value to be compared.</span></span>


### <a name="b--__invalidresult__"></a><span data-ttu-id="3e3f5-109">b： __无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="3e3f5-109">b : __invalid<Result>__</span></span>

<span data-ttu-id="3e3f5-110">要比较的第二个值。</span><span class="sxs-lookup"><span data-stu-id="3e3f5-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="3e3f5-111">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="3e3f5-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="3e3f5-112">`true` 当且仅当不 `a` 等于时 `b` 。</span><span class="sxs-lookup"><span data-stu-id="3e3f5-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="3e3f5-113">注解</span><span class="sxs-lookup"><span data-stu-id="3e3f5-113">Remarks</span></span>

<span data-ttu-id="3e3f5-114">以下项是等效的：</span><span class="sxs-lookup"><span data-stu-id="3e3f5-114">The following are equivalent:</span></span>

```Q#
let cond = a != b;
let cond = NotEqualR(a, b);
```