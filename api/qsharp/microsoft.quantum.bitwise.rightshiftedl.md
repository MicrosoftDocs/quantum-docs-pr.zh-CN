---
uid: Microsoft.Quantum.Bitwise.RightShiftedL
title: RightShiftedL 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedL
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: 03ed69c7151e62b91c4a036e301f99b45ce5ab62
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842098"
---
# <a name="rightshiftedl-function"></a><span data-ttu-id="ba931-102">RightShiftedL 函数</span><span class="sxs-lookup"><span data-stu-id="ba931-102">RightShiftedL function</span></span>

<span data-ttu-id="ba931-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="ba931-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="ba931-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="ba931-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="ba931-105">将数字的按位表示形式向右移位给定的位数。</span><span class="sxs-lookup"><span data-stu-id="ba931-105">Shifts the bitwise representation of a number right by a given number of bits.</span></span>

```qsharp
function RightShiftedL (value : BigInt, amount : Int) : BigInt
```


## <a name="input"></a><span data-ttu-id="ba931-106">输入</span><span class="sxs-lookup"><span data-stu-id="ba931-106">Input</span></span>

### <a name="value--bigint"></a><span data-ttu-id="ba931-107">值： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="ba931-107">value : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="ba931-108">要 (不太重要) 向右移动的按位表示形式的数字。</span><span class="sxs-lookup"><span data-stu-id="ba931-108">The number whose bitwise representation is to be shifted to the right (less significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="ba931-109">金额： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ba931-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ba931-110">要向右移动的位数 `value` 。</span><span class="sxs-lookup"><span data-stu-id="ba931-110">The number of bits by which `value` is to be shifted to the right.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="ba931-111">输出： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="ba931-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="ba931-112">的值，右移一 `value` `amount` 位。</span><span class="sxs-lookup"><span data-stu-id="ba931-112">The value of `value`, shifted right by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="ba931-113">备注</span><span class="sxs-lookup"><span data-stu-id="ba931-113">Remarks</span></span>

<span data-ttu-id="ba931-114">以下项是等效的：</span><span class="sxs-lookup"><span data-stu-id="ba931-114">The following are equivalent:</span></span>

```qsharp
let c = a >>> b;
let c = RightShiftedL(a, b);
```