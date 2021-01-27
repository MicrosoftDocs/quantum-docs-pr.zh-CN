---
uid: Microsoft.Quantum.Convert.RangeAsIntArray
title: RangeAsIntArray 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: RangeAsIntArray
qsharp.summary: Creates an array `arr` of integers enumerated by start..step..end.
ms.openlocfilehash: 8c6b83d78e3b22ea1a17a48de66592950bf905a3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850103"
---
# <a name="rangeasintarray-function"></a><span data-ttu-id="fb9c0-102">RangeAsIntArray 函数</span><span class="sxs-lookup"><span data-stu-id="fb9c0-102">RangeAsIntArray function</span></span>

<span data-ttu-id="fb9c0-103">命名空间 [：](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="fb9c0-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="fb9c0-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="fb9c0-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="fb9c0-105">创建一个 `arr` 由 start. 枚举的整数数组。步骤 .。。端面.</span><span class="sxs-lookup"><span data-stu-id="fb9c0-105">Creates an array `arr` of integers enumerated by start..step..end.</span></span>

```qsharp
function RangeAsIntArray (range : Range) : Int[]
```


## <a name="input"></a><span data-ttu-id="fb9c0-106">输入</span><span class="sxs-lookup"><span data-stu-id="fb9c0-106">Input</span></span>

### <a name="range--range"></a><span data-ttu-id="fb9c0-107">范围： [范围](xref:microsoft.quantum.lang-ref.range)</span><span class="sxs-lookup"><span data-stu-id="fb9c0-107">range : [Range](xref:microsoft.quantum.lang-ref.range)</span></span>

<span data-ttu-id="fb9c0-108">`Range` `start..step..end` 要转换为数组的值的。</span><span class="sxs-lookup"><span data-stu-id="fb9c0-108">A `Range` of values `start..step..end` to be converted to an array.</span></span>



## <a name="output--int"></a><span data-ttu-id="fb9c0-109">输出： [Int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="fb9c0-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="fb9c0-110">一个新的整数数组，对应于通过循环访问的值 `range` 。</span><span class="sxs-lookup"><span data-stu-id="fb9c0-110">A new array of integers corresponding to values iterated over by `range`.</span></span>

## <a name="example"></a><span data-ttu-id="fb9c0-111">示例</span><span class="sxs-lookup"><span data-stu-id="fb9c0-111">Example</span></span>

```qsharp
// The following returns [1,3,5,7];
let array = RangeAsIntArray(1..2..8);
```