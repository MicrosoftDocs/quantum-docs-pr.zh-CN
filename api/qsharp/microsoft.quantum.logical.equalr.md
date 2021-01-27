---
uid: Microsoft.Quantum.Logical.EqualR
title: EqualR 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualR
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 9ce29f2868f092001a3dca23a2913a3963ac70fe
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98815984"
---
# <a name="equalr-function"></a><span data-ttu-id="0349d-102">EqualR 函数</span><span class="sxs-lookup"><span data-stu-id="0349d-102">EqualR function</span></span>

<span data-ttu-id="0349d-103">命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="0349d-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="0349d-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0349d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0349d-105">当且仅当两个输入相等时，返回 true。</span><span class="sxs-lookup"><span data-stu-id="0349d-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualR (a : Result, b : Result) : Bool
```


## <a name="input"></a><span data-ttu-id="0349d-106">输入</span><span class="sxs-lookup"><span data-stu-id="0349d-106">Input</span></span>

### <a name="a--__invalidresult__"></a><span data-ttu-id="0349d-107">答：__无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="0349d-107">a : __invalid<Result>__</span></span>

<span data-ttu-id="0349d-108">要比较的第一个值。</span><span class="sxs-lookup"><span data-stu-id="0349d-108">The first value to be compared.</span></span>


### <a name="b--__invalidresult__"></a><span data-ttu-id="0349d-109">b：__无效 <Result>__</span><span class="sxs-lookup"><span data-stu-id="0349d-109">b : __invalid<Result>__</span></span>

<span data-ttu-id="0349d-110">要比较的第二个值。</span><span class="sxs-lookup"><span data-stu-id="0349d-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="0349d-111">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="0349d-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="0349d-112">`true` 当且仅当 `a` 等于时 `b` 。</span><span class="sxs-lookup"><span data-stu-id="0349d-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="0349d-113">备注</span><span class="sxs-lookup"><span data-stu-id="0349d-113">Remarks</span></span>

<span data-ttu-id="0349d-114">以下项是等效的：</span><span class="sxs-lookup"><span data-stu-id="0349d-114">The following are equivalent:</span></span>

```qsharp
let cond = a == b;
let cond = EqualR(a, b);
```