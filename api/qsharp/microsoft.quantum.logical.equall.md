---
uid: Microsoft.Quantum.Logical.EqualL
title: EqualL 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: EqualL
qsharp.summary: Returns true if and only if two inputs are equal.
ms.openlocfilehash: 58086f40ea20b6f1a5fa6996e3a6703e2bf66306
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98815968"
---
# <a name="equall-function"></a><span data-ttu-id="5e4ec-102">EqualL 函数</span><span class="sxs-lookup"><span data-stu-id="5e4ec-102">EqualL function</span></span>

<span data-ttu-id="5e4ec-103">命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="5e4ec-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="5e4ec-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5e4ec-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="5e4ec-105">当且仅当两个输入相等时，返回 true。</span><span class="sxs-lookup"><span data-stu-id="5e4ec-105">Returns true if and only if two inputs are equal.</span></span>

```qsharp
function EqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="5e4ec-106">输入</span><span class="sxs-lookup"><span data-stu-id="5e4ec-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="5e4ec-107">a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="5e4ec-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="5e4ec-108">要比较的第一个值。</span><span class="sxs-lookup"><span data-stu-id="5e4ec-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="5e4ec-109">b： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="5e4ec-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="5e4ec-110">要比较的第二个值。</span><span class="sxs-lookup"><span data-stu-id="5e4ec-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="5e4ec-111">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="5e4ec-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="5e4ec-112">`true` 当且仅当 `a` 等于时 `b` 。</span><span class="sxs-lookup"><span data-stu-id="5e4ec-112">`true` if and only if `a` is equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="5e4ec-113">备注</span><span class="sxs-lookup"><span data-stu-id="5e4ec-113">Remarks</span></span>

<span data-ttu-id="5e4ec-114">以下项是等效的：</span><span class="sxs-lookup"><span data-stu-id="5e4ec-114">The following are equivalent:</span></span>

```qsharp
let cond = a == b;
let cond = EqualL(a, b);
```