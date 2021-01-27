---
uid: Microsoft.Quantum.Bitwise.RightShiftedI
title: RightShiftedI 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedI
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: 5c3106eb73178554184cbfb37333c027805c69f3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845258"
---
# <a name="rightshiftedi-function"></a><span data-ttu-id="0b22f-102">RightShiftedI 函数</span><span class="sxs-lookup"><span data-stu-id="0b22f-102">RightShiftedI function</span></span>

<span data-ttu-id="0b22f-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="0b22f-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="0b22f-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="0b22f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="0b22f-105">将数字的按位表示形式向右移位给定的位数。</span><span class="sxs-lookup"><span data-stu-id="0b22f-105">Shifts the bitwise representation of a number right by a given number of bits.</span></span>

```qsharp
function RightShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a><span data-ttu-id="0b22f-106">输入</span><span class="sxs-lookup"><span data-stu-id="0b22f-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="0b22f-107">值： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0b22f-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0b22f-108">要 (不太重要) 向右移动的按位表示形式的数字。</span><span class="sxs-lookup"><span data-stu-id="0b22f-108">The number whose bitwise representation is to be shifted to the right (less significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="0b22f-109">金额： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0b22f-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0b22f-110">要向右移动的位数 `value` 。</span><span class="sxs-lookup"><span data-stu-id="0b22f-110">The number of bits by which `value` is to be shifted to the right.</span></span>



## <a name="output--int"></a><span data-ttu-id="0b22f-111">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="0b22f-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="0b22f-112">的值，右移一 `value` `amount` 位。</span><span class="sxs-lookup"><span data-stu-id="0b22f-112">The value of `value`, shifted right by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="0b22f-113">备注</span><span class="sxs-lookup"><span data-stu-id="0b22f-113">Remarks</span></span>

<span data-ttu-id="0b22f-114">以下项是等效的：</span><span class="sxs-lookup"><span data-stu-id="0b22f-114">The following are equivalent:</span></span>

```qsharp
let c = a >>> b;
let c = RightShiftedI(a, b);
```