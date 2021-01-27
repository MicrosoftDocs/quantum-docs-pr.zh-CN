---
uid: Microsoft.Quantum.Bitwise.LeftShiftedI
title: LeftShiftedI 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedI
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 3f551bdba5c8e2a1456838769e4cee0660d0f969
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845308"
---
# <a name="leftshiftedi-function"></a><span data-ttu-id="ad741-102">LeftShiftedI 函数</span><span class="sxs-lookup"><span data-stu-id="ad741-102">LeftShiftedI function</span></span>

<span data-ttu-id="ad741-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="ad741-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="ad741-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ad741-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ad741-105">将数字的按位表示形式向左移动给定的位数。</span><span class="sxs-lookup"><span data-stu-id="ad741-105">Shifts the bitwise representation of a number left by a given number of bits.</span></span>

```qsharp
function LeftShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a><span data-ttu-id="ad741-106">输入</span><span class="sxs-lookup"><span data-stu-id="ad741-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="ad741-107">值： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ad741-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ad741-108">要向左移动 (更重要) 的按位表示形式的数字。</span><span class="sxs-lookup"><span data-stu-id="ad741-108">The number whose bitwise representation is to be shifted to the left (more significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="ad741-109">金额： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ad741-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ad741-110">要向左移动的位数 `value` 。</span><span class="sxs-lookup"><span data-stu-id="ad741-110">The number of bits by which `value` is to be shifted to the left.</span></span>



## <a name="output--int"></a><span data-ttu-id="ad741-111">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ad741-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ad741-112">的值 `value` ，按位向左移动 `amount` 。</span><span class="sxs-lookup"><span data-stu-id="ad741-112">The value of `value`, shifted left by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="ad741-113">备注</span><span class="sxs-lookup"><span data-stu-id="ad741-113">Remarks</span></span>

<span data-ttu-id="ad741-114">以下项是等效的：</span><span class="sxs-lookup"><span data-stu-id="ad741-114">The following are equivalent:</span></span>

```qsharp
let c = a <<< b;
let c = LeftShiftedI(a, b);
```