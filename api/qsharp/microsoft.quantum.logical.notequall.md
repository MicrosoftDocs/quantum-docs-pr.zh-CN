---
uid: Microsoft.Quantum.Logical.NotEqualL
title: NotEqualL 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotEqualL
qsharp.summary: Returns true if and only if two inputs are not equal.
ms.openlocfilehash: b19de2e4e8052c77118f341700357b212e20af53
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849027"
---
# <a name="notequall-function"></a><span data-ttu-id="6ebe7-102">NotEqualL 函数</span><span class="sxs-lookup"><span data-stu-id="6ebe7-102">NotEqualL function</span></span>

<span data-ttu-id="6ebe7-103">命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="6ebe7-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="6ebe7-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6ebe7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6ebe7-105">当且仅当两个输入不相等时，返回 true。</span><span class="sxs-lookup"><span data-stu-id="6ebe7-105">Returns true if and only if two inputs are not equal.</span></span>

```qsharp
function NotEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="6ebe7-106">输入</span><span class="sxs-lookup"><span data-stu-id="6ebe7-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="6ebe7-107">a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="6ebe7-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="6ebe7-108">要比较的第一个值。</span><span class="sxs-lookup"><span data-stu-id="6ebe7-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="6ebe7-109">b： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="6ebe7-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="6ebe7-110">要比较的第二个值。</span><span class="sxs-lookup"><span data-stu-id="6ebe7-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="6ebe7-111">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="6ebe7-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6ebe7-112">`true` 当且仅当不 `a` 等于时 `b` 。</span><span class="sxs-lookup"><span data-stu-id="6ebe7-112">`true` if and only if `a` is not equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="6ebe7-113">备注</span><span class="sxs-lookup"><span data-stu-id="6ebe7-113">Remarks</span></span>

<span data-ttu-id="6ebe7-114">以下项是等效的：</span><span class="sxs-lookup"><span data-stu-id="6ebe7-114">The following are equivalent:</span></span>

```qsharp
let cond = a != b;
let cond = NotEqualL(a, b);
```