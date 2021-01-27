---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: IntAsBoolArray 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a non-negative integer, using the little-endian representation for the returned array.
ms.openlocfilehash: 8b3d230605cc756a5da01e45e47f91c5b8e9f541
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98833308"
---
# <a name="intasboolarray-function"></a><span data-ttu-id="e68d7-102">IntAsBoolArray 函数</span><span class="sxs-lookup"><span data-stu-id="e68d7-102">IntAsBoolArray function</span></span>

<span data-ttu-id="e68d7-103">命名空间 [：](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="e68d7-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="e68d7-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="e68d7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="e68d7-105">使用返回的数组的小字节序表示形式，生成非负整数的二进制表示形式。</span><span class="sxs-lookup"><span data-stu-id="e68d7-105">Produces a binary representation of a non-negative integer, using the little-endian representation for the returned array.</span></span>

```qsharp
function IntAsBoolArray (number : Int, bits : Int) : Bool[]
```


## <a name="input"></a><span data-ttu-id="e68d7-106">输入</span><span class="sxs-lookup"><span data-stu-id="e68d7-106">Input</span></span>

### <a name="number--int"></a><span data-ttu-id="e68d7-107">number： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e68d7-107">number : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e68d7-108">要转换为布尔值数组的非负整数。</span><span class="sxs-lookup"><span data-stu-id="e68d7-108">A non-negative integer to be converted to an array of boolean values.</span></span>


### <a name="bits--int"></a><span data-ttu-id="e68d7-109">bits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="e68d7-109">bits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="e68d7-110">的二进制表示形式的位数 `number` 。</span><span class="sxs-lookup"><span data-stu-id="e68d7-110">The number of bits in the binary representation of `number`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="e68d7-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="e68d7-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="e68d7-112">表示的布尔值数组 `number` 。</span><span class="sxs-lookup"><span data-stu-id="e68d7-112">An array of boolean values representing `number`.</span></span>

## <a name="remarks"></a><span data-ttu-id="e68d7-113">备注</span><span class="sxs-lookup"><span data-stu-id="e68d7-113">Remarks</span></span>

<span data-ttu-id="e68d7-114">输入 `bits` 必须介于0到63之间。</span><span class="sxs-lookup"><span data-stu-id="e68d7-114">The input `bits` must be between 0 and 63.</span></span>
<span data-ttu-id="e68d7-115">输入 `number` 必须介于0到 $ 2 ^ {\texttt{bits}}-$1 之间。</span><span class="sxs-lookup"><span data-stu-id="e68d7-115">The input `number` must be between 0 and $2^{\texttt{bits}} - 1$.</span></span>