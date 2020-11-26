---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: IntAsBoolArray 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a positive integer, using the little-endian representation for the returned array.
ms.openlocfilehash: f89cb3d7ca29d7deaaf49573b2670534166caded
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224337"
---
# <a name="intasboolarray-function"></a><span data-ttu-id="125a8-102">IntAsBoolArray 函数</span><span class="sxs-lookup"><span data-stu-id="125a8-102">IntAsBoolArray function</span></span>

<span data-ttu-id="125a8-103">命名空间 [：](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="125a8-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="125a8-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="125a8-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="125a8-105">使用返回的数组的小字节序表示形式，生成正整数的二进制表示形式。</span><span class="sxs-lookup"><span data-stu-id="125a8-105">Produces a binary representation of a positive integer, using the little-endian representation for the returned array.</span></span>

```qsharp
function IntAsBoolArray (number : Int, bits : Int) : Bool[]
```


## <a name="input"></a><span data-ttu-id="125a8-106">输入</span><span class="sxs-lookup"><span data-stu-id="125a8-106">Input</span></span>

### <a name="number--int"></a><span data-ttu-id="125a8-107">number： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="125a8-107">number : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="125a8-108">要转换为布尔值数组的正整数。</span><span class="sxs-lookup"><span data-stu-id="125a8-108">A positive integer to be converted to an array of boolean values.</span></span>


### <a name="bits--int"></a><span data-ttu-id="125a8-109">bits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="125a8-109">bits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="125a8-110">的二进制表示形式的位数 `number` 。</span><span class="sxs-lookup"><span data-stu-id="125a8-110">The number of bits in the binary representation of `number`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="125a8-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="125a8-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="125a8-112">表示的布尔值数组 `number` 。</span><span class="sxs-lookup"><span data-stu-id="125a8-112">An array of boolean values representing `number`.</span></span>

## <a name="remarks"></a><span data-ttu-id="125a8-113">备注</span><span class="sxs-lookup"><span data-stu-id="125a8-113">Remarks</span></span>

<span data-ttu-id="125a8-114">输入 `bits` 必须介于0到63之间。</span><span class="sxs-lookup"><span data-stu-id="125a8-114">The input `bits` must be between 0 and 63.</span></span>
<span data-ttu-id="125a8-115">输入 `number` 必须介于0到 $ 2 ^ {\texttt{bits}}-$1 之间。</span><span class="sxs-lookup"><span data-stu-id="125a8-115">The input `number` must be between 0 and $2^{\texttt{bits}} - 1$.</span></span>