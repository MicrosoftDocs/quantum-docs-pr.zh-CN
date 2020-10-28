---
uid: Microsoft.Quantum.Convert.BoolArrayAsBigInt
title: BoolArrayAsBigInt 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsBigInt
qsharp.summary: Converts a given array of Booleans to an equivalent big integer. The 0 element of the array is the least significant bit of the big integer.
ms.openlocfilehash: 75656ba188a1b822eb42e98412365bf5873bf46e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695689"
---
# <a name="boolarrayasbigint-function"></a><span data-ttu-id="0ff6d-102">BoolArrayAsBigInt 函数</span><span class="sxs-lookup"><span data-stu-id="0ff6d-102">BoolArrayAsBigInt function</span></span>

<span data-ttu-id="0ff6d-103">命名空间 [：](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="0ff6d-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="0ff6d-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="0ff6d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="0ff6d-105">将给定的布尔值数组转换为等效的大整数。</span><span class="sxs-lookup"><span data-stu-id="0ff6d-105">Converts a given array of Booleans to an equivalent big integer.</span></span>
<span data-ttu-id="0ff6d-106">数组的0元素是大整数的最小有效位。</span><span class="sxs-lookup"><span data-stu-id="0ff6d-106">The 0 element of the array is the least significant bit of the big integer.</span></span>

```qsharp
function BoolArrayAsBigInt (a : Bool[]) : BigInt
```


## <a name="input"></a><span data-ttu-id="0ff6d-107">输入</span><span class="sxs-lookup"><span data-stu-id="0ff6d-107">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="0ff6d-108">a： [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="0ff6d-108">a : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>





## <a name="output--bigint"></a><span data-ttu-id="0ff6d-109">输出： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="0ff6d-109">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>



## <a name="remarks"></a><span data-ttu-id="0ff6d-110">注解</span><span class="sxs-lookup"><span data-stu-id="0ff6d-110">Remarks</span></span>

<span data-ttu-id="0ff6d-111">有关更多详细信息，请参阅 [c # BigInteger 构造函数](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) 。</span><span class="sxs-lookup"><span data-stu-id="0ff6d-111">See [C# BigInteger constructor](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) for more details.</span></span>