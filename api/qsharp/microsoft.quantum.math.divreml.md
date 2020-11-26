---
uid: Microsoft.Quantum.Math.DivRemL
title: DivRemL 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: DivRemL
qsharp.summary: Divides one BigInteger value by another, returns the result and the remainder as a tuple.
ms.openlocfilehash: 40ce295b82d138ad0b5261641c7f3649631d309d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210839"
---
# <a name="divreml-function"></a><span data-ttu-id="0c431-102">DivRemL 函数</span><span class="sxs-lookup"><span data-stu-id="0c431-102">DivRemL function</span></span>

<span data-ttu-id="0c431-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="0c431-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="0c431-104">包： [QSharp。](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="0c431-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="0c431-105">将一个 BigInteger 值除以另一个值，返回结果，并将余数作为元组返回。</span><span class="sxs-lookup"><span data-stu-id="0c431-105">Divides one BigInteger value by another, returns the result and the remainder as a tuple.</span></span>

```qsharp
function DivRemL (dividend : BigInt, divisor : BigInt) : (BigInt, BigInt)
```


## <a name="input"></a><span data-ttu-id="0c431-106">输入</span><span class="sxs-lookup"><span data-stu-id="0c431-106">Input</span></span>

### <a name="dividend--bigint"></a><span data-ttu-id="0c431-107">被除数： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="0c431-107">dividend : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>




### <a name="divisor--bigint"></a><span data-ttu-id="0c431-108">除数： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="0c431-108">divisor : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--bigintbigint"></a><span data-ttu-id="0c431-109">输出： ([bigint](xref:microsoft.quantum.lang-ref.bigint)、[bigint](xref:microsoft.quantum.lang-ref.bigint)) </span><span class="sxs-lookup"><span data-stu-id="0c431-109">Output : ([BigInt](xref:microsoft.quantum.lang-ref.bigint),[BigInt](xref:microsoft.quantum.lang-ref.bigint))</span></span>



## <a name="remarks"></a><span data-ttu-id="0c431-110">备注</span><span class="sxs-lookup"><span data-stu-id="0c431-110">Remarks</span></span>

<span data-ttu-id="0c431-111">有关更多详细信息，请参阅[BigInteger。](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.divrem)</span><span class="sxs-lookup"><span data-stu-id="0c431-111">See [System.Numerics.BigInteger.DivRem](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.divrem) for more details.</span></span>