---
uid: Microsoft.Quantum.Arrays.SequenceL
title: SequenceL 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 3e5c7f64825f09d82792d3e46fe3f53f5814510b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220257"
---
# <a name="sequencel-function"></a><span data-ttu-id="817f4-102">SequenceL 函数</span><span class="sxs-lookup"><span data-stu-id="817f4-102">SequenceL function</span></span>

<span data-ttu-id="817f4-103">命名空间 [：](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="817f4-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="817f4-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="817f4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="817f4-105">获取给定时间间隔内的整数数组。</span><span class="sxs-lookup"><span data-stu-id="817f4-105">Get an array of integers in a given interval.</span></span>

```qsharp
function SequenceL (from : BigInt, to : BigInt) : BigInt[]
```


## <a name="input"></a><span data-ttu-id="817f4-106">输入</span><span class="sxs-lookup"><span data-stu-id="817f4-106">Input</span></span>

### <a name="from--bigint"></a><span data-ttu-id="817f4-107">from： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="817f4-107">from : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="817f4-108">间隔的包含开始索引。</span><span class="sxs-lookup"><span data-stu-id="817f4-108">An inclusive start index of the interval.</span></span>


### <a name="to--bigint"></a><span data-ttu-id="817f4-109">to： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="817f4-109">to : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="817f4-110">不小于的间隔的非独占结束索引 `from` 。</span><span class="sxs-lookup"><span data-stu-id="817f4-110">An inclusive end index of the interval that is not smaller than `from`.</span></span>



## <a name="output--bigint"></a><span data-ttu-id="817f4-111">输出： [BigInt](xref:microsoft.quantum.lang-ref.bigint)[]</span><span class="sxs-lookup"><span data-stu-id="817f4-111">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)[]</span></span>

<span data-ttu-id="817f4-112">一个包含数字序列的数组， `from` `from + 1` ，...， `to` 。</span><span class="sxs-lookup"><span data-stu-id="817f4-112">An array containing the sequence of numbers `from`, `from + 1`, ..., `to`.</span></span>

## <a name="remarks"></a><span data-ttu-id="817f4-113">备注</span><span class="sxs-lookup"><span data-stu-id="817f4-113">Remarks</span></span>

<span data-ttu-id="817f4-114">与之间的 `from` 差异 `to` 必须符合某个 `Int` 值。</span><span class="sxs-lookup"><span data-stu-id="817f4-114">The difference between `from` and `to` must fit into an `Int` value.</span></span>