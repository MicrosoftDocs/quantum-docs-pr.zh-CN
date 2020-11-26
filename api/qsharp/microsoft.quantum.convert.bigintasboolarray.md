---
uid: Microsoft.Quantum.Convert.BigIntAsBoolArray
title: BigIntAsBoolArray 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BigIntAsBoolArray
qsharp.summary: Converts a given big integer to an array of Booleans. The 0 element of the array is the least significant bit of the big integer.
ms.openlocfilehash: 593fad99ef22d3c906b9f10adc07638bed227509
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224541"
---
# <a name="bigintasboolarray-function"></a><span data-ttu-id="49b8f-102">BigIntAsBoolArray 函数</span><span class="sxs-lookup"><span data-stu-id="49b8f-102">BigIntAsBoolArray function</span></span>

<span data-ttu-id="49b8f-103">命名空间 [：](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="49b8f-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="49b8f-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="49b8f-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="49b8f-105">将给定的大整数转换为布尔数组。</span><span class="sxs-lookup"><span data-stu-id="49b8f-105">Converts a given big integer to an array of Booleans.</span></span>
<span data-ttu-id="49b8f-106">数组的0元素是大整数的最小有效位。</span><span class="sxs-lookup"><span data-stu-id="49b8f-106">The 0 element of the array is the least significant bit of the big integer.</span></span>

```qsharp
function BigIntAsBoolArray (a : BigInt) : Bool[]
```


## <a name="input"></a><span data-ttu-id="49b8f-107">输入</span><span class="sxs-lookup"><span data-stu-id="49b8f-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="49b8f-108">a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="49b8f-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--bool"></a><span data-ttu-id="49b8f-109">Output： [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="49b8f-109">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>



## <a name="remarks"></a><span data-ttu-id="49b8f-110">备注</span><span class="sxs-lookup"><span data-stu-id="49b8f-110">Remarks</span></span>

<span data-ttu-id="49b8f-111">有关更多详细信息，请参阅 [c # BigInteger 构造函数](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) 。</span><span class="sxs-lookup"><span data-stu-id="49b8f-111">See [C# BigInteger constructor](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) for more details.</span></span>