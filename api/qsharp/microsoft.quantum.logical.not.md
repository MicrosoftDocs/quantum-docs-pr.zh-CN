---
uid: Microsoft.Quantum.Logical.Not
title: Not 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: Not
qsharp.summary: Returns the Boolean negation of a value.
ms.openlocfilehash: bf09cac8d126371df6218b7e92d68a881b732dc8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849074"
---
# <a name="not-function"></a><span data-ttu-id="78762-102">Not 函数</span><span class="sxs-lookup"><span data-stu-id="78762-102">Not function</span></span>

<span data-ttu-id="78762-103">命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="78762-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="78762-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="78762-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="78762-105">返回值的布尔值求反。</span><span class="sxs-lookup"><span data-stu-id="78762-105">Returns the Boolean negation of a value.</span></span>

```qsharp
function Not (value : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="78762-106">输入</span><span class="sxs-lookup"><span data-stu-id="78762-106">Input</span></span>

### <a name="value--bool"></a><span data-ttu-id="78762-107">值： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="78762-107">value : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="78762-108">要求反的值。</span><span class="sxs-lookup"><span data-stu-id="78762-108">The value to be negated.</span></span>



## <a name="output--bool"></a><span data-ttu-id="78762-109">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="78762-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="78762-110">`true` 当且仅当 `value` 为时 `false` 。</span><span class="sxs-lookup"><span data-stu-id="78762-110">`true` if and only if `value` is `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="78762-111">备注</span><span class="sxs-lookup"><span data-stu-id="78762-111">Remarks</span></span>

<span data-ttu-id="78762-112">以下项是等效的：</span><span class="sxs-lookup"><span data-stu-id="78762-112">The following are equivalent:</span></span>

```qsharp
let x = not value;
let x = Not(value);
```