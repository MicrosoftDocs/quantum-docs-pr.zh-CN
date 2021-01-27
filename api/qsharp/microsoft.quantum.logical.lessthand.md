---
uid: Microsoft.Quantum.Logical.LessThanD
title: LessThanD 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanD
qsharp.summary: Returns true if and only if a number is less than another number.
ms.openlocfilehash: 7135ed4b3414d143f5020496ae524bf89980a8a1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849162"
---
# <a name="lessthand-function"></a><span data-ttu-id="6d776-102">LessThanD 函数</span><span class="sxs-lookup"><span data-stu-id="6d776-102">LessThanD function</span></span>

<span data-ttu-id="6d776-103">命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="6d776-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="6d776-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="6d776-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="6d776-105">当且仅当一个数字小于另一个数字时，返回 true。</span><span class="sxs-lookup"><span data-stu-id="6d776-105">Returns true if and only if a number is less than another number.</span></span>

```qsharp
function LessThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="6d776-106">输入</span><span class="sxs-lookup"><span data-stu-id="6d776-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="6d776-107">答： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6d776-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6d776-108">要比较的第一个值。</span><span class="sxs-lookup"><span data-stu-id="6d776-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="6d776-109">b： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6d776-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6d776-110">要比较的第二个值。</span><span class="sxs-lookup"><span data-stu-id="6d776-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="6d776-111">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="6d776-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="6d776-112">`true` 当且仅当 `a` 严格小于时 `b` 。</span><span class="sxs-lookup"><span data-stu-id="6d776-112">`true` if and only if `a` is strictly less than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="6d776-113">备注</span><span class="sxs-lookup"><span data-stu-id="6d776-113">Remarks</span></span>

<span data-ttu-id="6d776-114">以下项是等效的：</span><span class="sxs-lookup"><span data-stu-id="6d776-114">The following are equivalent:</span></span>

```qsharp
let cond = a < b;
let cond = LessThanD(a, b);
```