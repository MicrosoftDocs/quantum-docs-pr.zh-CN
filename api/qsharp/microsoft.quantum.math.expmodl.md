---
uid: Microsoft.Quantum.Math.ExpModL
title: ExpModL 函数
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModL
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: 73d434bd364847b4e5e06d1a9f460424e0c50850
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "92700640"
---
# <a name="expmodl-function"></a><span data-ttu-id="41570-102">ExpModL 函数</span><span class="sxs-lookup"><span data-stu-id="41570-102">ExpModL function</span></span>

<span data-ttu-id="41570-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="41570-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="41570-104">软件包 [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="41570-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="41570-105">返回一个整数，该整数针对给定的模数引发了给定的幂。</span><span class="sxs-lookup"><span data-stu-id="41570-105">Returns an integer raised to a given power, with respect to a given modulus.</span></span>

```qsharp
function ExpModL (expBase : BigInt, power : BigInt, modulus : BigInt) : BigInt
```


## <a name="description"></a><span data-ttu-id="41570-106">说明</span><span class="sxs-lookup"><span data-stu-id="41570-106">Description</span></span>

<span data-ttu-id="41570-107">让我们通过 $N $ $p $ 和模数来表示 $x expBase。</span><span class="sxs-lookup"><span data-stu-id="41570-107">Let us denote expBase by $x$, power by $p$ and modulus by $N$.</span></span>
<span data-ttu-id="41570-108">该函数返回 $x ^ p \operatorname{mod} N $。</span><span class="sxs-lookup"><span data-stu-id="41570-108">The function returns $x^p \operatorname{mod} N$.</span></span>

<span data-ttu-id="41570-109">假定 $N $，$x $ 为正，且 power 为非负数。</span><span class="sxs-lookup"><span data-stu-id="41570-109">We assume that $N$, $x$ are positive and power is non-negative.</span></span>

## <a name="input"></a><span data-ttu-id="41570-110">输入</span><span class="sxs-lookup"><span data-stu-id="41570-110">Input</span></span>

### <a name="expbase--bigint"></a><span data-ttu-id="41570-111">expBase： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="41570-111">expBase : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>




### <a name="power--bigint"></a><span data-ttu-id="41570-112">power： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="41570-112">power : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>




### <a name="modulus--bigint"></a><span data-ttu-id="41570-113">模数： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="41570-113">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--bigint"></a><span data-ttu-id="41570-114">输出： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="41570-114">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>



## <a name="remarks"></a><span data-ttu-id="41570-115">注解</span><span class="sxs-lookup"><span data-stu-id="41570-115">Remarks</span></span>

<span data-ttu-id="41570-116">与中的位数成正比，而 `power` 不是 `power` 本身。</span><span class="sxs-lookup"><span data-stu-id="41570-116">Takes time proportional to the number of bits in `power`, not the `power` itself.</span></span>