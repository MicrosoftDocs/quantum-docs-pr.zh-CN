---
uid: Microsoft.Quantum.Logical.Not
title: Not 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: f2db43f4a2ce83d8cad1d60aa8c481a33b0c7d44
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96197443"
---
# <a name="not-function"></a><span data-ttu-id="cd5e4-102">Not 函数</span><span class="sxs-lookup"><span data-stu-id="cd5e4-102">Not function</span></span>

<span data-ttu-id="cd5e4-103">命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="cd5e4-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="cd5e4-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="cd5e4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="cd5e4-105">返回值的布尔值求反。</span><span class="sxs-lookup"><span data-stu-id="cd5e4-105">Returns the Boolean negation of a value.</span></span>

```qsharp
function Not (value : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="cd5e4-106">输入</span><span class="sxs-lookup"><span data-stu-id="cd5e4-106">Input</span></span>

### <a name="value--bool"></a><span data-ttu-id="cd5e4-107">值： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="cd5e4-107">value : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="cd5e4-108">要求反的值。</span><span class="sxs-lookup"><span data-stu-id="cd5e4-108">The value to be negated.</span></span>



## <a name="output--bool"></a><span data-ttu-id="cd5e4-109">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="cd5e4-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="cd5e4-110">`true` 当且仅当 `value` 为时 `false` 。</span><span class="sxs-lookup"><span data-stu-id="cd5e4-110">`true` if and only if `value` is `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="cd5e4-111">备注</span><span class="sxs-lookup"><span data-stu-id="cd5e4-111">Remarks</span></span>

<span data-ttu-id="cd5e4-112">以下项是等效的：</span><span class="sxs-lookup"><span data-stu-id="cd5e4-112">The following are equivalent:</span></span>

```Q#
let x = not value;
let x = Not(value);
```