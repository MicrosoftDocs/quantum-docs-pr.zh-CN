---
uid: Microsoft.Quantum.Logical.EqualB
title: EqualB 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualB
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 2a15a749f52fe814db4fa57118f69c80fa22158a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98817259"
---
# <a name="equalb-function"></a><span data-ttu-id="d6b74-102">EqualB 函数</span><span class="sxs-lookup"><span data-stu-id="d6b74-102">EqualB function</span></span>

<span data-ttu-id="d6b74-103">命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="d6b74-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="d6b74-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="d6b74-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="d6b74-105">当且仅当两个输入相等时，返回 true。</span><span class="sxs-lookup"><span data-stu-id="d6b74-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualB (a : Bool, b : Bool) : Bool
```


## <a name="input"></a><span data-ttu-id="d6b74-106">输入</span><span class="sxs-lookup"><span data-stu-id="d6b74-106">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="d6b74-107">a： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d6b74-107">a : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d6b74-108">要比较的第一个值。</span><span class="sxs-lookup"><span data-stu-id="d6b74-108">The first value to be compared.</span></span>


### <a name="b--bool"></a><span data-ttu-id="d6b74-109">b： [Bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="d6b74-109">b : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d6b74-110">要比较的第二个值。</span><span class="sxs-lookup"><span data-stu-id="d6b74-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="d6b74-111">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="d6b74-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="d6b74-112">`true` 当且仅当 `a` 等于时 `b` 。</span><span class="sxs-lookup"><span data-stu-id="d6b74-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="d6b74-113">备注</span><span class="sxs-lookup"><span data-stu-id="d6b74-113">Remarks</span></span>

<span data-ttu-id="d6b74-114">以下项是等效的：</span><span class="sxs-lookup"><span data-stu-id="d6b74-114">The following are equivalent:</span></span>

```qsharp
let cond = a == b;
let cond = EqualB(a, b);
```