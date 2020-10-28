---
uid: Microsoft.Quantum.Convert.IntAsBoolArray
title: IntAsBoolArray 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: IntAsBoolArray
qsharp.summary: Produces a binary representation of a positive integer, using the little-endian representation for the returned array.
ms.openlocfilehash: 9783a49a77bdc39ffe8c7725196eb620f4cd0100
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695666"
---
# <a name="intasboolarray-function"></a><span data-ttu-id="35f86-102">IntAsBoolArray 函数</span><span class="sxs-lookup"><span data-stu-id="35f86-102">IntAsBoolArray function</span></span>

<span data-ttu-id="35f86-103">命名空间 [：](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="35f86-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="35f86-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="35f86-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="35f86-105">使用返回的数组的小字节序表示形式，生成正整数的二进制表示形式。</span><span class="sxs-lookup"><span data-stu-id="35f86-105">Produces a binary representation of a positive integer, using the little-endian representation for the returned array.</span></span>

```qsharp
function IntAsBoolArray (number : Int, bits : Int) : Bool[]
```


## <a name="input"></a><span data-ttu-id="35f86-106">输入</span><span class="sxs-lookup"><span data-stu-id="35f86-106">Input</span></span>

### <a name="number--int"></a><span data-ttu-id="35f86-107">number： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="35f86-107">number : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="35f86-108">要转换为布尔值数组的正整数。</span><span class="sxs-lookup"><span data-stu-id="35f86-108">A positive integer to be converted to an array of boolean values.</span></span>


### <a name="bits--int"></a><span data-ttu-id="35f86-109">bits： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="35f86-109">bits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="35f86-110">的二进制表示形式的位数 `number` 。</span><span class="sxs-lookup"><span data-stu-id="35f86-110">The number of bits in the binary representation of `number`.</span></span>



## <a name="output--bool"></a><span data-ttu-id="35f86-111">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="35f86-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>

<span data-ttu-id="35f86-112">表示的布尔值数组 `number` 。</span><span class="sxs-lookup"><span data-stu-id="35f86-112">An array of boolean values representing `number`.</span></span>

## <a name="remarks"></a><span data-ttu-id="35f86-113">注解</span><span class="sxs-lookup"><span data-stu-id="35f86-113">Remarks</span></span>

<span data-ttu-id="35f86-114">输入 `bits` 必须介于0到63之间。</span><span class="sxs-lookup"><span data-stu-id="35f86-114">The input `bits` must be between 0 and 63.</span></span>
<span data-ttu-id="35f86-115">输入 `number` 必须介于0到 $ 2 ^ {\texttt{bits}}-$1 之间。</span><span class="sxs-lookup"><span data-stu-id="35f86-115">The input `number` must be between 0 and $2^{\texttt{bits}} - 1$.</span></span>