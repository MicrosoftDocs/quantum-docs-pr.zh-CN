---
uid: Microsoft.Quantum.Bitwise.LeftShiftedL
title: LeftShiftedL 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: LeftShiftedL
qsharp.summary: Shifts the bitwise representation of a number left by a given number of bits.
ms.openlocfilehash: 00d4f9151c620e044074930933ea2912b52534ed
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219662"
---
# <a name="leftshiftedl-function"></a><span data-ttu-id="88e0d-102">LeftShiftedL 函数</span><span class="sxs-lookup"><span data-stu-id="88e0d-102">LeftShiftedL function</span></span>

<span data-ttu-id="88e0d-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="88e0d-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="88e0d-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="88e0d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="88e0d-105">将数字的按位表示形式向左移动给定的位数。</span><span class="sxs-lookup"><span data-stu-id="88e0d-105">Shifts the bitwise representation of a number left by a given number of bits.</span></span>

```qsharp
function LeftShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="88e0d-106">输入</span><span class="sxs-lookup"><span data-stu-id="88e0d-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="88e0d-107">值： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="88e0d-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="88e0d-108">要向左移动 (更重要) 的按位表示形式的数字。</span><span class="sxs-lookup"><span data-stu-id="88e0d-108">The number whose bitwise representation is to be shifted to the left (more significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="88e0d-109">金额： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="88e0d-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="88e0d-110">要向左移动的位数 `value` 。</span><span class="sxs-lookup"><span data-stu-id="88e0d-110">The number of bits by which `value` is to be shifted to the left.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="88e0d-111">输出： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="88e0d-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="88e0d-112">的值 `value` ，按位向左移动 `amount` 。</span><span class="sxs-lookup"><span data-stu-id="88e0d-112">The value of `value`, shifted left by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="88e0d-113">备注</span><span class="sxs-lookup"><span data-stu-id="88e0d-113">Remarks</span></span>

<span data-ttu-id="88e0d-114">以下项是等效的：</span><span class="sxs-lookup"><span data-stu-id="88e0d-114">The following are equivalent:</span></span>

```Q#
let c = a <<< b;
let c = LeftShiftedL(a, b);
```