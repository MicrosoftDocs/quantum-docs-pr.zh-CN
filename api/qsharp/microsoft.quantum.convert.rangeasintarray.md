---
uid: Microsoft.Quantum.Convert.RangeAsIntArray
title: RangeAsIntArray 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: RangeAsIntArray
qsharp.summary: Creates an array `arr` of integers enumerated by start..step..end.
ms.openlocfilehash: bd3ac51d2925d7a4450b2bc5e6f7899fcab18f2c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695653"
---
# <a name="rangeasintarray-function"></a><span data-ttu-id="c5a47-102">RangeAsIntArray 函数</span><span class="sxs-lookup"><span data-stu-id="c5a47-102">RangeAsIntArray function</span></span>

<span data-ttu-id="c5a47-103">命名空间 [：](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="c5a47-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="c5a47-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c5a47-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c5a47-105">创建一个 `arr` 由 start. 枚举的整数数组。步骤 .。。端面.</span><span class="sxs-lookup"><span data-stu-id="c5a47-105">Creates an array `arr` of integers enumerated by start..step..end.</span></span>

```qsharp
function RangeAsIntArray (range : Range) : Int[]
```


## <a name="input"></a><span data-ttu-id="c5a47-106">输入</span><span class="sxs-lookup"><span data-stu-id="c5a47-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="c5a47-107">范围： [范围](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="c5a47-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="c5a47-108">`Range` `start..step..end` 要转换为数组的值的。</span><span class="sxs-lookup"><span data-stu-id="c5a47-108">A `Range` of values `start..step..end` to be converted to an array.</span></span>



## <a name="output--int"></a><span data-ttu-id="c5a47-109">输出： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="c5a47-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="c5a47-110">一个新的整数数组，对应于通过循环访问的值 `range` 。</span><span class="sxs-lookup"><span data-stu-id="c5a47-110">A new array of integers corresponding to values iterated over by `range`.</span></span>