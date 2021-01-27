---
uid: Microsoft.Quantum.Logical.GreaterThanD
title: GreaterThanD 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: GreaterThanD
qsharp.summary: Returns true if and only if a number is greater than another number.
ms.openlocfilehash: 26a963645758b6de83654304c38830af5c561b3a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98849217"
---
# <a name="greaterthand-function"></a><span data-ttu-id="73b64-102">GreaterThanD 函数</span><span class="sxs-lookup"><span data-stu-id="73b64-102">GreaterThanD function</span></span>

<span data-ttu-id="73b64-103">命名空间： [Microsoft 量子. 逻辑](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="73b64-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="73b64-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="73b64-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="73b64-105">当且仅当一个数字大于另一个数字时，返回 true。</span><span class="sxs-lookup"><span data-stu-id="73b64-105">Returns true if and only if a number is greater than another number.</span></span>

```qsharp
function GreaterThanD (a : Double, b : Double) : Bool
```


## <a name="input"></a><span data-ttu-id="73b64-106">输入</span><span class="sxs-lookup"><span data-stu-id="73b64-106">Input</span></span>

### <a name="a--double"></a><span data-ttu-id="73b64-107">答： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="73b64-107">a : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="73b64-108">要比较的第一个值。</span><span class="sxs-lookup"><span data-stu-id="73b64-108">The first value to be compared.</span></span>


### <a name="b--double"></a><span data-ttu-id="73b64-109">b： [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="73b64-109">b : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="73b64-110">要比较的第二个值。</span><span class="sxs-lookup"><span data-stu-id="73b64-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="73b64-111">输出：[布尔](xref:microsoft.quantum.lang-ref.bool)值</span><span class="sxs-lookup"><span data-stu-id="73b64-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="73b64-112">`true` 当且仅当 `a` 严格大于时 `b` 。</span><span class="sxs-lookup"><span data-stu-id="73b64-112">`true` if and only if `a` is strictly greater than `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="73b64-113">备注</span><span class="sxs-lookup"><span data-stu-id="73b64-113">Remarks</span></span>

<span data-ttu-id="73b64-114">以下项是等效的：</span><span class="sxs-lookup"><span data-stu-id="73b64-114">The following are equivalent:</span></span>

```qsharp
let cond = a > b;
let cond = GreaterThanD(a, b);
```