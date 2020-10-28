---
uid: Microsoft.Quantum.Convert.MaybeBigIntAsInt
title: MaybeBigIntAsInt 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: MaybeBigIntAsInt
qsharp.summary: Converts a given big integer to an equivalent integer, if possible. The function returns a pair of the resulting integer and a Boolean flag which is true, if and only if the conversion was possible.
ms.openlocfilehash: b91912f6f669afad888e71174fef6e2e6f8e7156
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92695663"
---
# <a name="maybebigintasint-function"></a><span data-ttu-id="93976-102">MaybeBigIntAsInt 函数</span><span class="sxs-lookup"><span data-stu-id="93976-102">MaybeBigIntAsInt function</span></span>

<span data-ttu-id="93976-103">命名空间 [：](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="93976-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="93976-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="93976-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="93976-105">如果可能，将给定的大整数转换为等效的整数。</span><span class="sxs-lookup"><span data-stu-id="93976-105">Converts a given big integer to an equivalent integer, if possible.</span></span>
<span data-ttu-id="93976-106">当且仅当可以进行转换时，函数将返回生成的整数对以及布尔标志。</span><span class="sxs-lookup"><span data-stu-id="93976-106">The function returns a pair of the resulting integer and a Boolean flag which is true, if and only if the conversion was possible.</span></span>

```qsharp
function MaybeBigIntAsInt (a : BigInt) : (Int, Bool)
```


## <a name="input"></a><span data-ttu-id="93976-107">输入</span><span class="sxs-lookup"><span data-stu-id="93976-107">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="93976-108">a： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="93976-108">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--intbool"></a><span data-ttu-id="93976-109">Output： ([Int](xref:microsoft.quantum.lang-ref.int)、[Bool](xref:microsoft.quantum.lang-ref.bool)) </span><span class="sxs-lookup"><span data-stu-id="93976-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Bool](xref:microsoft.quantum.lang-ref.bool))</span></span>



## <a name="remarks"></a><span data-ttu-id="93976-110">注解</span><span class="sxs-lookup"><span data-stu-id="93976-110">Remarks</span></span>

<span data-ttu-id="93976-111">有关更多详细信息，请参阅 [c # BigInteger 构造函数](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) 。</span><span class="sxs-lookup"><span data-stu-id="93976-111">See [C# BigInteger constructor](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) for more details.</span></span>