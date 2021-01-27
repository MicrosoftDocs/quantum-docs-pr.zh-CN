---
uid: Microsoft.Quantum.Convert.BoolArrayAsBigInt
title: BoolArrayAsBigInt 函数
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsBigInt
qsharp.summary: Converts a given array of Booleans to an equivalent big integer. The 0 element of the array is the least significant bit of the big integer.
ms.openlocfilehash: 220a733b94fd62cef21ab13e1cb3d3f973861506
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/26/2021
ms.locfileid: "98834411"
---
# <a name="boolarrayasbigint-function"></a><span data-ttu-id="bca68-102">BoolArrayAsBigInt 函数</span><span class="sxs-lookup"><span data-stu-id="bca68-102">BoolArrayAsBigInt function</span></span>

<span data-ttu-id="bca68-103">命名空间 [：](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="bca68-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="bca68-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="bca68-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="bca68-105">将给定的布尔值数组转换为等效的大整数。</span><span class="sxs-lookup"><span data-stu-id="bca68-105">Converts a given array of Booleans to an equivalent big integer.</span></span>
<span data-ttu-id="bca68-106">数组的0元素是大整数的最小有效位。</span><span class="sxs-lookup"><span data-stu-id="bca68-106">The 0 element of the array is the least significant bit of the big integer.</span></span>

```qsharp
function BoolArrayAsBigInt (a : Bool[]) : BigInt
```


## <a name="input"></a><span data-ttu-id="bca68-107">输入</span><span class="sxs-lookup"><span data-stu-id="bca68-107">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="bca68-108">a： [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="bca68-108">a : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>





## <a name="output--bigint"></a><span data-ttu-id="bca68-109">输出： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="bca68-109">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>



## <a name="remarks"></a><span data-ttu-id="bca68-110">备注</span><span class="sxs-lookup"><span data-stu-id="bca68-110">Remarks</span></span>

<span data-ttu-id="bca68-111">有关更多详细信息，请参阅 [c # BigInteger 构造函数](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) 。</span><span class="sxs-lookup"><span data-stu-id="bca68-111">See [C# BigInteger constructor](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) for more details.</span></span>