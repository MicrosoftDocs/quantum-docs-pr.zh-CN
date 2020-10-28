---
uid: Microsoft.Quantum.Synthesis.IntegerBits
title: IntegerBits 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: IntegerBits
qsharp.summary: Returns all positions in which bits of an integer are set.
ms.openlocfilehash: ab459cd841cdac116cf0e98c094834f628b6a2d3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92696618"
---
# <a name="integerbits-function"></a><span data-ttu-id="276b3-102">IntegerBits 函数</span><span class="sxs-lookup"><span data-stu-id="276b3-102">IntegerBits function</span></span>

<span data-ttu-id="276b3-103">命名空间 [：](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="276b3-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="276b3-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="276b3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="276b3-105">返回在其中设置整数位的所有位置。</span><span class="sxs-lookup"><span data-stu-id="276b3-105">Returns all positions in which bits of an integer are set.</span></span>

```qsharp
function IntegerBits (value : Int, length : Int) : Int[]
```


## <a name="input"></a><span data-ttu-id="276b3-106">输入</span><span class="sxs-lookup"><span data-stu-id="276b3-106">Input</span></span>

### <a name="value--int"></a><span data-ttu-id="276b3-107">值： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="276b3-107">value : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="276b3-108">非负数。</span><span class="sxs-lookup"><span data-stu-id="276b3-108">A nonnegative number.</span></span>


### <a name="length--int"></a><span data-ttu-id="276b3-109">长度： [Int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="276b3-109">length : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="276b3-110">的二进制扩展中的位数 `value` 。</span><span class="sxs-lookup"><span data-stu-id="276b3-110">The number of bits in the binary expansion of `value`.</span></span>



## <a name="output--int"></a><span data-ttu-id="276b3-111">输出： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="276b3-111">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="276b3-112">一个包含所有位位置的数组， (从 0) 开始，该数组在 `value` 考虑所有位向上定位的二进制扩展中为 1 `length - 1` 。</span><span class="sxs-lookup"><span data-stu-id="276b3-112">An array containing all bit positions (starting from 0) that are 1 in the binary expansion of `value` considering all bits up to position `length - 1`.</span></span>  <span data-ttu-id="276b3-113">所有位置都按位置按递增顺序排列在数组中。</span><span class="sxs-lookup"><span data-stu-id="276b3-113">All positions are ordered in the array by position in an increasing order.</span></span>