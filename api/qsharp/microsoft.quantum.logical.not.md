---
uid: Microsoft.Quantum.Logical.Not
title: Not 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: 3a688aac0178a2f4127496c1009fe7d5ee7ae198
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695153"
---
# <a name="not-function"></a><span data-ttu-id="529a8-102">Not 函数</span><span class="sxs-lookup"><span data-stu-id="529a8-102">Not function</span></span>

<span data-ttu-id="529a8-103">命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="529a8-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="529a8-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="529a8-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="529a8-105">返回值的布尔值求反。</span><span class="sxs-lookup"><span data-stu-id="529a8-105">Returns the Boolean negation of a value.</span></span>

```qsharp
function Not (value : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="529a8-106">输入</span><span class="sxs-lookup"><span data-stu-id="529a8-106">Input</span></span>

### <a name="value--bool"></a><span data-ttu-id="529a8-107">值： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="529a8-107">value : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="529a8-108">要求反的值。</span><span class="sxs-lookup"><span data-stu-id="529a8-108">The value to be negated.</span></span>



## <a name="output--bool"></a><span data-ttu-id="529a8-109">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="529a8-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="529a8-110">`true` 当且仅当 `value` 为时 `false` 。</span><span class="sxs-lookup"><span data-stu-id="529a8-110">`true` if and only if `value` is `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="529a8-111">注解</span><span class="sxs-lookup"><span data-stu-id="529a8-111">Remarks</span></span>

<span data-ttu-id="529a8-112">以下项是等效的：</span><span class="sxs-lookup"><span data-stu-id="529a8-112">The following are equivalent:</span></span>

```Q#
let x = not value;
let x = Not(value);
```