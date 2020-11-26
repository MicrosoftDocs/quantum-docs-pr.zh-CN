---
uid: Microsoft.Quantum.Bitwise.RightShiftedI
title: RightShiftedI 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Bitwise
qsharp.name: RightShiftedI
qsharp.summary: Shifts the bitwise representation of a number right by a given number of bits.
ms.openlocfilehash: b20a4a8c281a470af9a4828f8a5ca905a7918723
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209768"
---
# <a name="rightshiftedi-function"></a><span data-ttu-id="26a31-102">RightShiftedI 函数</span><span class="sxs-lookup"><span data-stu-id="26a31-102">RightShiftedI function</span></span>

<span data-ttu-id="26a31-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Bitwise)</span><span class="sxs-lookup"><span data-stu-id="26a31-103">Namespace: [Microsoft.Quantum.Bitwise](xref:Microsoft.Quantum.Bitwise)</span></span>

<span data-ttu-id="26a31-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="26a31-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="26a31-105">将数字的按位表示形式向右移位给定的位数。</span><span class="sxs-lookup"><span data-stu-id="26a31-105">Shifts the bitwise representation of a number right by a given number of bits.</span></span>

```qsharp
function RightShiftedI (value : Int, amount : Int) : Int
```


## <a name="input"></a><span data-ttu-id="26a31-106">输入</span><span class="sxs-lookup"><span data-stu-id="26a31-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="26a31-107">值： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="26a31-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="26a31-108">要 (不太重要) 向右移动的按位表示形式的数字。</span><span class="sxs-lookup"><span data-stu-id="26a31-108">The number whose bitwise representation is to be shifted to the right (less significant).</span></span>


### <a name="amount--int"></a><span data-ttu-id="26a31-109">金额： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="26a31-109">amount : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="26a31-110">要向右移动的位数 `value` 。</span><span class="sxs-lookup"><span data-stu-id="26a31-110">The number of bits by which `value` is to be shifted to the right.</span></span>



## <a name="output--int"></a><span data-ttu-id="26a31-111">输出： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="26a31-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="26a31-112">的值，右移一 `value` `amount` 位。</span><span class="sxs-lookup"><span data-stu-id="26a31-112">The value of `value`, shifted right by `amount` bits.</span></span>

## <a name="remarks"></a><span data-ttu-id="26a31-113">备注</span><span class="sxs-lookup"><span data-stu-id="26a31-113">Remarks</span></span>

<span data-ttu-id="26a31-114">以下项是等效的：</span><span class="sxs-lookup"><span data-stu-id="26a31-114">The following are equivalent:</span></span>

```Q#
let c = a >>> b;
let c = RightShiftedI(a, b);
```