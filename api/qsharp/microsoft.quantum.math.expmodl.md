---
uid: Microsoft.Quantum.Math.ExpModL
title: ExpModL 函数
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModL
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: 07da113caeb9f6f3f3f3f92f13478f33021bfa14
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/26/2020
ms.locfileid: "96210738"
---
# <a name="expmodl-function"></a><span data-ttu-id="54f5a-102">ExpModL 函数</span><span class="sxs-lookup"><span data-stu-id="54f5a-102">ExpModL function</span></span>

<span data-ttu-id="54f5a-103">命名空间： [Microsoft 量子](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="54f5a-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="54f5a-104">包： [Microsoft 量子. 标准版](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="54f5a-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="54f5a-105">返回一个整数，该整数针对给定的模数引发了给定的幂。</span><span class="sxs-lookup"><span data-stu-id="54f5a-105">Returns an integer raised to a given power, with respect to a given modulus.</span></span>

```qsharp
function ExpModL (expBase : BigInt, power : BigInt, modulus : BigInt) : BigInt
```


## <a name="description"></a><span data-ttu-id="54f5a-106">描述</span><span class="sxs-lookup"><span data-stu-id="54f5a-106">Description</span></span>

<span data-ttu-id="54f5a-107">让我们通过 $N $ $p $ 和模数来表示 $x expBase。</span><span class="sxs-lookup"><span data-stu-id="54f5a-107">Let us denote expBase by $x$, power by $p$ and modulus by $N$.</span></span>
<span data-ttu-id="54f5a-108">该函数返回 $x ^ p \operatorname{mod} N $。</span><span class="sxs-lookup"><span data-stu-id="54f5a-108">The function returns $x^p \operatorname{mod} N$.</span></span>

<span data-ttu-id="54f5a-109">假定 $N $，$x $ 为正，且 power 为非负数。</span><span class="sxs-lookup"><span data-stu-id="54f5a-109">We assume that $N$, $x$ are positive and power is non-negative.</span></span>

## <a name="input"></a><span data-ttu-id="54f5a-110">输入</span><span class="sxs-lookup"><span data-stu-id="54f5a-110">Input</span></span>

### <a name="expbase--bigint"></a><span data-ttu-id="54f5a-111">expBase： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="54f5a-111">expBase : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>




### <a name="power--bigint"></a><span data-ttu-id="54f5a-112">power： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="54f5a-112">power : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>




### <a name="modulus--bigint"></a><span data-ttu-id="54f5a-113">模数： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="54f5a-113">modulus : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>





## <a name="output--bigint"></a><span data-ttu-id="54f5a-114">输出： [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="54f5a-114">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>



## <a name="remarks"></a><span data-ttu-id="54f5a-115">备注</span><span class="sxs-lookup"><span data-stu-id="54f5a-115">Remarks</span></span>

<span data-ttu-id="54f5a-116">与中的位数成正比，而 `power` 不是 `power` 本身。</span><span class="sxs-lookup"><span data-stu-id="54f5a-116">Takes time proportional to the number of bits in `power`, not the `power` itself.</span></span>