---
uid: Microsoft.Quantum.Bitwise.LeftShiftedI
title: LeftShiftedI 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedI
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: ce68311adf211169c2fb499bb189332370a6d6ac
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696421"
---
# <a name="leftshiftedi-function"></a><span data-ttu-id="2891a-102">LeftShiftedI 函数</span><span class="sxs-lookup"><span data-stu-id="2891a-102">LeftShiftedI function</span></span>

<span data-ttu-id="2891a-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="2891a-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="2891a-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2891a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2891a-105">将数字的按位表示形式向左移动给定的位数。</span><span class="sxs-lookup"><span data-stu-id="2891a-105">Shifts the bitwise representation of a number left by a given number of bits.</span></span>

```qsharp
function LeftShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a><span data-ttu-id="2891a-106">输入</span><span class="sxs-lookup"><span data-stu-id="2891a-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="2891a-107">值： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2891a-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2891a-108">要向左移动 (更重要) 的按位表示形式的数字。</span><span class="sxs-lookup"><span data-stu-id="2891a-108">The number whose bitwise representation is to be shifted to the left (more significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="2891a-109">金额： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2891a-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2891a-110">要向左移动的位数 `value` 。</span><span class="sxs-lookup"><span data-stu-id="2891a-110">The number of bits by which `value` is to be shifted to the left.</span></span>



## <a name="output--int"></a><span data-ttu-id="2891a-111">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2891a-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2891a-112">的值 `value` ，按位向左移动 `amount` 。</span><span class="sxs-lookup"><span data-stu-id="2891a-112">The value of `value`, shifted left by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="2891a-113">注解</span><span class="sxs-lookup"><span data-stu-id="2891a-113">Remarks</span></span>

<span data-ttu-id="2891a-114">以下项是等效的：</span><span class="sxs-lookup"><span data-stu-id="2891a-114">The following are equivalent:</span></span>

```Q#
let c = a <<< b;
let c = LeftShiftedI(a, b);
```