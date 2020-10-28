---
uid: Microsoft.Quantum.Bitwise.LeftShiftedL
title: LeftShiftedL 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedL
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 17e5c845755f74e9703381bc82bfd63be836d038
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696416"
---
# <a name="leftshiftedl-function"></a><span data-ttu-id="cb9d1-102">LeftShiftedL 函数</span><span class="sxs-lookup"><span data-stu-id="cb9d1-102">LeftShiftedL function</span></span>

<span data-ttu-id="cb9d1-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="cb9d1-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="cb9d1-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="cb9d1-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="cb9d1-105">将数字的按位表示形式向左移动给定的位数。</span><span class="sxs-lookup"><span data-stu-id="cb9d1-105">Shifts the bitwise representation of a number left by a given number of bits.</span></span>

```qsharp
function LeftShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="cb9d1-106">输入</span><span class="sxs-lookup"><span data-stu-id="cb9d1-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="cb9d1-107">值： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="cb9d1-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="cb9d1-108">要向左移动 (更重要) 的按位表示形式的数字。</span><span class="sxs-lookup"><span data-stu-id="cb9d1-108">The number whose bitwise representation is to be shifted to the left (more significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="cb9d1-109">金额： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="cb9d1-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="cb9d1-110">要向左移动的位数 `value` 。</span><span class="sxs-lookup"><span data-stu-id="cb9d1-110">The number of bits by which `value` is to be shifted to the left.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="cb9d1-111">输出： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="cb9d1-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="cb9d1-112">的值 `value` ，按位向左移动 `amount` 。</span><span class="sxs-lookup"><span data-stu-id="cb9d1-112">The value of `value`, shifted left by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="cb9d1-113">注解</span><span class="sxs-lookup"><span data-stu-id="cb9d1-113">Remarks</span></span>

<span data-ttu-id="cb9d1-114">以下项是等效的：</span><span class="sxs-lookup"><span data-stu-id="cb9d1-114">The following are equivalent:</span></span>

```Q#
let c = a <<< b;
let c = LeftShiftedL(a, b);
```